# auto-rd

这是一个用于实践 **AI Agent 自动研发流水线** 的最小仓库。

## 目标

通过 GitHub Issue、GitHub Actions、Codex / Claude Code 等 Agent 的协作，把研发流程拆成：

1. 人类定义需求或问题。
2. 人类明确验收标准和测试方法。
3. Agent 基于 Issue 自动分析、实现、提交 PR。
4. 人类或独立 Reviewer Agent 审核 PR。
5. 合并并持续迭代流程。

## 推荐实践顺序

1. 使用仓库内置的 Issue 模板创建任务。
2. 给 Issue 打上 `agent-ready` 标签，表示任务已具备可执行条件。
3. GitHub Actions 监听该标签并触发 Agent 任务。
4. Agent 按照 Issue 中的验收标准完成修改并提交 PR。
5. 由人类或 Reviewer Agent 审核、测试、合并。

## 仓库内容

- `docs/ai-delivery-pipeline.md`：项目内的流水线规划与设计文档。
- `.github/ISSUE_TEMPLATE/task.yml`：统一的任务 Issue 模板。
- `.github/PULL_REQUEST_TEMPLATE.md`：PR 提交规范。
- `.github/workflows/agent_issue_router.yml`：GitHub Actions 入口骨架。

## 下一步建议

如果你要开始“找手感”，建议第一批 Issue 只挑这三类：

- 文档补充
- 小型脚本或配置项
- 低风险页面 / 非核心逻辑改动

这样最容易验证整条流水线是否顺畅，再逐步扩大 Agent 的权限和任务范围。
