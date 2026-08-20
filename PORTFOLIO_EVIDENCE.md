# 项目贡献与证据表

_用于简历、作品集与面试中的可验证项目表述。_

---

## 📊 证据矩阵

| 项目 | 个人贡献重点 | 已验证证据 | 不应声称 |
| --- | --- | --- | --- |
| IssuePilot | LangGraph 调查图、只读 GitHub 工具、SQLite checkpoint、证据约束、人工批准与审计导出 | 后端 51 项测试；前端 2 项测试与构建；Docker Compose 构建；[CI run](https://github.com/chenyi-c/issuepilot/actions/runs/31621057740) | 自动修复、命令执行、自动发布、生产准确率 |
| Log AI Assistant | 调查支持模块、ClickHouse helper 边界、脱敏证据、Windows 跨进程锁、质量门禁 | Docker 后端/前端 CI；JSON/Markdown golden evidence；[PR #3](https://github.com/chenyi-c/log-ai-assistant/pull/3) | 模型自主决策、零漏洞、完整生产部署 |
| Campus Resale AI Assist | 个人 Draft PR 中的 Python/FastAPI 服务、结构化输出校验、规则风险下限、故障回退与脱敏评测 | 18 项 Python 测试；40 条固定脱敏样例；[Draft PR #2](https://github.com/chenyi-c/campus-resale/pull/2) | 整个平台个人所有、Java 主导开发、自动审核或真实市场效果 |
| AgentDeck | 任务运行闭环、人工验收、运行摘要、浏览器证据与 CI | 143 个单元测试；7 个浏览器流程；[PR #4](https://github.com/chenyi-c/agentdeck/pull/4) CI 通过 | 云端、多用户、任意 Agent 编排、数据库运行时 |
| Building Energy MVP | BDG2 数据准备、来源校验、时区规范化、缺失分析、数据库迁移 | 2,184 小时候选、2,180 行联结、99.82% 联结率、27 个测试；[PR #2](https://github.com/chenyi-c/building-energy-ai-mvp/pull/2) | LLM/RAG/MCP、故障分类准确率、节能效果 |

## 🔗 主项目代码证据

### IssuePilot

- [V4 CI](https://github.com/chenyi-c/issuepilot/actions/runs/31621057740)
- [固定评测 JSON](https://github.com/chenyi-c/issuepilot/blob/main/docs/evidence/investigation-evaluation.json)
- [真实浏览器截图](https://github.com/chenyi-c/issuepilot/blob/main/docs/assets/issuepilot-v4.png)

### AgentDeck（补充）

- [人工验收与运行摘要 PR](https://github.com/chenyi-c/agentdeck/pull/4)
- [真实渲染截图](https://github.com/chenyi-c/agentdeck/blob/master/docs/assets/agentdeck-acceptance-summary.png)
- [CI workflow](https://github.com/chenyi-c/agentdeck/blob/master/.github/workflows/ci.yml)

### Log AI Assistant

- [调查证据 Markdown](https://github.com/chenyi-c/log-ai-assistant/blob/main/docs/evidence/interview-investigation-demo.md)
- [调查证据 JSON](https://github.com/chenyi-c/log-ai-assistant/blob/main/docs/evidence/interview-investigation-demo.json)
- [质量审计](https://github.com/chenyi-c/log-ai-assistant/blob/main/docs/12_engineering_quality_audit.md)

## ✅ 简历可用表述

- IssuePilot：实现带 SQLite checkpoint 的 LangGraph 调查流程，将只读工具结果组织为可引用证据，并在人工批准点暂停；不执行建议命令或自动发布
- Log AI Assistant：构建规则优先、证据驱动的日志调查链路，补齐脱敏回放、跨进程幂等与 Docker CI
- Campus Resale：在课程团队系统的个人分支中独立补充 Python/FastAPI 发布辅助服务，以 Pydantic、规则风险下限和固定 mock 回放验证故障降级
- AgentDeck：实现本地 Agent 任务的运行、Review、人工验收与摘要闭环，并用单元测试和浏览器流程验证
- Building Energy MVP：将人工样例替换为 BDG2 公开数据子集，显式处理来源、时区、缺失值、精度和旧数据库迁移
