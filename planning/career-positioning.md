# 职业方向定位

> 当前结论：不走纯算法/模型训练路线，不做纯 AI 前端壳子，目标是面向企业场景的 **Full-stack AI / Agent Engineer**。

---

## 为什么不选择纯算法/模型训练

纯算法和模型训练路线需要长期积累：

- 数学基础：线性代数、概率统计、优化方法
- 深度学习理论：Transformer、训练技巧、模型压缩、分布式训练
- 工程环境：GPU、训练框架、数据管线、模型评估
- 论文和实验积累

这条路线价值很高，但不适合作为当前从 0 转型的主线。当前更现实的方向是使用已有模型和框架，解决真实业务问题。

---

## 三个 AI 工程方向的区别

### 1. AI 应用开发

核心是把 LLM 接入真实业务，做出可以使用的产品和工具。

常见场景：

- 企业知识库问答
- RAG 文档检索
- 智能客服
- 文档总结和结构化抽取
- 资料分类和推荐
- 工作流自动化
- 业务系统里的 AI 助手

核心能力：

- OpenAI / Anthropic API
- Prompt Engineering
- Structured Output
- Tool Calling
- RAG
- FastAPI / Next.js
- 数据库和文件处理
- 部署、日志、权限、成本控制

风险：

- 低端的“套 API + 聊天界面”会快速贬值。
- 真正有价值的是能做 RAG、工具调用、业务集成、评估和生产化。

定位：

> AI 应用开发是落地点，不是终点。

---

### 2. Agent 工程

核心是让 LLM 驱动的复杂任务变得可控、可恢复、可观测、可评估。

常见场景：

- 多步骤任务自动化
- 工具调用和工作流编排
- 长任务执行
- 人类审批
- 多系统集成
- 企业内部自动化 Agent
- 代码、运维、销售、客服、资料管理 Agent

核心能力：

- LangGraph / OpenAI Agents SDK
- 状态管理
- Tool Calling
- Workflow Orchestration
- Human-in-the-loop
- MCP
- 失败重试和中断恢复
- Tracing / Observability
- Agent Evals
- 权限、沙箱、安全边界

风险：

- 直接学习 Agent 理论容易变成概念堆叠。
- 没有实际应用经验时，状态、工具、记忆、工作流都很抽象。

定位：

> Agent 工程是主攻方向，但需要建立在 AI 应用开发和 RAG 实践之上。

---

### 3. AI 前端工程

核心是构建 AI 产品的交互体验。

常见场景：

- 流式输出
- AI Chat UI
- Agent 执行过程可视化
- 工具调用进度展示
- 人类审批界面
- 文档编辑器中的 AI 辅助
- 多模态交互

核心能力：

- React / Next.js
- TypeScript
- Vercel AI SDK
- SSE / WebSocket
- 状态管理
- AI 产品交互设计

风险：

- 如果只停留在 UI 层，容易被定位成“会接 AI 的前端”。

定位：

> AI 前端工程是差异化优势，不作为最终职业定位。

---

## 最终职业定位

目标定位：

> 面向 Agentic Coding 和企业自动化场景的 Full-stack AI / Agent Engineer，重点掌握 RAG、Tool Calling、Workflow、Agent 状态管理、可观测性和部署。

能力组合：

- Python AI 后端
- TypeScript / Next.js 前端
- RAG 工程
- Tool Calling
- Agent Workflow
- LangGraph / OpenAI Agents SDK
- FastAPI / API 服务化
- Evals / Observability
- 部署和工程化

一句话描述：

> 不是“会用 AI”，而是能把 AI 系统做成可靠产品。

---

## 长期聚焦方向

长期更靠拢：

> Agentic Coding / AI 软件工程工具。

重点研究：

- Claude Code / Codex / Cursor 类工具的架构模式
- Coding Agent 如何理解代码库
- Coding Agent 如何调用文件、Shell、Git、测试工具
- 如何做人类审批、权限控制、执行日志和回滚
- 如何从测试反馈中自动修复

主作品方向：

- CodePilot Lab：本地 Coding Agent Harness
- Agent Tool Platform：插件化 Agent 工具平台
- Personal Media Graph：长期兴趣产品，练 RAG / 图谱 / 推荐

---

## 路线原则

- **不走纯算法优先**：不把模型训练、论文和底层数学作为当前主线。
- **不做纯 AI 前端**：前端是优势，但必须补齐后端、RAG、Agent 和工程化。
- **不刷纯理论资料**：理论资料只在实操遇到问题时查。
- **项目驱动学习**：用真实项目串起 API、RAG、工具调用、Agent、部署和评估。
- **主攻 Agent，但从应用落地切入**：先做能用的 AI 应用，再逐步升级到可控 Agent 工作流。
- **长期靠拢 Agentic Coding**：学习内容最终尽量服务 CodePilot Lab 这类 AI 软件工程工具。
