# agent-template 元模板

用于初始化和维护 App / Game 项目的 Agent 协作规范。模板优先使用 Headless 工作方式，以 `issue/` 记录需求、检查和交接，区分实现完成与用户验收。

## 子模板

- [App 模板](app-agent-template/AGENTS.md)：应用、网站、工具和服务项目。
- [Game 模板](game-agent-template/AGENTS.md)：游戏项目，包含 [universe 叙事资产规则](game-agent-template/universe/AGENTS.md)。

## 初始化项目

在用户指定的新项目目录中按需复制相应子模板，包含适用的 `.gitignore` / `.gitattributes` 等隐藏文件；排除嵌套 `.git`、个人 IDE 配置与 `archive/retired-workflow/` 停用档案。保留 `issue/` 中的一个 [Issue 模板](app-agent-template/issue/issue_template.md)，按实际项目填写规则与说明，其他文档按需要维护。

任务路径统一为 `project-name/worktree(如有)/issue/issue_任务描述.md`：中文不翻译、英文词用连字符，类型只记在属性中，文件名不带版本编号。Git / P4 编号记在对应 Comment，`recorded-version` 是可选的内容发布版本。目录示例不授权创建 branch 或 worktree。

## 维护

先阅读 [`AGENTS.md`](AGENTS.md)。通用规则同时更新 App / Game，活动维护记录见 [`issue/`](issue/)；普通项目任务不自动升级模板，也不自动提交。

旧需求与执行日志保留在 [停用档案](archive/retired-workflow/README.md)，不再用于新任务。Issue 使用 frontmatter 和 Description / Comments 两个一级正文标题；Description 维护当前事实，Comments 按规定二级标题追加历史；16 类类型保留原含义，见 [Issue 类型](app-agent-template/AGENTS.md#issue-类型)。

Issue 名称与文件名描述真实交付物或功能。绑定飞书后，新 Issue 默认进入同一任务表，完整 Comments 对应“最新进展记录”一格；创建人、修改人和产品版本的写法见模板 AGENTS.md。Codex 用户全局规则位于 `/Users/taobe/.codex/AGENTS.md`。

Godot 项目默认使用 Godot .NET / C#，包括自有运行脚本、编辑器工具、Godot 导入脚本和自动测试；只有用户明确特别要求才使用其他脚本语言。规则见 App / Game 模板的 Godot 小节。Godot 入口固定为 `project.godot`，显示名称和 C# 工程 / 解决方案按实际项目命名。

实际执行并记录 Issue 时，本地 assignees 只追加已核实的 GitHub/Gitea 平台账号，created-by / updated-by 使用对应用户；绑定飞书后，执行人保留原有成员并追加对应飞书用户。标准细则见 App / Game 的“执行人与平台身份”，不会因新建待办或同步字段而自动认领任务。
