# Agent Template 元模板协作规范

版本：v1.0.0-260713-093516

本文件是 `agent-template/` 元模板的协作规范。

本元模板不直接作为项目模板使用；项目模板位于 [`app-agent-template/AGENTS.md`](app-agent-template/AGENTS.md) 与 [`game-agent-template/AGENTS.md`](game-agent-template/AGENTS.md)。维护本元模板时，请先理解下面的规则。

## 0. 元模板说明

- 本目录是 Agent 协作规范的元仓库。
- 顶层 `agent-template/` 不直接作为项目模板；它包含 `app-agent-template/` 与 `game-agent-template/` 两个子模板供复制。
- 初始化 App 项目时，复制 `app-agent-template/*` 到新项目根目录。
- 初始化 Game 项目时，复制 `game-agent-template/*` 到新项目根目录。
- `game-agent-template/universe/` 是 Game 子模板的子模块，用于游戏叙事资产。

## 1. 标准内容

「标准内容」（0–10 节）只存在于 `app-agent-template/AGENTS.md` 与 `game-agent-template/AGENTS.md`，本元模板不再单独维护。

修改「标准内容」时，**必须**同时更新 `app-agent-template/AGENTS.md` 与 `game-agent-template/AGENTS.md` 的对应章节，并在顶层 `agent-log/` 中记录变更。

## 2. 元模板结构

- [`AGENTS.md`](AGENTS.md)：本文件。
- [`README.md`](README.md)：元模板使用说明。
- [`REQUIREMENTS.md`](REQUIREMENTS.md)：元模板自身维护需求。
- [`DESIGN.md`](DESIGN.md)：标记"不适用"，元模板无 UI。
- `.gitignore`：默认忽略 `.DS_Store`。
- `agent-log/`：元模板自身的执行日志；保留全部历史。
- `app-agent-template/`：App 项目子模板。
- `game-agent-template/`：Game 项目子模板。
- `game-agent-template/universe/`：Game 子模板下的叙事资产子模块。

## 3. 维护规则

- 三份 `AGENTS.md` 文档（`agent-template/AGENTS.md`、`app-agent-template/AGENTS.md`、`game-agent-template/AGENTS.md`）的开头应包含版本号，格式为 `vx.x.x-yymmdd-hhmmss`。
- 每次修改上述任意一份 `AGENTS.md` 时，必须同步更新其版本号：根据改动幅度调整语义版本 `x.x.x`，并将 `yymmdd-hhmmss` 改为本次修改完成时的日期时间。
- 修改「标准内容」时，必须同时更新 `app-agent-template/AGENTS.md` 与 `game-agent-template/AGENTS.md`。
- 修改子模板的「项目专用内容」占位时，确保占位示例清晰、有指导性。
- 新增子模板类型（如 `library-agent-template/`、`service-agent-template/`）时，参照 `app-agent-template/` / `game-agent-template/` 创建完整的 `AGENTS.md` / `README.md` / `REQUIREMENTS.md` / `DESIGN.md` / `agent-log/`，并在本文件增加索引。
- 修改 `game-agent-template/universe/` 时，先阅读 [`universe/AGENTS.md`](game-agent-template/universe/AGENTS.md) 并遵守其规则。
- 子模板 `agent-log/` 仅保留占位文件；顶层 `agent-log/` 保留全部历史。

## 4. 复制到新项目

- 复制 `app-agent-template/*` 或 `game-agent-template/*` 到新项目根目录。
- 复制后按子模板 `AGENTS.md §0` 清理：删除嵌套 `.git`、`.github`、IDE 配置；删除子模板 `agent-log/` 中的占位文件。
- 在新项目根 `AGENTS.md`「项目专用内容」中填写真实信息。
- 顶层 `agent-template/` 目录可保留作为参考，也可以删除。

## 5. agent-log 规则

- 本目录的 `agent-log/` 保留全部历史，用于回溯元模板演进。
- 子模板的 `agent-log/` 仅保留占位文件。
- 每次执行任务时，按需在于规则创建日志；元模板自身的演进日志记录到顶层 `agent-log/`。

## 6. Git 与网络访问要求

- 维护本元模板及其子模板时，`git fetch --prune`、`git merge --ff-only` 等同步操作需要直接访问远端仓库。
- **Git 操作不应在断网或沙箱环境中静默执行**；如果当前执行环境默认禁止联网，应提示用户切换到允许网络访问的模式，否则无法完成同步预检。
- 这条规则同样适用于从本模板复制出去的实际项目：项目级的 `AGENTS.md` 已要求在任务开始前执行 Git 同步预检，该预检依赖网络访问。
