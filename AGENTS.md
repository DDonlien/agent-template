# Agent Template 元模板协作规范

版本：v2.1.4-261024-162234

本仓库维护可复制的 App / Game 协作模板，不直接作为项目模板。用户最新明确要求优先于模板和历史资料。

## 适用规则与入口

1. 元模板维护采用 [App 模板的通用规则](app-agent-template/AGENTS.md#通用规则)，包括最小改动、Headless、Issue、版本管理与用户验收边界；不继承其项目示例。Game 通用部分必须与 App 一致。
2. 初始化 App 使用 [`app-agent-template/`](app-agent-template/AGENTS.md)，初始化 Game 使用 [`game-agent-template/`](game-agent-template/AGENTS.md)。`game-agent-template/universe/` 是叙事资产子目录；改动前阅读其 [局部规则](game-agent-template/universe/AGENTS.md)。
3. 普通项目任务不自动检查或升级远端模板。维护本仓库时只检查当前工作副本与目标改动，不自动执行远端同步；分支 / worktree 的创建、切换和重定位均须明确授权。
4. 默认不 commit、push、创建 PR 或执行其他提交 / 发布动作；单独的每日 commit 和手动 commit 流程不提供本任务授权。

## 仓库内容

- [`README.md`](README.md)：模板用途与初始化入口。
- [`issue/`](issue/)：活动维护任务、检查与交接；[Issue 模板](issue/issue_template.md) 是唯一占位模板。
- [`DESIGN.md`](DESIGN.md)：元模板无视觉界面的现有说明。
- [`app-agent-template/`](app-agent-template/AGENTS.md)、[`game-agent-template/`](game-agent-template/AGENTS.md)：可复制的项目规则与示例文档。
- [`archive/retired-workflow/`](archive/retired-workflow/README.md)：已停用的旧需求、执行日志及模板，保留历史原文，不再追加新任务。

## 模板维护

1. 通用规则只在 App / Game 的通用部分维护；修改时同步两份，保持内容一致。技术栈专用规则放在对应模板；涉及引擎或原生资产时，按 Game 的[引擎与原生资产实现原则](game-agent-template/AGENTS.md#引擎与原生资产实现原则)维护局部一致性、可编辑资产与原生能力优先，具体引擎只补必要差异。项目示例保持清晰且不强制填空。
2. 根、App、Game 的 `AGENTS.md` 修改规则或元数据时递增自身语义版本，并更新 `vx.x.x-yymmdd-hhmmss` 时间戳；本次 v2.0.0 表示从旧需求 / 日志制度迁到 Issue 的协作流程变化。Universe 的局部版本独立维护。
3. 修改结构时同步相关 README、DESIGN、Issue 和 universe 引用；用 `rg` 与 Markdown 链接 / diff 检查确认一致性。按本次范围说明实际检查，视觉和大量自动化验收由用户决定。
4. 活动任务迁到 `issue/` 并保留旧稳定 ID。属性使用 frontmatter，正文仅有 `# Description` 和 `# Comments` 两个一级标题；Description 维护当前事实，Comments 以规定的二级标题追加。16 类类型及完整规范以 [Issue 维护标准](app-agent-template/AGENTS.md#issue-维护标准) 和 [Issue 类型](app-agent-template/AGENTS.md#issue-类型) 为准。
5. 标准路径为 `project-name/worktree(如有)/issue/issue_任务描述.md`，按原语言命名，中文不翻译、英文词用连字符；类型只在属性中，文件名不带版本编号。Git / P4 编号记在对应 Comment 内容里，可涉及多个 change；`recorded-version` 仅为可选的内容发布版本。历史时间、具体 Agent、模型或原会话无法追溯时保留原始信息并说明缺失，不补造；每条实际执行 Comment 末尾使用有来源依据的对应会话深度链接，不照抄模板示例，也不把文档迁移会话冒充历史业务执行会话。
6. 新增子模板时提供适用的规则、README 与一个 Issue 模板，其他文档按实际需要创建；不复活旧 `REQUIREMENTS.md` / `agent-log/` 制度，不为每层目录补空文档。
7. 维护规则与文件格式，不修改 my-issue 插件；现有实现兼容属于独立任务。

## 复制到项目

按 [`README.md`](README.md) 选择对应子模板，保留适用隐藏配置，排除模板 `.git`、个人 IDE 配置和停用档案。新项目按实际内容填写规则，使用根 `issue/`；已有项目只按用户授权迁移，不自动改工作区布局、版本管理系统或分支。
