# 陈盛漳｜AI 应用后端与 Agent 工程

_面向 AI 应用开发、Python 后端与 Agent 工程实习；关注工具调用、证据约束、故障降级、人工审批和可重复验证。_

## 主项目

### 1. [IssuePilot](https://github.com/chenyi-c/issuepilot)｜可审计 GitHub 故障调查 Agent

个人项目。使用 Python、FastAPI、LangGraph 与 SQLite checkpoint 组织有状态调查流程，只调用五类只读 GitHub 工具；所有判断保留来源链接、工具记录和证据预览，并在人工批准点暂停。

- [V4 代码与说明](https://github.com/chenyi-c/issuepilot/tree/main) · [CI](https://github.com/chenyi-c/issuepilot/actions/runs/31621057740) · [真实浏览器截图](https://github.com/chenyi-c/issuepilot/blob/main/docs/assets/issuepilot-v4.png)
- 验证：后端 51 项测试、前端 2 项测试与构建、Docker Compose 构建均通过；六个固定合成案例用于回归，不代表生产准确率
- 边界：只读调查，不执行建议命令，不自动发布 GitHub 评论，也不声称替代人工排障

### 2. [Log AI Assistant](https://github.com/chenyi-c/log-ai-assistant)｜安全日志异常检测与研判证据链

校企合作团队项目。我负责 Python 异常检测、事件建模、证据链、脱敏回放、人工复核与 FastAPI 查询；Kafka、Flink、ClickHouse、React 属于团队全链路，不写成个人独立成果。

- [质量收口 PR](https://github.com/chenyi-c/log-ai-assistant/pull/3) · [调查证据](https://github.com/chenyi-c/log-ai-assistant/blob/main/docs/evidence/interview-investigation-demo.md)
- 验证：Docker CI 覆盖稳定 anomaly_id、去重、ATT&CK 窄范围映射、脱敏证据和复核状态

### 3. [Campus Resale AI Assist](https://github.com/chenyi-c/campus-resale/pull/2)｜Python 商品发布辅助服务

课程团队项目中的个人功能分支。我独立补充 Python/FastAPI 服务，使用 Pydantic 校验 OpenAI-compatible 输出；无密钥、超时、网络失败或非法 JSON 时回退本地规则，高风险规则不能被模型降低。

- [Python 服务 Draft PR](https://github.com/chenyi-c/campus-resale/pull/2) · [功能分支](https://github.com/chenyi-c/campus-resale/tree/codex/python-ai-assist-service)
- 验证：18 项 Python 测试与 40 条固定脱敏样例覆盖正常商品、高风险词和模型故障；Spring Boot 仅是课程系统兼容层

## 补充项目

| 项目 | 证明点 | 证据 |
| --- | --- | --- |
| [AgentDeck](https://github.com/chenyi-c/agentdeck) | 本地任务生命周期、SSE、worktree 隔离、人工验收 | [PR #4](https://github.com/chenyi-c/agentdeck/pull/4) |
| [Building Energy MVP](https://github.com/chenyi-c/building-energy-ai-mvp) | BDG2 公开数据子集、来源/时区/缺失处理、工具证据 | [PR #2](https://github.com/chenyi-c/building-energy-ai-mvp/pull/2) |

完整口径见 [项目证据表](PORTFOLIO_EVIDENCE.md)，面试讲解见 [面试指南](INTERVIEW_GUIDE.md)。

## 开源参考与边界

- IssuePilot 直接使用 MIT 许可的 [LangGraph](https://github.com/langchain-ai/langgraph)；参考 MIT 许可的 [mini-SWE-agent](https://github.com/SWE-agent/mini-swe-agent) 的精简轨迹思路，未复制其源码
- 日志项目参考 MIT 许可的 [Presidio](https://github.com/microsoft/presidio) 脱敏思路；具体复用边界记录在各仓库 `THIRD_PARTY_NOTICES.md`
- 不把固定样例通过数表述为模型准确率，不虚构线上用户、业务收益、生产性能或团队项目所有权
