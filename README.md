# orca-codex-workflow

基于 Orca + Codex 的受监督多 Agent 协作流程、模板和使用说明。

本项目描述如何把一次需求推进到可审查的候选版本：由 Coordinator 拆解任务，Worker 在隔离工作区实现，QA 验证，Reviewer 独立审查，最后由人工决定是否合并。它不是独立协作平台，不提供无人监督运行，也不替代 Orca、Codex、Git 或组织审批流程。

## 非目标

- 不是 Agent Runtime 或 Agent 平台。
- 不是自动驾驶研发系统。
- 不是无人监督的生产平台。
- 不负责保存凭证、企业内部数据或业务数据。

## 快速开始

1. 阅读[流程与能力边界](docs/workflow.md)和[能力边界说明](docs/capability-boundary.md)。
2. 从[Coordinator 任务卡](docs/templates/coordinator.md)开始，明确需求、范围、保护边界和验收标准。
3. 按[中文用户手册](用户手册.md)完成 Worker、QA、Reviewer 和人工审批交接。
4. 根据实际 Orca/Codex 环境填写本机配置；公开仓库只保留[配置示例](examples/config.example.env)。示例中的 `APPROVAL_REQUIRED=true` 只是配置占位值，不是本仓库已实现的权限强制机制。

## 核心角色

Coordinator 负责拆解需求和组织交接；Worker 在隔离工作区完成分配的修改；QA 从冻结候选执行适用验证；Reviewer 独立检查差异和证据；Human Approval 决定是否合并。

## 内容

- [流程与能力边界](docs/workflow.md)：角色、状态、依赖、证据和人工决策点。
- [架构说明](docs/architecture.md)：Human、Coordinator、Worker、Reviewer 和 Human Approval 的关系。
- [能力边界](docs/capability-boundary.md)：已验证、未验证和人工决策原则。
- [中文用户手册](用户手册.md)：准备、发起任务和交接检查。
- [任务模板](docs/templates/README.md)：Coordinator、Worker、Reviewer 模板。
- [配置示例](examples/config.example.env)：占位配置，不含凭证或内部资源实际值。
- [脱敏验证案例](examples/m2-validation-case.md)：说明如何引用历史 M2 结果而不把它当作本发布版本的通过证据。
- [最小任务示例](examples/simple-task-example.md)：从需求到人工合并的最小闭环。
- [FAQ](FAQ.md)：项目定位、模型支持和运行边界。
- [路线图](ROADMAP.md)：未来方向和明确不做的事情。

## 发布边界

本仓库只包含流程、模板、手册和无凭证示例。详细边界见[能力边界说明](docs/capability-boundary.md)。机会库页面、业务数据、飞书同步、售后数据、内部 dispatch capability、本机路径和原始运行记录均不属于公开发布内容。

本项目不自动配置 remote、不自动推送或合并；实际仓库操作仍由人工审核具体提交。首次 GitHub push 由人工 Terminal 执行；Codex Worker 代为执行 push 的能力尚未验证。后续更新沿用本仓库提交历史。
