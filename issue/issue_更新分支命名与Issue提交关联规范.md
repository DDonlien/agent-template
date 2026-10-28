---
uid: "00001"
type: DOC
status: in_progress
importance: p0
emergency: p0
updated-time: "2026-10-28T05:12:01+00:00"
created-time: "2026-10-28T05:12:01+00:00"
start-time:
closed-time:
created-version:
closed-version:
estimated-workhour:
actual-workhour:
commit-related: []
tags:
  - agent-template
  - collaboration
---
# Description

在 agent-template 源仓库落实用户确认的分支命名、Issue 元数据和提交关联规范，并仅提交本任务文件。

- 分支名采用 `user-name/target-branch-name[/usage-name]`；仅人工明确授权 Agent 创建时适用，已有分支不重命名，名称不代表实际 Git 祖先。
- UID 为仓库内唯一的五位十进制字符串；同一 Git common repository 的分支和 worktree 共用命名域，既有 id、parent、completed-time 和历史数据保留。
- 提交消息使用 Summary、Detail，空一行后以单行 `Issues: issue-00001` 关联真实任务；同一 Issue 可跨提交，一次提交可列多个去重 UID。不创建或移动原生 Git tag。
- 源模板保留用户新增字段、Comment 首尾引用和附件路径；commit-related 反向记录实际完整 hash，未知时间、版本和工时留空。
- `732bc1fa0d74586aea519e8ba7e8ee05eb448589` 是用户手写模板的输入提交，不冒充本轮适配实现提交。

## 当前范围与状态

- [x] 确认最终 Issues trailer、多对多关联及仓库内 UID 域。
- [x] 保留现有内容更新检查、按需文档维护和授权边界；普通任务不自动升级远端模板。
- [ ] 完成源规则、三份模板及本 Issue 的最终一致性检查并提交。
- [ ] 将已产生的真实适配提交 hash 录入 commit-related 和对应 Comment。

本 Issue 只覆盖源仓库。本轮跨仓库首批写入仍受此前审批拒绝限制，其他工作副本及 13 个未检出分支未推广；my-issue/main 的 merge、第三方、生成及 demo 副本保持不动。

commit-related 记录填写时已存在的相关提交；后续记录提交自身的 hash 延至下一次实际 Issue 更新补入，不为追写自身 hash 继续制造提交链。

# Comments

## 20261028-051201_Codex

依据用户最终确认，将提交内关联统一为单行 Issues trailer，移除待确认载体及原生标签移动表述。此时尚未产生本轮实际适配提交，因此 commit-related 暂为空列表，不填写伪造或占位 hash；真实 hash 在提交生成后记录。

本次执行环境未提供完整模型标识，未补造 Model-Detail。未执行 GUI、引擎或业务构建验收。

> [本次规范适配需求与执行对话](codex://threads/01a172bc-a59e-74ad-9553-ff4370c9a0f0)
