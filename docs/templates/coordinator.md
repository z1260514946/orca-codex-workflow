# Coordinator 任务卡

岗位与责任以[流程说明](../workflow.md)为准。按实际交付类型选择岗位，QA、Reviewer 等仅在适用时启用。以下是派单内容模板，不是可直接提交的 Orca API 参数。

```yaml
goal: "<目标>"
non_goals: ["<明确不做项>"]
role: "<本次承担的逻辑岗位>"
rules_version: "<规则入口、协作说明及版本>"
required_reading: ["<必读章节和可读资料位置>"]
effective_state: "<当前有效结论、来源和适用范围>"
input_baseline:
  git_sha: "<完整输入 SHA>"
  files: ["<必要输入文件及版本；未提交文件附 SHA-256 和可读内容>"]
  uncommitted_diff: "<明确列出或 clean>"
allowed_changes:
  paths: ["<允许修改路径；只读任务填无>"]
  protected: ["<受保护路径或字段>"]
  permissions: "<读写、外部访问和批准边界>"
  budget: "<时间、重试、用量或费用上限>"
completion_and_evidence:
  criteria: ["<完成条件及各自对应的证据位置>"]
  checks: ["<适用核验及独立性要求>"]
failure_block_escalation_recovery:
  failure: "<失败和停止条件>"
  blocked: "<阻断证据及保持状态>"
  escalation: "<升级对象、原因和人工决定点>"
  recovery: "<现有检查点、恢复条件和失效条件>"
formal_return: "<按 Worker 正式回传模板填写并走官方回执入口>"
```

回传字段见[Worker 完成报告](worker.md)。模板和公开示例只使用占位值，不包含实际运行标识、内部证据或凭证。
