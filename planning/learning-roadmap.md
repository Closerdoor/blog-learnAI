# 学习路线规划

> 本文档记录我的AI学习路线讨论与决策过程

---

## 当前状态

- **背景**: 前端工程师，熟悉 TypeScript/JavaScript
- **目标**: 快速转型 AI 应用开发（Agent 方向）
- **时间**: 2026年5月开始
- **策略**: 快速上手实践，利用 TS 优势，缩短学习周期

---

## 学习路线（已确定）

### 第一阶段：Prompt Engineering 与 API 基础（第1周）

**目标**: 掌握 Prompt 基础，能调用 OpenAI API

**学习资源**:
- [x] LLM Cookbook - 面向开发者的 Prompt Engineering
- [x] DeepLearning.ai - Prompt Engineering for Developers（2小时）

**实操任务**:
- [ ] 配置开发环境，安装 OpenAI SDK
- [ ] 实现第一个 Function Calling（天气查询示例）
- [ ] 完成 Prompt 基础练习（总结、推断、转换）

**笔记文件**: `docs/part1/prompt-engineering.md`

---

### 第二阶段：应用开发与 Function Calling（第2周）

**目标**: 构建聊天应用，掌握 Function Calling

**学习资源**:
- [ ] Generative AI for Beginners - Lesson 04-07
- [ ] LLM Cookbook - 搭建基于 ChatGPT 的问答系统

**实操任务**:
- [ ] 构建一个简单的聊天应用
- [ ] 实现 Function Calling 集成外部工具
- [ ] 使用 Vercel AI SDK 的 useChat hook

**笔记文件**: `docs/part1/vercel-ai-sdk.md`

---

### 第三阶段：LangChain 应用开发（第3周）

**目标**: 使用 LangChain 构建完整应用

**学习资源**:
- [ ] LLM Cookbook - 使用 LangChain 开发应用程序
- [ ] LLM Cookbook - 使用 LangChain 访问个人数据

**实操任务**:
- [ ] 使用 LangChain 构建链式调用
- [ ] 实现记忆功能（ConversationBufferMemory）
- [ ] 构建一个能访问个人数据的应用

**笔记文件**: `docs/part2/llamaindex.md`

---

### 第四阶段：RAG 与知识库（第4周）

**目标**: 掌握 RAG 基础，构建知识库应用

**学习资源**:
- [ ] Generative AI for Beginners - Lesson 15 (RAG)
- [ ] LLM Cookbook - 搭建和评估高级 RAG 应用

**实操任务**:
- [ ] 理解 Embedding 和向量数据库
- [ ] 构建一个简单的 RAG 应用
- [ ] 实现文档检索和问答

**笔记文件**: `docs/part2/vector-database.md`

---

### 第五阶段：Agent 开发（第5-6周）

**目标**: 深入 Agent 工程，构建可控 Agent

**学习资源**:
- [ ] Generative AI for Beginners - Lesson 17 (AI Agents)
- [ ] Harness 工程指南 - 第1-7章
- [ ] LangGraph 官方文档和示例

**实操任务**:
- [ ] 理解 Agent 架构（Node、Edge、State）
- [ ] 使用 LangGraph.js 构建简单 Agent
- [ ] 实现工具调用和状态管理
- [ ] 构建五子棋解说 Agent（实战项目）

**笔记文件**: `docs/part3/langgraph-basics.md`

---

## 实战项目规划

### 项目1：资料馆智能助手（第3-4周）

- **技术栈**: LangChain + RAG
- **功能**: 语义搜索、自动分类、智能推荐
- **笔记文件**: `docs/projects/treasure-assistant.md`

### 项目2：五子棋解说 Agent（第5-6周）

- **技术栈**: LangGraph + Tool Calling
- **功能**: 分析棋局、实时解说、胜率预测
- **笔记文件**: `docs/projects/gomoku-commentator.md`

---

## 学习进度追踪

| 阶段 | 状态 | 开始时间 | 完成时间 |
|------|------|----------|----------|
| 第一阶段：Prompt Engineering | 待开始 | - | - |
| 第二阶段：应用开发 | 待开始 | - | - |
| 第三阶段：LangChain | 待开始 | - | - |
| 第四阶段：RAG | 待开始 | - | - |
| 第五阶段：Agent | 待开始 | - | - |

---

## 讨论记录

### 2026年5月13日

- 确定学习路线：快速上手实践，利用 TS 优势
- 学习周期：从24周压缩到4-6周
- 核心资源：LLM Cookbook + Generative AI for Beginners + Harness 工程指南
- 优先使用 TypeScript 工具：Vercel AI SDK、LangGraph.js

---

*最后更新: 2026年5月13日*
