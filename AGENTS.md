# Agent Template 元模板协作规范

版本：v2.2.2-261029-220831

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
4. 活动任务迁到 `issue/` 并保留旧稳定 ID。属性使用 frontmatter，正文仅有 `# Description` 和 `# Comments` 两个一级标题；Description 维护当前事实，Comments 以规定的二级标题追加。16 类类型及完整规范以 [Issue 维护标准](app-agent-template/AGENTS.md#issue-维护标准) 和 [Issue 类型](app-agent-template/AGENTS.md#issue-类型) 为准。 AI Comment 的 Model-Detail 必须逐项记录厂牌、确切版本、规模/型号档位、推理级别和加速选择，以连字符连接，例如 `GPT-6.1-SOL-MAX-FAST`。任一不可核实项写 `UNKNOWN` 并说明；加速用 `FAST` / `NONFAST` / `UNKNOWN`，不根据速度、订阅或服务优先级猜测，不以系列名代替确切版本，也不回填未知历史。人工 Comment 不填模型字段。
5. 标准路径为 `project-name/worktree(如有)/issue/issue_任务描述.md`，按原语言命名，中文不翻译、英文词用连字符；类型只在属性中，文件名不带版本编号。Git / P4 编号在对应 Comment 首部以 `>` 引用，并汇总到 `commit-related` 列表；Comment 末尾以 `>` 引用真实会话链接。新版元数据字段按用户手写模板维护，assignees 采用仅追加的平台账号列表；未知版本、时间、创建/修改身份和工时留空；既有 `recorded-version`、`completed-time`、`parent`、`id` 兼容保留。分支命名及 Issue 提交关联约定继承 App / Game 通用规则，UID 在同一 Git common repository 的分支 / worktree 内统一查重；提交与 Issue 为多对多关联，不涉及移动标签。提交采用 Summary、Detail，并在正文后空一行，以单行 `Issues: issue-00001, issue-00007` 记录去重后的相关 UID；Git 仅解析 trailer 的键和值，UID 列表是本规范约定，不创建或移动 refs/tags。历史时间、具体 Agent、模型或原会话无法追溯时保留原始信息并说明缺失，不补造；每条实际执行 Comment 末尾使用有来源依据的对应会话深度链接，不照抄模板示例，也不把文档迁移会话冒充历史业务执行会话。
6. 新增子模板时提供适用的规则、README 与一个 Issue 模板，其他文档按实际需要创建；不复活旧 `REQUIREMENTS.md` / `agent-log/` 制度，不为每层目录补空文档。
7. 维护规则与文件格式，不修改 my-issue 插件；现有实现兼容属于独立任务。

## 任务分类与追踪协作

执行前以玩家 / 最终用户能否直接或间接感受到结果为唯一分类界限。功能性任务必须关联最具体 Issue，自动复用、修改或判断新任务 / 子任务；事务性不因本条被强制建 Issue。遵循 [App 通用规则](app-agent-template/AGENTS.md#任务分类与追踪协作) 的完整定义，不按文件类型或改动大小判定，也不让普通追踪判断反复中断任务。

开始及恢复执行先按项目约定读取当前任务、已配置外部 tracker 的最新状态；稳定 UID / 链接双向可定位，吸收可确认的人工修正，不用旧快照覆盖用户新值。仅维护项目明确配置的系统，保留既有流程和来源；明显冲突、关键歧义或权限不足时局部暂停，继续独立部分，不绕过权限或虚报同步。

## 复制到项目

按 [`README.md`](README.md) 选择对应子模板，保留适用隐藏配置，排除模板 `.git`、个人 IDE 配置和停用档案。新项目按实际内容填写规则，使用根 `issue/`；已有项目只按用户授权迁移，不自动改工作区布局、版本管理系统或分支。

## 本轮标准维护

Issue 标题与文件名使用实际交付物或功能名称；真实父子功能逐级拆解，不建分组空壳。已绑定飞书的项目，新任务默认进入同表，完整Comments同步“最新进展记录”一格；本地创建/修改人使用已核实的平台账号，执行人只追加；飞书创建/修改人继续使用内置人员类型。尊重用户当前版本关联、删列和人工拆解，不用隐藏或重新造列覆盖这些修改。通用条款见App/Game的“Issue名称、层级与飞书同步”。

## 执行人与平台身份

1. AI 代表用户实际执行任务，且已在对应 Issue 记录时，登记本次执行用户。只查看、规划拆解、代建未开工任务或同步字段，不据此认领这些功能；规划、文档维护本身是实际任务时，在其对应 Issue 登记，不批量认领整张待办表。
2. 本地 Issue 的 `assignees` 使用账号列表，`created-by`、`updated-by` 使用单个账号。账号取自当前仓库对应 GitHub / Gitea 平台已核实的用户，以 `<host>/<login>` 记录，避免跨站同名；不以组织名、远端仓库所有者、`git user.name`、飞书显示名或 AI 名称冒充平台用户。新建 Issue 填写有依据的创建人，实际更新时填写修改人；执行人按已确认的平台身份去重并追加，保留其他执行人。已有创建人不因后续执行而更换；历史身份仅在能确认同一账号时规范表示，缺少依据不回填当前用户。实际 Agent 与模型仍记录在 Comments。
3. Issue 已绑定飞书任务时，先读取该记录当前“执行人”，把经过核实的对应飞书用户追加进去：保留全部已有成员与顺序，仅新增缺少的用户，不把执行人数组替换为当前用户一人。写后读回确认；遇到并发新增成员时重新合并。仅追加成功或已存在才记为已同步。字段容量、权限或身份映射不支持追加时，保留原值、记录具体待处理原因，继续独立工作。
4. GitHub / Gitea 账号与飞书用户通过已验证的当前服务身份或项目明确映射对应；同名、组织归属和历史记录操作者本身不足以证明是同一人。飞书“创建人/修改人”继续使用只读的内置 `created_by` / `updated_by`，不手动伪造，也不将其回填为本地 Issue 的历史作者。本地人员使用平台账号，飞书“执行人”使用飞书用户 ID，各自保留正确身份域。
5. `assignees: []` 纳入 Issue 标准模板，新增人员属性放在 `tags` 之前；保留已有属性、UID、记录 ID、人工分工与全部历史。本规范不要求新建飞书表、恢复已删除字段、启用原生 GitHub/Gitea Issue 或批量改写历史人员。没有外部绑定时只维护本地 Issue；确需绑定而暂时不能同步时如实记录待处理。
