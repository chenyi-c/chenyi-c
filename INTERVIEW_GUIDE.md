# 项目面试指南

_用事实、测试和失败复盘讲清四个项目，避免堆砌技术名词。_

---

## 🎯 30 秒自我介绍

我主要做 AI 应用后端和 Agent 工程。IssuePilot 证明我能把状态图、只读工具、checkpoint、证据引用和人工批准组成可审计 Agent；Log AI Assistant 证明我能完成 Python 异常检测、稳定事件 ID、脱敏研判与回归验证；Campus 的个人分支补充结构化模型输出、规则风险下限和故障降级。AgentDeck 与 Building Energy 用于补充本地任务闭环和公开数据治理能力。

## 🔍 三个主项目故事

### IssuePilot：没有证据时不能批准

- 问题：模型可能给出听起来合理、但没有工具证据支持的调查结论
- 设计：五类 GitHub 工具全部只读，每条 observation 保存来源 URL、工具名和有界预览；质量策略把无证据结果标为不可批准
- 状态：LangGraph 在人工审批节点暂停，SQLite checkpoint 支持重启后继续
- 边界：只输出草案和 argv 验证计划，不执行命令、不自动发评论

### Log AI Assistant：Windows 锁并不跨进程

- 现象：所谓 Windows file-lock 实际使用进程内 `threading.Lock`
- 风险：两个 scheduler 进程能同时执行相同幂等键
- 修复：先用两个子进程复现，再改为 `msvcrt.locking` 固定字节锁；POSIX 继续使用 `fcntl`
- 防复发：竞争、异常释放与 Linux/Windows Mypy 都进入验证

### Campus Resale：模型输出可能掩盖规则风险

- 现象：模型建议和规则建议需要合并，但模型可能给出更低风险等级
- 风险：高风险商品因模型结果被降级
- 修复：规则风险成为不可降低的 floor；模型失败只返回稳定原因码，前端不展示异常原文
- 防复发：Java service/client 测试和前端真实组件断言

### Building Energy：离线证据与数据库可能不一致

- 现象：源时间是美国东部本地时间，却被直接追加 `Z`；数据库列又只保留两位小数
- 风险：时间窗口发生偏移，数据库与 CSV 的总量和异常结果不同
- 修复：使用 `America/New_York` 规范化到 UTC，采用四位小数，并补旧 volume 幂等迁移
- 防复发：时区、DST、重复时间戳、NaN/Inf 和 CSV/DB parity 测试

## 💬 高频问题

| 问题 | 回答重点 |
| --- | --- |
| IssuePilot 为什么算 Agent？ | 有显式状态图、真实只读工具、持久 checkpoint、证据约束和人工批准；不是一次性 prompt 包装 |
| 为什么不让它自动修复？ | 项目验证的是可审计调查；命令执行和发布属于高风险动作，当前只生成证据关联的 argv 计划 |
| 为什么 SSE 要先订阅再 replay？ | 避免完成事件发生在订阅之前造成丢失，并用序号去重 |
| 如何证明任务结果可审计？ | JSONL 事件、Git Diff、Review、人工验收和运行摘要共同形成证据链 |
| 为什么日志助手不是“让 AI 自己判断”？ | 规则和工具证据可重放；模型只在候选范围内补充，不覆盖确定性事实 |
| 幂等怎么保证？ | 数据库成功记录检查加跨进程文件锁；Windows 与 POSIX 分别验证 |
| 如何避免演示数据泄密？ | 白名单字段、用户/IP 脱敏、golden evidence 回归、容器内同样校验 |
| Campus 的个人贡献是什么？ | 个人 Draft PR 中的 Python/FastAPI 发布辅助服务、结构化校验、规则风险 floor 和固定 mock 回放；不声称主导 Java 平台 |
| Energy 为什么不能说准确率？ | BDG2 子集没有故障标签，只能报告覆盖、缺失和规则阈值结果 |
| Docker 与本地结果不一致怎么办？ | 把 Docker 设为官方路径；本地 fallback 单独报告，不混为同一证据 |
| 为什么把 AgentDeck 和 Energy 放到补充项目？ | 三个主项目已经分别覆盖 Agent、异常检测和 LLM 故障降级；继续平铺会削弱求职主线 |

## 📋 演示降级顺序

1. Live：运行真实项目和接口
2. Replay：使用固定输入、结构化 JSON/Markdown 和 stub-backed 浏览器流程
3. Static：展示截图、CI、PR 和架构/失败复盘

任何一级失败都切换到下一级，不在面试现场临时安装大依赖、修改端口或暴露 API Key。
