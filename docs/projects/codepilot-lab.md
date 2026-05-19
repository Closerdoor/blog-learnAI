# CodePilot Lab

> 主线求职作品：一个面向代码库任务的本地 Coding Agent Harness。

---

## 项目目标

研究并实现 Claude Code / Codex / Cursor 类 Coding Agent 的核心工作流：

```text
理解任务 → 读取代码 → 制定计划 → 修改文件 → 运行测试 → 继续修复 → 生成 diff → 人工确认
```

## 为什么做这个项目

这个项目对齐长期方向：

- Agentic Coding
- AI 软件工程工具
- Developer Tools
- Tool Calling
- Agent Workflow
- Test Runner Feedback Loop

它比普通聊天机器人或个人知识库更接近未来软件开发工具链，也更适合作为求职主作品。

## 版本规划

### v0：代码库读取 + 修改建议

- 扫描项目目录
- 读取指定文件
- 根据任务生成修改计划
- 输出建议，不实际写文件

### v1：文件修改 + Diff

- 支持受控文件修改
- 生成 Git diff
- 用户确认后保留修改

### v2：运行测试 + 自动修复

- 调用测试命令
- 读取失败信息
- 让 Agent 继续修复

### v3：LangGraph 状态流

- 将 plan / edit / test / fix / review 拆成节点
- 支持 checkpoint
- 支持中断恢复

### v4：权限控制 + Trace

- 工具权限分级
- 高风险操作人工确认
- 记录完整执行轨迹
- 形成可展示的任务报告

## 核心模块

- Codebase Scanner
- Context Builder
- Tool Registry
- File Tools
- Shell Tool
- Git Diff Tool
- Test Runner
- Planning Agent
- Review / Approval
- Trace Log

## 学习路径关联

- 阶段 1：Structured Output 和基础 Tool Calling
- 阶段 2：代码库理解和 RAG / Memory
- 阶段 3：Tool Registry 和权限控制
- 阶段 4：LangGraph Agent Workflow
- 阶段 5：Trace、评估、安全和部署

