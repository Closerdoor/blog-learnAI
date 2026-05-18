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

### 4. AI Agent 全栈学习课程 (Callous-0923/agent-study)

- **来源**: [GitHub](https://github.com/Callous-0923/agent-study)
- **特点**: 36 章 Agent 全栈课程，覆盖 ReAct、Tool Calling、LangGraph、RAG、MCP、A2A、上下文工程、Agent 安全、可观测性等主题
- **内容形态**: 每章是 `.py` 文件，形式为“讲义 + 可运行概念演示”
- **适用**: 建立 Agent 知识地图、理解术语和架构分类、面试查漏补缺
- **风险**: 仓库很新，覆盖面很宽，部分章节大量使用模拟代码，不适合作为主线教材从头刷到尾
- **推荐学习方式**: 作为二线参考资料，只挑重点章节阅读
- **优先章节**:
  - `Ch1` - 第一个 Agent，理解 ReAct 循环和 Function Calling 基础
  - `Ch4` - LangChain / LangGraph 框架概览
  - `Ch9` - RAG 技术演进：Naive RAG、Advanced RAG、GraphRAG、Agentic RAG
  - `Ch11` - Tool Calling 底层机制
  - `Ch18` - Agent 安全与护栏
  - `Ch19` - Agentic Workflow 设计模式
  - `Ch20` - Context Engineering
  - `Ch24` - Agent 可观测性

---

## 快速上手实践资源

### 5. Generative AI for Beginners (Microsoft) ⭐推荐

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

### 6. LLM Cookbook (Datawhale) ⭐推荐

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

### 7. Neural Networks: Zero to Hero (Karpathy)

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

## 资料类型分类

> 目标：优先选择能动手产出项目的资料，纯理论资料只作为路线判断和查漏补缺。

### A. 手把手实操 / 可运行项目优先

| 资料 | 类型 | 推荐程度 | 使用方式 |
|------|------|----------|----------|
| Generative AI for Beginners | 系统课程 + 代码示例 | ⭐⭐⭐ | 挑 Lesson 04-07、11、15、17，跟着跑示例 |
| LLM Cookbook | Notebook 实操课程 | ⭐⭐⭐ | 用中文材料快速补 Prompt、API、RAG 基础 |
| DeepLearning.ai Prompt Engineering for Developers | 短课 + 练习 | ⭐⭐⭐ | 用 2 小时建立 Prompt 基础 |
| DeepLearning.ai Building Systems with the ChatGPT API | 短课 + 系统设计练习 | ⭐⭐⭐ | 学会把多个 LLM 调用组合成应用流程 |
| Vercel AI SDK | 官方文档 + 示例项目 | ⭐⭐⭐ | 对接你的前端优势，重点看 `streamText`、`useChat`、Tool Calling |
| LangGraph 官方文档和示例 | 官方教程 + 可运行示例 | ⭐⭐⭐ | Agent 阶段主线资料，重点学状态、节点、边、持久化 |
| LlamaIndex 官方文档 | 官方教程 + RAG 示例 | ⭐⭐ | RAG 阶段用于构建资料馆助手原型 |
| Callous-0923/agent-study | 讲义 + 可运行概念演示 | ⭐⭐ | 只挑 Ch1、Ch4、Ch9、Ch11、Ch19、Ch20 辅助理解 |

### B. 理论 / 路线 / 查漏补缺资料

| 资料 | 类型 | 推荐程度 | 使用方式 |
|------|------|----------|----------|
| 零基础学 AI | 基础路线和概念 | ⭐⭐ | 快速扫读，不作为主线 |
| Harness 工程指南 | Agent 工程理论 | ⭐⭐ | 中后期理解 Agent 平台、MCP、运行时 |
| AIGC-Interview-Book | 面试百科 / 查漏字典 | ⭐⭐ | 遇到概念不懂时查，不从头读 |
| Neural Networks: Zero to Hero | 底层原理课程 | ⭐ | 当前先放后面，除非决定深入模型原理 |
| Dify 源码 | 产品/平台研究 | ⭐⭐ | 有项目经验后再研究工作流封装 |
| OpenClaw 源码 | 自驱 Agent 系统研究 | ⭐ | 当前只观察，不进入主线 |

### C. 当前主线选择原则

- **先项目，后百科**：优先选择能跑出代码、能沉淀笔记、能服务你的 Treasure / 五子棋项目的资料。
- **官方资料优先**：框架变化快，LangGraph、Vercel AI SDK、OpenAI/Anthropic API 以官方文档为准。
- **理论只回答问题**：当实操中遇到“为什么 Agent 要有状态”“为什么 RAG 检索不准”“为什么 Tool Calling 会乱调工具”时，再回到理论资料查。
- **不按大而全资料顺序刷**：AIGC-Interview-Book、agent-study 都属于地图型资料，适合抽查，不适合连续刷。

---

*最后更新: 2026年5月*
