# Worker 完成报告

适用于执行 Worker、资料研究 Worker 和独立 QA 等岗位。以下是回传内容模板，不是 Orca API 参数；正式回执须使用当前版本支持的入口与生命周期枚举。

```yaml
lifecycle_outcome: "<当前官方接口支持的生命周期 outcome>"
quality_status: "<PASS | FAIL | BLOCKED | UNVERIFIED>"
actual_agent_and_tools: "<实际 Agent、岗位与可核实工具版本>"
model:
  provider: "<可核实值或 UNVERIFIED>"
  name: "<可核实值或 UNVERIFIED>"
  effort: "<可核实值或 UNVERIFIED>"
task_dispatch_receipt: "<Task / Dispatch / 正式回执引用>"
input_versions: "<基线 SHA、必要输入文件版本和实际读取的 SHA-256>"
delivery_version: "<固定候选 SHA 或只读交付版本>"
modified_files: ["<实际修改文件；只读任务填无>"]
tests_and_exit_codes: ["<实际命令、真实退出码、执行时间；未执行如实标记>"]
evidence_locations: ["<原始输出、实际读取证据和核验结果位置>"]
unresolved_items: ["<未解决事项、风险和下一依赖>"]
human_judgment_needed: "<是或否；需要判断的具体范围>"
```

`worker_done` 仅表示生命周期结算，不能代替独立质量判断。`PASS`、`FAIL`、`BLOCKED`、`UNVERIFIED` 属于 `quality_status`，不得直接填入不支持这些值的生命周期参数。Worker 自测不是独立 QA，Worker 提交也不能直接称为集成候选。

无法核实的模型或强度写 `UNVERIFIED`，不得从工具名称、任务标题或历史配置推断。只读任务不强制创建提交；模型、文件内容与哈希都须以实际读取证据为准。公开模板只保留占位值，不发布真实运行标识和内部证据。
