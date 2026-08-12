# 陈盛漳｜AI 应用后端与 Agent 工程

_面向 AI 应用后端、Agent 工程实习；关注可追溯执行、确定性回退、证据链、数据质量与可复现交付。_

---

## 🎯 两个主项目

### AgentDeck

本地优先的 Codex 任务控制台，覆盖项目注册、任务运行、结构化事件、Git Diff Review、隔离 worktree、人工验收与运行摘要。项目刻意保持 local-only，不包装为云端多用户平台。

- [项目仓库](https://github.com/chenyi-c/agentdeck)
- [收口 PR 与完整 CI](https://github.com/chenyi-c/agentdeck/pull/4)
- [90 秒演示脚本](https://github.com/chenyi-c/agentdeck/blob/master/docs/demo/90-second-demo.md)
- 验证：143 个 Vitest 测试、7 个 Playwright 流程、lint/build/CI 通过

### Log AI Assistant

面向日志异常调查的 AI 应用后端：保留确定性规则和工具证据，以 ClickHouse 数据、异常事件、调查证据链、脱敏回放及人工反馈支撑判断，而不是让模型自由生成结论。

- [项目仓库](https://github.com/chenyi-c/log-ai-assistant)
- [质量收口 PR 与 Docker CI](https://github.com/chenyi-c/log-ai-assistant/pull/3)
- [结构化调查证据](https://github.com/chenyi-c/log-ai-assistant/blob/main/docs/evidence/interview-investigation-demo.md)
- 验证：Python/React/Docker CI 通过，提交的 JSON 与 Markdown 证据由回归测试校验

## 📊 项目证据

| 项目 | 主要证明 | 验证入口 |
| --- | --- | --- |
| [AgentDeck](https://github.com/chenyi-c/agentdeck) | Agent 生命周期、SSE、worktree 隔离、人工验收 | [PR #4](https://github.com/chenyi-c/agentdeck/pull/4) |
| [Log AI Assistant](https://github.com/chenyi-c/log-ai-assistant) | AI 应用后端、证据链、数据质量、跨进程幂等 | [PR #3](https://github.com/chenyi-c/log-ai-assistant/pull/3) |
| [Campus Resale](https://github.com/chenyi-c/campus-resale) | 团队项目中的 Java AI 集成、规则风险下限 | [PR #3](https://github.com/chenyi-c/campus-resale/pull/3) |
| [Building Energy MVP](https://github.com/chenyi-c/building-energy-ai-mvp) | 公开数据加工、时区/缺失分析、可解释评测 | [PR #2](https://github.com/chenyi-c/building-energy-ai-mvp/pull/2) |

完整的个人贡献边界、数字和非声明项见 [项目证据表](PORTFOLIO_EVIDENCE.md)。面试叙事和常见问题见 [面试指南](INTERVIEW_GUIDE.md)。

## 🔐 表达边界

- 不把规则系统描述成 LLM、RAG 或 MCP
- 不把无标签异常评测描述成准确率
- 不把团队项目全部成果归为个人所有
- 不用未验证的性能提升、模型效果或线上部署数字
