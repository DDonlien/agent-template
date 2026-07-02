# 元模板需求

本文件记录 `agent-template/` 元模板自身的维护需求。

撰写规则见 [`AGENTS.md`](AGENTS.md)。

# 任务清单

## Phase - meta - 元模板自身维护

### meta/main: 维护元模板结构

- [ ] \[meta-DOC-A-001] 元模板自身结构稳定 #P1
  - [ ] 顶层 `AGENTS.md` / `README.md` / `REQUIREMENTS.md` / `DESIGN.md` 与 `agent-log/` 保持稳定
  - [ ] `app-agent-template/` 与 `game-agent-template/` 子模板保持可用
  - [ ] 顶层 `agent-log/` 保留全部历史；子模板 `agent-log/` 仅保留占位
  - [ ] 修改「标准内容」时同步更新 `app-agent-template/AGENTS.md` 与 `game-agent-template/AGENTS.md`
