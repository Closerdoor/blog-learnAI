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

1. [hello-agents](https://github.com/datawhalechina/hello-agents)
   - Datawhale 的中文 Agent 系统教程，作为本轮 Agent 入门主线资料。
   - 本轮只看和基础能力相关的章节，不从头刷完整仓库。
   - 优先阅读：
     - 第 1 章：智能体的基本概念
     - 第 3 章：智能体的基础模块
     - 第 4 章：智能体的经典范式，重点理解 ReAct、Plan-and-Solve、Reflection
     - 第 7 章：从 0 开始构建智能体框架，作为 CodePilot Lab 的架构启发

2. [OpenAI API Docs](https://platform.openai.com/docs)
   - OpenAI 官方文档，作为 API 调用、结构化输出和工具调用的一手参考。
   - 本轮重点看：模型调用、Structured Outputs、Function Calling / Tools。

3. [ChatGPT Prompt Engineering for Developers](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/)
   - DeepLearning.ai 短课，作为 Prompt Engineering 补充资料。
   - 如果时间有限，可以先看 hello-agents 和 OpenAI API Docs，再回来看这个短课。
   - 目标：理解如何写清晰指令、提供上下文、指定输出格式、做总结/分类/抽取/转换。

4. [OpenAI Cookbook](https://github.com/openai/openai-cookbook)
   - OpenAI 官方示例仓库。
   - 不需要从头读，只查本轮相关示例：Structured Output、Tool Calling、JSON 输出、Embeddings 后续再看。

5. [Generative AI for Beginners](https://github.com/microsoft/generative-ai-for-beginners)
   - Microsoft 开源课程，Python + TypeScript 示例。
   - 本轮可选章节：
     - Lesson 04：Prompt Engineering Fundamentals
     - Lesson 05：Advanced Prompts
     - Lesson 11：Function Calling
   - 时间不够可以先跳过，作为补充资料。

6. [LLM Cookbook](https://github.com/datawhalechina/llm-cookbook)
   - Datawhale 中文 Notebook 课程。
   - 本轮可选：只看 Prompt Engineering 和 API 调用相关章节，用来补中文解释。

暂时不看：

- LangGraph
- MCP
- CrewAI / AutoGen
- AIGC-Interview-Book
- agent-study
- Claude Code 架构分析

说明：

- hello-agents 现在作为 Agent 入门中文主线资料。
- OpenAI API Docs 仍然是模型调用、结构化输出和工具调用的一手参考。
- 不要因为 hello-agents 内容丰富就把全部章节一次刷完，本轮只服务“AI 应用基础 + Agent 前置能力”。

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
