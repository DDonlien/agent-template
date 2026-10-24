# agent-template 元模板

用于初始化和维护 App / Game 项目的 Agent 协作规范。模板优先使用 Headless 工作方式，以 `issue/` 记录需求、检查和交接，区分实现完成与用户验收。

## 子模板

- [App 模板](app-agent-template/AGENTS.md)：应用、网站、工具和服务项目。
- [Game 模板](game-agent-template/AGENTS.md)：游戏项目，包含 [universe 叙事资产规则](game-agent-template/universe/AGENTS.md)。

## 初始化项目

在用户指定的新项目目录中按需复制相应子模板，包含适用的 `.gitignore` / `.gitattributes` 等隐藏文件；排除嵌套 `.git`、个人 IDE 配置与 `archive/retired-workflow/` 停用档案。保留 `issue/` 中的一个 [Issue 模板](app-agent-template/issue/issue_template.md)，按实际项目填写规则与说明，其他文档按需要维护。

任务路径统一为 `project-name/worktree(如有)/issue/issue_任务描述[_实际版本编号].md`。实际实施版本只在核实后填写；尚无提交或未核实则省略文件名后缀，并在 property 说明。目录示例不授权创建 branch 或 worktree。

## 维护

先阅读 [`AGENTS.md`](AGENTS.md)。通用规则同时更新 App / Game，活动维护记录见 [`issue/`](issue/)；普通项目任务不自动升级模板，也不自动提交。

旧需求与执行日志保留在 [停用档案](archive/retired-workflow/README.md)，不再用于新任务。Issue 正文维护当前事实，Comments 追加历史；16 类类型保留原含义，见 [Issue 类型](app-agent-template/AGENTS.md#issue-类型)。
