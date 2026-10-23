# 精简协作规范并迁移 Issue 流程

- ID：`20261023-001`。
- 类型：`DOC`。
- 状态：实现与相关 Markdown 检查完成；待用户审阅。
- 范围：根、App、Game 和 universe 的 Markdown 规则、模板与相关引用。
- 关联：`meta-DOC-A-001`。
- 版本管理标识：`versioncontrolid`（含义待定义，保留占位）。

## 目标与当前事实

用户授权停用旧需求 / 执行日志制度，改用当前工作副本根 `issue/`，保留 16 类类型的原含义和一个 Issue 模板；活动需求迁移，历史原文保留。普通任务不自动升级模板或同步远端，按目标文件处理 Git、Perforce 等混合版本管理，不自动 commit、push 或创建 PR。

优先 Headless；Blender 任务始终要求 MCP，UE Blueprint 要求 UE 编辑器 MCP，UE 非 Blueprint 不统一要求 MCP，Rider 按实际调试 / 编译信息需要调用，Godot 优先直接改代码和 Headless。AI 检查正确性，视觉及大量自动化验收由用户负责。

## 实现

- [x] 根、App、Game、universe 规则和 README / DESIGN 引用更新。
- [x] 旧需求和日志模板停用归档，活动 `meta-DOC-A-001` 迁移；历史原文保持不变。
- [x] App / Game 通用规则、16 类类型与 Issue 模板保持一致，Issue 正文与 Comments 职责清晰。

## 检查

- [x] 相关 Markdown 一致性、55 处相对链接 / 标题引用、47 份原文归档完整性及 `git diff --check` 均通过。

## 用户审阅

- [ ] 用户审阅本次规则与 Issue 命名约定；实现或本地检查通过不代替用户确认。

## 边界与下一步

当前分支 `main`，原工作区干净。不得创建 / 切换 branch 或 worktree，不 commit、push 或开 PR，不做 GUI / 自动化验收，不修改 my-issue 插件。兼容实现与 `versioncontrolid` 定义属于后续任务。

## Comments

### 2026-10-23 15:57:44 UTC — Agent

根据用户提供的可信对话历史开始本次维护，确认目标为已连接 Mac 上的 `DDonlien/agent-template` 现有工作副本；根、App、Game 和 universe 适用规则及旧需求均已阅读。先在临时目录形成 Markdown 修改，再应用到该工作副本，保持用户分支与提交状态。

### 2026-10-23 16:01:33 UTC — Agent

已完成本次 Markdown 更新与活动需求迁移。19 份当前文档的一致性与引用检查通过，App / Game 通用规则和 16 类原定义一致，每份项目模板保留一个相同的 Issue 模板；47 份旧需求 / 日志 / 模板与原件逐字节一致。停用档案中的历史引用按原文保留，不作为活动入口。

当前仍为 `main`，HEAD 未改变，Git 暂存区为空，改动均未提交。未创建或切换 branch / worktree，未 commit、push 或创建 PR；未做 GUI、视觉或自动化验收，未修改 my-issue 插件。用户审阅仍未勾选；`versioncontrolid` 继续保留明确占位。
