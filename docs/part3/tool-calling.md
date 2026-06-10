# 工具调用

> 目标：让模型不只生成文本，而是能选择工具、传递参数、接收结果并继续完成任务。

## 学习重点

- Tool Schema 设计
- 工具描述如何影响调用准确率
- 参数校验
- 工具调用失败处理
- 并行工具调用
- 人类确认

## 项目连接

- CodePilot Lab：文件、Shell、Git、测试工具
- Agent Tool Platform：插件工具注册、权限和路由

## 待补充

- OpenAI Tool Calling 示例
- Anthropic Tool Use 示例
- 工具描述评分清单

---

## 手写 ReAct Agent Demo：天气与景点推荐

> 对应代码：`project/hello_llm.py`

这个 demo 展示了一个最小的手写 ReAct Agent 流程。

它完成的任务是：

```text
用户请求：查询北京天气，并根据天气推荐一个适合的旅游景点。
```

整个过程不是一次模型调用完成，而是通过多轮循环完成：

```text
Thought → Action → Observation → Thought → Action → Observation → Finish
```

---

### 1. Demo 的整体结构

代码可以分成五个部分：

1. 配置和系统提示词
2. 工具函数
3. 工具注册表
4. LLM 客户端
5. Agent 主循环

---

### 2. 配置和系统提示词

代码通过 `python-dotenv` 从项目根目录读取 `.env`：

```python
PROJECT_ROOT = Path(__file__).resolve().parents[1]
load_dotenv(PROJECT_ROOT / ".env", encoding="utf-8-sig")
```

这样无论从项目根目录运行，还是从 `project/` 目录运行，都能读取根目录的 `.env`。

配置项包括：

```python
OPENAI_API_KEY
OPENAI_BASE_URL
LLM_MODEL
TAVILY_API_KEY
```

当前使用的是 OpenAI-compatible API，因此可以接入 OpenAI、DeepSeek 或其他兼容服务。

系统提示词 `AGENT_SYSTEM_PROMPT` 告诉模型：

- 你是一个可以使用工具的旅行助手。
- 必须按 `Thought` 和 `Action` 的格式输出。
- 可用工具包括 `get_weather` 和 `get_attraction`。
- 如果任务完成，使用 `Finish[...]` 输出最终答案。

这一步很重要，因为当前 demo 没有使用官方 Function Calling，而是让模型按文本格式输出工具调用指令。

---

### 3. 工具函数

demo 中有两个工具。

第一个工具是天气查询：

```python
def get_weather(city: str) -> str:
```

它会请求 `wttr.in`，根据城市查询当前天气，并返回自然语言结果。

例如：

```text
北京当前天气:Cloudy ，气温20摄氏度
```

第二个工具是景点推荐：

```python
def get_attraction(city: str, weather: str) -> str:
```

它使用 Tavily Search API，根据城市和天气搜索适合游玩的景点。

例如：

```text
In cloudy weather, visit the Forbidden City and the National Museum of China indoors...
```

---

### 4. 工具注册表

工具函数被放入一个字典：

```python
available_tools = {
    "get_weather": get_weather,
    "get_attraction": get_attraction,
}
```

这个字典的作用是建立映射：

```text
模型输出的工具名 → Python 中真正执行的函数
```

例如模型输出：

```text
Action: get_weather(city="北京")
```

代码会解析出工具名：

```text
get_weather
```

然后到 `available_tools` 中找到真正的 Python 函数并执行。

---

### 5. LLM 客户端

代码中封装了一个客户端：

```python
class OpenAICompatibleClient:
```

核心调用逻辑是：

```python
response = self.client.chat.completions.create(
    model=self.model,
    messages=messages,
    stream=False
)
```

每次调用模型时，都会传入两类消息：

```python
messages = [
    {"role": "system", "content": system_prompt},
    {"role": "user", "content": prompt}
]
```

其中：

- `system_prompt` 负责约束模型行为。
- `prompt` 是当前任务历史，包括用户请求、模型前一次输出和工具 Observation。

---

### 6. Agent 主循环

主循环最多执行 5 轮：

```python
for i in range(5):
```

设置最大轮数是为了避免 Agent 无限循环。

每一轮大致做 6 件事。

第一步，拼接历史：

```python
full_prompt = "\n".join(prompt_history)
```

第二步，调用模型：

```python
llm_output = llm.generate(full_prompt, system_prompt=AGENT_SYSTEM_PROMPT)
```

第三步，解析模型输出中的 `Action`：

```python
action_match = re.search(r"Action: (.*)", llm_output, re.DOTALL)
```

第四步，如果 Action 是 `Finish[...]`，任务结束：

```python
if action_str.startswith("Finish"):
```

