# 20260807-214301-utcp8-taobe-deepseek-v4-flash

## 用户原始 Prompt

```text
这些记录到 2 个AGENTS 文档：A1, A2, A3, A4, A5, A6, B4, B5, B6, B8, C3, C9;
A7, B1, B3, 在 GAME 的 AGENTS 文档里记录为针对 UE 引擎项目的专门要求而非所有游戏的泛用要求；
```

## 启动运行时的分支和版本

- 分支：`main`
- 版本：待本次任务提交后确定（执行前未记录具体 commit；工作区为 `agent-template` 元模板仓库）
- 同步：本任务在受限网络环境执行，未执行 `git fetch --prune` 同步预检；变更仅限工作区文档，未涉及提交。

## 任务执行时间

- 开始：`2026-08-07 21:43:01 UTC+8`
- 结束：`2026-08-07 21:47:00 UTC+8`（约）
- 任务结束时是否执行了提交：否

## 已阅读上下文

- `agent-template/AGENTS.md`（元模板协作规范）
- `agent-template/app-agent-template/AGENTS.md`（编辑对象）
- `agent-template/game-agent-template/AGENTS.md`（编辑对象）
- `agent-template/REQUIREMENTS.md`
- 既有日志 `agent-log/20260713-093516-utcp8-taobe-gpt-5-5.md`（格式参考）

## 匹配到的需求

- 无明确需求 ID；本次为「标准内容」扩充，与 `REQUIREMENTS.md` 中 `meta-DOC-A-001` 的同步更新要求一致。

## 对话与行动记录

- 前置阶段：扫描 `~/Projects/GitHub` 与 `~/Projects/Gitea` 下全部仓库共 40 份 `AGENTS.md`，与 `app-agent-template/` / `game-agent-template/` 标准版逐份 diff，提炼出值得反哺标准版的条目（A/B/C/D 四级，来源另列为 lesson learn）。
- 用户确认收录范围：A1、A2、A3、A4、A5、A6、B4、B5、B6、B8、C3、C9 写入两份模板；A7、B1、B3 仅写入 Game 模板，且限定为 UE 引擎项目专门要求。
- 本次改动为「标准内容」修改，按元模板规则同步更新两份子模板，并将版本号从 `v1.0.0-260713-093516` 提升为 `v1.1.0-260807-214301`（新增两个小节，属 minor 变更）。
- 已确认两份模板修改前逐字一致，编辑采用相同的锚点文本。
- 执行编辑（两份模板各一次批量编辑）：
  - §2 每次任务执行中：追加对话归档纪律（B5，3 条）。
  - §3 REQUIREMENTS 维护标准：追加需求描述语言质量（B4，3 条）与需求收录边界（A4，3 条）。
  - §7 工程默认规则：追加验证边界（A2，2 条）、提交纪律（A3，3 条）、事实与推断标注（A5，1 条）、注释规范（B6，1 条）、一致性检查（C3，1 条）、流程阶段化（B8，1 条）。
  - §8 目录命名规则：追加存量不迁移（A6，1 条）与跨平台文件名约束（C9，1 条）。
  - 新增「### 11. 版本管理纪律」（A1，5 条），两份模板同步。
  - 仅 Game 模板新增「### 12. UE 引擎项目专门要求」（A7 工具链访问纪律、B1 调试无响应排查、B3 编辑器启动默认值），开头注明仅适用于 Unreal Engine 项目。

## 完成工作

- 更新 `app-agent-template/AGENTS.md`：版本号 `v1.1.0-260807-214301`；§2、§3、§7、§8 扩充；新增 §11。
- 更新 `game-agent-template/AGENTS.md`：版本号 `v1.1.0-260807-214301`；§2、§3、§7、§8 扩充；新增 §11、§12（UE 引擎专门要求）。
- 顶层 `agent-template/AGENTS.md` 与 `universe/AGENTS.md` 未改动，版本号保持不变。
- 新增本次执行日志。

## 更新的需求 ID

- 无。

## 更新的 README 或 DESIGN 章节

- README：无
- DESIGN：无

## 验证方式

- `diff app-agent-template/AGENTS.md game-agent-template/AGENTS.md`：确认除 §12（UE 专门要求）与「项目专用内容」占位标题差异外，标准内容段一致。
- `rg "### 11|### 12|版本：v1\.1\.0" app-agent-template/AGENTS.md game-agent-template/AGENTS.md`：确认小节与版本号写入。
- 未运行自动化测试；纯文档变更。

## 备注

- 本次执行环境无网络访问，未执行 Git 同步预检；如需提交，请在允许网络访问的模式下补做预检。
- 条目来源（lesson learn）记录在对话中，未写入模板。
