# 流程与能力边界

## 目标流程

```text
需求 → Coordinator 拆解 → Worker A/B 隔离开发
     → Coordinator 集成候选 → QA → Reviewer
     → AWAITING_APPROVAL → 人工批准后合并
```

每个阶段都应留下可定位的状态、输入、输出、退出码和下一动作。候选代码、测试输入或目标分支发生变化时，受影响的 QA、Review 和批准自动失效。

## 角色职责

| 角色 | 负责内容 | 不应拥有的权限 |
|---|---|---|
| Coordinator | 需求拆解、依赖、文件归属、候选集成和交接 | 不批准自己的结果，不改写业务口径 |
| Worker | 在隔离工作区完成分配的实现并提交 | 不修改其他 Worker、正式分支或未授权数据 |
| QA | 从冻结候选执行适用验证并保留原始结果 | 不修复被测代码，不降低验收门槛 |
| Reviewer | 独立检查需求、差异、风险和证据 | 不替代 QA，不替代最终批准人 |
| 人工批准人 | 批准、退回或拒绝精确候选 | 不批准未绑定完整 SHA 的对象 |

## 状态与证据

建议状态为 `RECEIVED`、`DECOMPOSED`、`DISPATCHED`、`RUNNING`、`INTEGRATING`、`QA`、`REVIEWING`、`AWAITING_APPROVAL` 和 `MERGED`；异常进入 `FAILED`、`BLOCKED` 或 `CANCELLED`。

最小证据包括：任务范围、明确不做项、基线 SHA、允许修改路径、Worker 提交 SHA、集成候选 SHA、精确命令、真实退出码、验证环境、Reviewer 结论和人工批准对象。摘要不能替代原始输出。

## 能力边界

这套材料提供流程约定和可复用模板，不提供编排服务、状态数据库、权限沙箱、审批系统或发布系统。是否具备自动派发、恢复、预算、权限隔离和外部写入能力，必须依据实际 Orca/Codex 环境单独验证；未验证的能力只能标为待核实或 BLOCKED。

公开发布不包含业务数据、机会库页面、飞书同步、售后数据、凭证、内部资源实际值、dispatch capability 或本机原始证据。
