# 当前学习计划

> 只记录当前这一小段计划。完成后再根据学习反馈更新下一段，不一次性制定过远计划。

---

## 当前阶段

**阶段 1：AI 应用基础最小闭环**

目标不是马上开始 CodePilot Lab，而是先补齐它的前置能力：

- 调用模型
- 写基础 Prompt
- 获得稳定结构化输出
- 让模型调用本地工具
- 记录学习过程

---

## 本轮目标

完成 3 个最小练习：

```text
hello_llm.py
structured_output.py
tool_calling_demo.py
```

完成后，需要能说明：

- 如何用 Python 调用一次 LLM
- 如何让模型按固定 JSON 结构输出
- Tool Calling 的基本流程是什么
- 模型“调用工具”和代码真正执行函数之间的关系

---

## 学习资料

本轮只使用这些资料，不扩展新资料：

1. DeepLearning.ai - Prompt Engineering for Developers
2. OpenAI API Docs
3. OpenAI Cookbook 中和 Structured Output / Tool Calling 相关的示例
4. Generative AI for Beginners Lesson 04、05、11（可选，时间不够就先跳过）

暂时不看：

- LangGraph
- MCP
- CrewAI / AutoGen
- AIGC-Interview-Book
- agent-study
- Claude Code 架构分析

---

## 执行步骤

### Step 1：看 Prompt Engineering 短课

目标：

- 建立 Prompt 基础概念
- 了解总结、分类、抽取、转换等常见任务
- 记录可复用 Prompt 技巧

记录到：

```text
raw/prompt-notes.md
```

如果没有时间整理正式笔记，只记录要点即可。

---

### Step 2：跑通模型调用

目标文件：

```text
hello_llm.py
```

最小目标：

- 从环境变量读取 API Key
- 调用一次模型
- 打印模型回复

完成标准：

- 能在本地命令行运行
- 能看到模型返回结果

---

### Step 3：结构化输出练习

目标文件：

```text
structured_output.py
```

练习任务：

输入一段学习资料描述，让模型输出固定 JSON：

```json
{
  "name": "资料名称",
  "type": "official_docs | course | cookbook | project | theory | interview",
  "stage": "阶段 1 | 阶段 2 | 阶段 3 | 阶段 4 | 阶段 5",
  "priority": "high | medium | low",
  "reason": "推荐或暂缓的原因"
}
```

完成标准：

- 输出可以被 Python 解析成 JSON
- 字段稳定
- 不夹杂多余自然语言

---

### Step 4：Tool Calling 最小练习

目标文件：

```text
tool_calling_demo.py
```

练习任务：

先写一个本地函数：

```python
def get_learning_stage(topic: str) -> str:
    ...
```

让模型根据用户输入判断是否需要调用这个工具。

示例输入：

```text
我现在想学 LangGraph，应该放在哪个阶段？
```

期望流程：

```text
用户问题
→ 模型判断需要查询学习阶段
→ 返回 tool call
→ Python 执行本地函数
→ 把结果返回给模型
→ 模型生成最终回答
```

完成标准：

- 能看到模型产生工具调用
- 能看到 Python 执行本地函数
- 能看到工具结果被模型用于最终回答

---

## 学习记录模板

完成本轮后，反馈给 Codex 时可以按这个格式：

```markdown
## 本轮学习反馈

### 看了什么

### 写了什么代码

### 跑通了什么

### 遇到的问题

### 还不理解的概念

### 我自己的想法
```

Codex 后续负责：

- 整理正式 GitBook 笔记
- 查漏补缺
- 调整路线
- 制定下一段计划

---

## 本轮完成标准

本轮完成不要求做成项目，只要求：

- [ ] 看完或快速过完 Prompt Engineering 短课
- [ ] 有一份 raw 笔记
- [ ] 跑通 `hello_llm.py`
- [ ] 跑通 `structured_output.py`
- [ ] 跑通 `tool_calling_demo.py`
- [ ] 能解释 Tool Calling 的基本流程

完成后再进入下一段：代码库读取、文件工具和 CodePilot Lab v0 前置准备。

