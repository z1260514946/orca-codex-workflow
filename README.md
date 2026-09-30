# orca-codex-workflow

基于 Orca + Codex 的受监督多 Agent 协作流程、模板和使用说明。

本项目描述如何把一次需求推进到可审查的候选版本：由 Coordinator 拆解任务，Worker 在隔离工作区实现，QA 验证，Reviewer 独立审查，最后由人工决定是否合并。它不是独立协作平台，不提供无人监督运行，也不替代 Orca、Codex、Git 或组织审批流程。

## 内容

- [流程与能力边界](docs/workflow.md)：角色、状态、依赖、证据和人工决策点。
- [中文用户手册](用户手册.md)：准备、发起任务和交接检查。
- [任务模板](docs/templates/README.md)：Coordinator、Worker、Reviewer 模板。
- [配置示例](examples/config.example.env)：占位配置，不含凭证或内部资源实际值。
- [脱敏验证案例](examples/m2-validation-case.md)：说明如何引用历史 M2 结果而不把它当作本发布版本的通过证据。

## 发布边界

本仓库只包含流程、模板、手册和无凭证示例。机会库页面、业务数据、飞书同步、售后数据、内部 dispatch capability、本机路径和原始运行记录均不属于公开发布内容。

不设置 remote、不推送、不自动合并。后续更新沿用本仓库提交历史，并由人工审核具体提交。
