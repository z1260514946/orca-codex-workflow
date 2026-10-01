# 最小任务示例（说明性案例）

下面的案例只演示流程，不调用外部服务，也不包含业务数据；它不是本仓库已实际执行的任务记录。

```text
需求定义
    ↓
Coordinator 创建 Task
    ↓
Worker 执行
    ↓
Reviewer 检查
    ↓
Human 合并
```

## 1. 需求定义

将 README 中的一段边界说明改得更清楚，并明确不修改代码、数据和配置行为。

## 2. Coordinator 创建 Task

Coordinator 填写任务卡，记录目标、允许修改文件、保护路径、验收标准和人工决定点，并为 Worker 指定独立工作区。

## 3. Worker 执行

Worker 只修改分配的 Markdown 文件，检查 Markdown 结构和相对链接，创建本地提交，并报告完整 SHA、文件清单和真实退出码。

## 4. Reviewer 检查

Reviewer 独立阅读需求、差异和验证结果，确认没有超范围修改、敏感信息或未经证实的能力声明，并给出 `PASS`、`BLOCKED` 或退回结论。

## 5. Human 合并

Human 核对精确候选 SHA、Reviewer 结论和变更范围后，决定是否合并。Agent 不替代该决定。