第五步，如果 Action 是工具调用，则解析工具名和参数：

```python
tool_name = re.search(r"(\w+)\(", action_str).group(1)
args_str = re.search(r"\((.*)\)", action_str).group(1)
kwargs = dict(re.findall(r'(\w+)="([^"]*)"', args_str))
```

例如：

```text
get_weather(city="北京")
```

会被解析为：

```python
tool_name = "get_weather"
kwargs = {"city": "北京"}
```

第六步，执行工具，并把结果作为 Observation 放回历史：

```python
observation = available_tools[tool_name](**kwargs)
observation_str = f"Observation: {observation}"
prompt_history.append(observation_str)
```

下一轮模型就能基于 Observation 继续推理。

---

### 7. 一次实际运行过程

用户输入：

```text
你好，请帮我查询一下今天北京的天气，然后根据天气推荐一个合适的旅游景点。
```

#### 第一轮

模型输出：

```text
Thought: 用户需要查询北京的天气，然后根据天气推荐景点。我首先调用 get_weather 工具获取天气信息。
Action: get_weather(city="北京")
```

代码解析出：

```python
tool_name = "get_weather"
kwargs = {"city": "北京"}
```

然后执行：

```python
get_weather(city="北京")
```

得到 Observation：

```text
Observation: 北京当前天气:Cloudy ，气温20摄氏度
```

#### 第二轮

模型看到天气结果后，继续输出：

```text
Thought: 已经获取到天气信息，北京当前是阴天。接下来根据天气推荐景点，调用 get_attraction 工具。
Action: get_attraction(city="北京", weather="Cloudy")
```

代码执行：

```python
get_attraction(city="北京", weather="Cloudy")
```

得到 Observation：

```text
Observation: In cloudy weather, visit the Forbidden City and the National Museum of China indoors...
```

#### 第三轮

模型已经获得天气和景点推荐，于是结束任务：

```text
Thought: 根据天气信息和景点推荐结果，我已经获得了足够的资料，可以回答用户的问题了。
Action: Finish[根据查询，北京当前天气为阴天，气温20摄氏度...]
```

代码检测到 `Finish[...]` 后，输出最终答案并结束循环。

---

### 8. 为什么会出现“已截断多余的 Thought-Action 对”

运行时可能出现：

```text
已截断多余的 Thought-Action 对
```

原因是模型有时会一次输出多步内容。

但当前 Agent 循环要求：

```text
每轮只执行一个 Action。
```

因此代码通过正则只保留第一组 `Thought + Action`，避免模型提前编造 Observation 或跳过工具执行。

这说明一个重要事实：

> 模型不是严格程序，它可能不完全遵守协议。Agent 外层代码必须做格式约束、解析、截断、重试和错误处理。

---

### 9. 当前 demo 和官方 Tool Calling 的区别

当前 demo 是手写 ReAct：

```text
模型输出文本 Action
Python 用正则解析文本
Python 执行工具
```

官方 Tool Calling 是：

```text
向模型传入工具 JSON Schema
模型返回结构化 tool_call
Python 根据 tool_call 执行工具
```

对比：

| 项目 | 当前 demo | 官方 Tool Calling |
|------|----------|-------------------|
| 工具描述 | 写在 Prompt 里 | 写成 JSON Schema |
| 工具调用 | 模型输出文本 | 模型返回结构化 tool call |
| 参数解析 | 正则解析 | SDK 返回结构化参数 |
| 稳定性 | 较弱 | 更强 |
| 学习价值 | 理解 Agent 原理 | 更适合生产使用 |

---

### 10. 这个 demo 展示的 Agent 核心概念

这个 demo 展示了 Agent 的几个基础组成：

- **LLM 是大脑**：负责思考下一步做什么。
- **工具是手**：负责查询天气、搜索景点。
- **Python 是执行器**：负责解析 Action 并真正执行函数。
- **Observation 是反馈**：工具执行结果会重新交给模型。
- **循环是关键**：多轮循环让 Agent 能完成多步骤任务。
- **协议约束很重要**：模型必须按约定格式输出，代码才能解析和执行。

---

### 11. 和 CodePilot Lab 的关系

当前 demo 的工具是：

```text
get_weather
get_attraction
```

未来 CodePilot Lab 中的工具会变成：

```text
read_file
write_file
run_command
git_diff
run_tests
```

当前任务是：

```text
查询天气并推荐景点
```

未来任务会变成：

```text
修复一个 bug
添加一个功能
运行测试并根据失败结果继续修复
```

底层结构仍然类似：

```text
Thought → Action → Observation → Next Thought
```

因此，这个 demo 是后续学习 Coding Agent 的第一块积木。
