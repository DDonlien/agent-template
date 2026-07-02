# agent-template 元模板

本目录是 Agent 协作规范的元模板，用于初始化新项目。

## 子模板

- `app-agent-template/`：App 项目模板。复制 `app-agent-template/*` 到新项目根目录使用。
- `game-agent-template/`：Game 项目模板。复制 `game-agent-template/*` 到新项目根目录使用。
  - `game-agent-template/universe/`：游戏叙事资产子模块。

## 初始化新项目

```bash
# App 项目
cp -R agent-template/app-agent-template/. /path/to/new-project/

# Game 项目
cp -R agent-template/game-agent-template/. /path/to/new-project/
```

复制后按子模板 `AGENTS.md §0` 清理，并填写「项目专用内容」。

## 维护

- 修改「标准内容」时同步更新 `app-agent-template/AGENTS.md` 与 `game-agent-template/AGENTS.md`。
- 维护本目录时，先阅读 [`AGENTS.md`](AGENTS.md)。
- 顶层 `agent-log/` 保留全部历史；子模板 `agent-log/` 仅保留占位。
