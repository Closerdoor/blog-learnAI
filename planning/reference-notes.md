# 参考笔记收集

> 收集各类开源学习路线和他人AI学习笔记，作为参考

---

## 学习路线参考

### 1. 零基础学 AI (yeasy)

- **来源**: [GitBook](https://yeasy.gitbook.io/ai_beginner_guide)
- **特点**: 双轨制学习路线（基础使用者轨 + 工程师增强轨）
- **适用**: 完全零基础、文科生、职场人士
- **重点章节**:
  - 第1-3章：AI基本概念、大模型原理
  - 第10-13章：工具使用、提示词工程、实战场景
- **推荐学习方式**: 快速扫读第1-2章，重点学习第10-13章

### 2. Harness 工程指南 (yeasy)

- **来源**: [GitBook](https://yeasy.gitbook.io/harness_engineering_guide)
- **特点**: 深入 Agent 工程基础设施，以 Codex/Claude Code/OpenClaw 为参考系统
- **适用**: Agent 平台工程师、应用架构师
- **重点内容**:
  - 运行时引擎、工具层、记忆子系统
  - 任务编排与工作流引擎
  - MCP 协议集成
- **推荐学习方式**: 作为进阶读物，在掌握基础后再深入

### 3. AIGC-Interview-Book (WeThinkIn)

- **来源**: [GitHub](https://github.com/WeThinkIn/AIGC-Interview-Book)
- **特点**: 算法工程师面试准备，内容全面
- **使用方式**: 作为查漏补缺字典，不从头阅读
- **重点章节**:
  - `AI Agent基础` - Agent 架构、ReAct 框架、Tool Calling
  - `大模型基础` - Token、Temperature、Context Window
  - `模型部署基础` - 量化、端侧推理

---

## 快速上手实践资源

### 4. Generative AI for Beginners (Microsoft) ⭐推荐

- **来源**: [GitHub](https://github.com/microsoft/generative-ai-for-beginners) | 111k stars
- **特点**: 21课，Python + TypeScript 双语言示例
- **适用**: 想要快速上手构建 AI 应用的开发者
- **推荐学习路径**:
  | 顺序 | 课程 | 主题 | 优先级 |
  |------|------|------|--------|
  | 1 | Lesson 04 | Prompt Engineering 基础 | ⭐⭐⭐ |
  | 2 | Lesson 05 | 高级 Prompt 技巧 | ⭐⭐⭐ |
  | 3 | Lesson 06 | 文本生成应用 | ⭐⭐⭐ |
  | 4 | Lesson 07 | 聊天应用 | ⭐⭐⭐ |
  | 5 | Lesson 11 | Function Calling | ⭐⭐⭐ |
  | 6 | Lesson 15 | RAG 与向量数据库 | ⭐⭐ |
  | 7 | Lesson 17 | AI Agents | ⭐⭐ |

### 5. LLM Cookbook (Datawhale) ⭐推荐

- **来源**: [GitHub](https://github.com/datawhalechina/llm-cookbook) | 24k stars
- **特点**: 吴恩达大模型系列课程中文版
- **适用**: 中文学习者，有完整 Notebook 可运行
- **必修课程**:
  1. 面向开发者的 Prompt Engineering
  2. 搭建基于 ChatGPT 的问答系统
  3. 使用 LangChain 开发应用程序
  4. 使用 LangChain 访问个人数据
- **选修课程**:
  - 使用 Gradio 搭建生成式 AI 应用
  - 微调大语言模型
  - 搭建和评估高级 RAG 应用

### 6. Neural Networks: Zero to Hero (Karpathy)

- **来源**: [GitHub](https://github.com/karpathy/nn-zero-to-hero) | 21.8k stars
- **特点**: 从零构建神经网络，深入底层原理
- **适用**: 想要深入理解神经网络原理的开发者
- **推荐学习方式**: 有时间再学，非紧急优先级

---

## 开源项目参考

### Agent 框架

| 项目 | 链接 | 语言 | 说明 |
|------|------|------|------|
| Vercel AI SDK | [GitHub](https://github.com/vercel/ai) | TS | 前端最强工具，useChat/streamUI |
| LangGraph | [GitHub](https://github.com/langchain-ai/langgraph) | JS/Python | 工业界 Agent 标准 |
| LangGraph.js | [GitHub](https://github.com/langchain-ai/langgraphjs) | JS | JS 版本示例 |

### 平台与工具

| 项目 | 链接 | 说明 |
|------|------|------|
| Dify | [GitHub](https://github.com/langgenius/dify) | 国产 AI 应用开发平台，研究其 Agent 工作流封装 |
| OpenClaw | [GitHub](https://github.com/openclaw/openclaw) | 自驱型 Agent 框架 |

---

## 官方文档

| 文档 | 链接 | 优先级 |
|------|------|--------|
| OpenAI API | https://platform.openai.com/docs | ⭐⭐⭐ |
| Anthropic API | https://docs.anthropic.com | ⭐⭐ |
| Vercel AI SDK | https://sdk.vercel.ai/docs | ⭐⭐⭐ |
| LlamaIndex | https://docs.llamaindex.ai | ⭐⭐ |
| LangGraph | https://langchain-ai.github.io/langgraph | ⭐⭐⭐ |

---

## 推荐课程

| 课程 | 链接 | 时长 | 优先级 |
|------|------|------|--------|
| Prompt Engineering for Developers | [DeepLearning.ai](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) | 2小时 | ⭐⭐⭐ |
| LangChain for LLM Application Development | [DeepLearning.ai](https://www.deeplearning.ai/short-courses/langchain/) | 1小时 | ⭐⭐⭐ |
| Building Systems with the ChatGPT API | [DeepLearning.ai](https://www.deeplearning.ai/short-courses/building-systems-with-chatgpt/) | 1小时 | ⭐⭐⭐ |

---

## 针对前端转型 AI 的快速路径

### 核心资源组合（约 4-6 周）

| 阶段 | 资源 | 时间 | 目标 |
|------|------|------|------|
| **第1周** | LLM Cookbook - Prompt Engineering | 1周 | 掌握 Prompt 基础，能调用 OpenAI API |
| **第2周** | Generative AI for Beginners L4-7 | 1周 | 构建聊天应用，掌握 Function Calling |
| **第3周** | LLM Cookbook - LangChain 开发 | 1周 | 使用 LangChain 构建应用 |
| **第4周** | Generative AI for Beginners L15 | 1周 | 掌握 RAG 基础 |
| **第5-6周** | Harness 工程指南 + LangGraph 实践 | 2周 | 深入 Agent 工程 |

### 利用 TS 优势

- 优先学习 **Vercel AI SDK**（TypeScript 原生）
- 使用 **LangGraph.js** 而非 Python 版本
- 前端 UI 可用 **Gradio** 或直接用 React

---

*最后更新: 2026年5月*
