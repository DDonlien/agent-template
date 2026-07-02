# Universe 协作规范

本文件是 `universe/` 目录的 Agent 子规则，用于指导 Agent 如何维护本目录下的剧本、世界观、故事、Wiki 和叙事设计资产。

本文件不是"如何写好剧本"的创作指南，也不是项目根目录的通用工程规范。工程、Git、日志、任务管理等通用规则，仍以上层 `AGENTS.md` 为准；在 `agent-template` 元模板中，上层 `AGENTS.md` 位于 [`../AGENTS.md`](../AGENTS.md)；当 `game/` 子模板被复制到新项目根目录后，上层 `AGENTS.md` 变为项目根的 `AGENTS.md`。执行本规范时，不得违背上层 `AGENTS.md`。

`AGENTS.md` 是约定文件名，可以作为例外保留。除约定文件名外，`universe/` 内所有文件夹名和英文文件名统一使用单数形式。

---

## 0. 使用原则

### 0.1 适用范围

`universe/` 是项目内所有剧本相关文字资产的唯一根目录，包括三类内容：

1. 故事文本：小说章节、短篇、场景片段、氛围描写、角色独白等。
2. Wiki 设定：角色、地点、组织、阵营、事件、物品、技术、概念、规则等。
3. 结构剧本：主线、支线、任务、对话树、过场、关卡叙事、分支条件、变量和剧情状态等。

上述内容不得散落到工程代码目录、资源目录或临时文档目录中。

### 0.2 Agent 的工作目标

Agent 在 `universe/` 下工作的目标是维护仓库内容，而不是代替用户定稿创作方向。具体包括：

- 把用户在聊天中确认的剧本和世界观内容，整理到正确文件和目录中。
- 维护文件之间的双链、引用、正史关系和结构一致性。
- 在不浪费上下文的前提下，优先读取与本次任务相关的文件。
- 避免把草稿误写成正史。
- 避免静默覆盖、删除或重写已有设定。
- 在发现冲突、缺口或命名不一致时，记录并提示用户。

### 0.3 阅读顺序

Agent 执行任务前应按以下顺序阅读上下文：

1. 上层 `AGENTS.md`。
2. 当前 `universe/AGENTS.md`。
3. 与用户请求直接相关的目录和文件。
4. 如果涉及正史、时间线或冲突，再检查 `canon/`。
5. 如果涉及角色、地点、组织、事件或术语，再检查对应 `wiki/` 页面。

不要为了小改动全量读取整个 `universe/`。优先使用搜索定位相关文件。

---

## 1. 目录结构

推荐结构如下：

```text
universe/
  AGENTS.md

  canon/
    rule.md
    timeline.md
    contradiction.md
    open-question.md

  wiki/
    character/
    location/
    faction/
    organization/
    event/
    item/
    technology/
    concept/

  story/
    novel/
    short-story/
    scene/
    fragment/

  script/
    structured/
    dialogue/
    quest/
    cutscene/
    ink/
    include/

  reference/
    inspiration/
    external-note/
    style-reference/
    external-knowledge/

  archive/
    deprecated/
    old-draft/
```

目录命名原则：

- `universe/` 下所有文件夹统一使用单数形式。
- 英文文件名统一使用单数形式。
- 二级以下目录和文件名优先保证 Obsidian 阅读体验，可以根据项目实际情况使用中文、英文或中英混合。
- 不随意新增顶层目录；如需新增，优先判断能否归入现有大类。
- 不使用无意义文件名，例如 `新建文档.md`、`未命名.md`、`最终版2.md`。

---

## 2. 各空间职责

### 2.1 `canon/`

`canon/` 管理全局正史和一致性，不存放普通 Wiki 条目。

- `rule.md`：世界观不可轻易推翻的核心规则，例如科技边界、死亡规则、叙事禁区、角色不可违背的核心动机。
- `timeline.md`：世界时间线。涉及历史顺序、事件因果、角色年龄、组织成立时间时，需要检查此文件。
- `contradiction.md`：设定冲突记录。Agent 发现冲突时，不得擅自覆盖旧设定，应记录冲突并等待用户确认。
- `open-question.md`：未决问题。聊天中尚未定论的设定，不应直接写成正史。

### 2.2 `wiki/`

`wiki/` 存放结构化设定资料。

- `character/`：角色。
- `location/`：地点。
- `faction/`：阵营。
- `organization/`：公司、机构、团体。
- `event/`：关键事件。
- `item/`：重要物品。
- `technology/`：技术设定。
- `concept/`：术语、概念、规则解释和会被反复引用的关键词。

每个重要实体应尽量有独立页面，不应长期只存在于故事或剧本段落中。术语表不单独放在 `canon/`，可放入 `wiki/concept/` 或其他更合适的 Wiki 分类。

### 2.3 `story/`

`story/` 存放偏文学阅读的文本。

- `novel/`：长篇或章节。
- `short-story/`：短篇故事。
- `scene/`：完整场景。
- `fragment/`：片段、氛围段落、未完成文本。

故事文本可以自然写作，但重要实体首次出现时应尽量添加 Obsidian 双链。

### 2.4 `script/`

`script/` 存放面向游戏实现、任务设计、分支叙事和交互叙事的文本。

- `structured/`：通用结构剧本。
- `dialogue/`：对话树、对白段落。
- `quest/`：任务、主线、支线。
- `cutscene/`：过场脚本。
- `ink/`：由 Markdown 剧本生成或维护的 Ink / Inky 文件。
- `include/`：可被脚本复用的片段、变量、公共对白或 include 文件。

默认情况下，`script/` 下的源文件以 Markdown 维护。`.ink` 文件不是默认源文件，而是需要时再生成或维护的派生文件。

### 2.5 `reference/`

`reference/` 存放参考资料，不直接等同于项目正史。

- `inspiration/`：灵感来源。
- `external-note/`：外部笔记。
- `style-reference/`：风格参考。
- `external-knowledge/`：外部知识资料。

引用 reference 内容时，应明确它是参考，不要自动写入正史。

### 2.6 `archive/`

`archive/` 存放废弃、旧稿和历史版本。

- `deprecated/`：已废弃但有回溯价值的设定。
- `old-draft/`：旧草稿。

大改、废弃、重构时，不直接删除旧版本。除非用户明确要求删除，否则应归档。

---

## 3. 文件与内容规则

### 3.1 Markdown 优先

除 `.ink`、图片、视频、音频等特殊资产外，`universe/` 中的文字内容统一使用 `.md`。

Markdown 文件负责承载：

- 正文内容。
- 结构说明。
- 设计备注。
- 双链关系。
- 未决问题。
- 与其他世界观资产的引用。

### 3.2 Ink 伴随文件规则

不要把 Ink 文件和 Markdown 文件合并成三段扩展名，例如不要使用 `.ink.md`。

如果某个内容只需要作为 Obsidian 文档维护，则使用单独的 `.md` 文件：

```text
script/dialogue/intro-dialogue.md
```

如果某个内容同时需要 Obsidian 维护文档和可被 Ink / Inky / 脚本管线读取的文件，则使用同一目录下两个同名文件：

```text
script/dialogue/intro-dialogue.md
script/dialogue/intro-dialogue.ink
```

也就是说，允许：

```text
<name>.md
<name>.ink
```

### 3.3 附件与相对路径

插入图片、视频、音频或其他非文本资产时，应使用相对路径，确保 Obsidian 可解析。

推荐将附件放在当前文件所在目录的局部资源目录中：

```text
folder/
  name.md
  asset/
    image.png
    video.mp4
```

如同一目录下存在多个文档共用素材，也可以使用该目录下统一的 `asset/`。

### 3.4 双链规则

优先使用 Obsidian 双链：

```md
[[角色名]]
[[地点名]]
[[组织名]]
[[事件名]]
```

如果存在同名或近似实体，使用路径或别名：

```md
[[wiki/character/Alex|Alex]]
[[wiki/organization/Alex Corp|Alex Corp]]
```

重要实体首次出现时应尽量加双链。同一段落中重复出现同一实体时，不必反复链接。

### 3.5 新实体创建规则

当聊天、故事或剧本中出现新的重要实体时，Agent 应判断是否需要创建 Wiki 页面。

应创建页面的情况：

- 新角色、地点、组织、公司、阵营。
- 新技术、规则、关键事件、核心术语。
- 会反复出现的重要物品或概念。

可以暂不创建页面的情况：

- 一次性普通物品。
- 临时名字。
- 明显仍在头脑风暴中的设定。
- 用户明确表示暂不整理的内容。

如果用户只是随口发散，不要把所有内容立即写入正史；可先写入草稿、未决问题，或向用户确认。

### 3.6 页面头部信息

重要页面可以在标题下方使用简短元信息，避免复杂 YAML。

```md
# 名称

> type: character
> id: CHR-001
> status: draft
> alias: 别名A, 别名B
```

`status` 推荐值：

- `draft`：明确但未定稿，可以继续调整。
- `canon`：正史，改动需谨慎。
- `deprecated`：已废弃，保留历史。
- `conflict`：存在冲突，等待确认。

---

## 4. Ink / Inky 规则

### 4.1 `.ink` 的权重

本项目默认先用 Markdown 撰写和维护剧本。`.md` 是主要维护格式，`.ink` 是后续生成、导出或接入 Inky / 游戏管线时使用的格式。

除非用户明确要求，Agent 不自动创建 `.ink` 文件，也不为了预留版本而生成空文件。

### 4.2 何时创建或更新 `.ink`

只有在以下情况中，Agent 才创建或更新 `.ink`：

- 用户明确要求生成 Ink / Inky 版本。
- 用户明确要求维护某个 `.ink` 文件。
- 用户要求将某批 Markdown 剧本批量转换成 `.ink`。
- 项目已有稳定规则要求某类脚本同步生成 `.ink`。

### 4.3 `.md` 与 `.ink` 的职责边界

Markdown 剧本负责：

- 剧情目标、玩家目标、情绪曲线。
- 场景结构、分支结构、触发条件。
- 变量设计、状态说明、验收标准。
- 设计备注、未决问题、Obsidian 双链。

`.ink` 文件负责 Ink / Inky 可解析或接近可解析的脚本主体：

- 实际文本。
- 对话。
- 选择项。
- knot / stitch。
- 变量。
- 条件跳转。

`.ink` 文件负责脚本管线中需要被 include 的片段或公共内容，例如：

- 公共变量。
- 复用对白。
- 公共函数或宏。
- 可被多个脚本引用的片段。

不要把大量设计讨论、Markdown 标题、checkbox、复杂表格和 Obsidian 关系说明写入 `.ink` 主体。

### 4.4 同名伴随文件规则

当用户要求某个 Markdown 文件同时拥有脚本管线文件时，使用同一目录、同一基名的伴随文件。

Ink 示例：

```text
script/dialogue/intro-dialogue.md
script/dialogue/intro-dialogue.ink
```

Include 示例：

```text
script/include/common-variable.md
script/include/common-variable.ink
```

这里的“同名”指去掉扩展名后，文件基名完全一致。

---

## 5. 稳定 ID 规则

重要资产建议拥有稳定 ID，避免重命名后失去追踪。

推荐前缀：

```text
CHR  角色
LOC  地点
FAC  阵营
ORG  组织 / 公司
EVT  事件
ITM  物品
TEC  技术
CON  概念 / 规则
STO  故事文本
SCN  场景
SCR  剧本
QST  任务
DLG  对话
ARC  剧情弧
```

示例：

```md
> id: CHR-001
> id: LOC-003
> id: SCR-002
> id: QST-004
```

ID 一旦分配，不因文件移动、标题修改或内容扩写而改变。

---

## 6. 内容更新原则

### 6.1 不静默覆盖正史

如果已有内容标记为 `canon`，Agent 不应直接覆盖关键设定。除非用户明确要求，否则应保留原设定，并将冲突、替代方案或待确认点记录到 `canon/contradiction.md` 或相关文件的“未决问题”中。

### 6.2 草稿不是正史

`draft` 表示“已经被记录，但尚未定稿”。Agent 可以整理、补链、拆分和归档草稿，但不得把草稿自动改写成正史语气。

### 6.3 设计讨论与正文分离

小说正文、Wiki 正史、Ink 主体和 include 主体应尽量干净。设计讨论、AI 备注和未决问题应放在：

- 文件底部的 `## 设计备注`。
- 文件底部的 `## 未决问题`。
- `canon/open-question.md`。
- `canon/contradiction.md`。

### 6.4 保留创作痕迹

大改、废弃、重构时，不直接删除旧版本。应移动到 `archive/`，或在原文件中增加变更记录。只有用户明确要求删除时，才删除历史内容。

---

## 7. 命名规则

### 7.1 文件夹和英文文件名

`universe/` 中所有文件夹名和英文文件名统一使用单数形式。约定文件名 `AGENTS.md` 例外。

推荐：

```text
wiki/character/memory-broker.md
wiki/location/noctropolis.md
script/dialogue/intro-dialogue.md
script/include/common-variable.md
story/scene/rainy-night.md
```

### 7.2 文件名质量

文件名应优先保证 Obsidian 阅读体验，同时避免无意义名称。

不推荐：

```text
新建文档.md
未命名.md
最终版.md
最终版2.md
改过的.md
```

### 7.3 标题

文件一级标题应是内容的正式名称：

```md
# Memory Broker
```

不要只用类型名作为标题：

```md
# 角色设定
# 剧本
# 世界观
```

### 7.4 别名

如果实体有多个名字，应在页面顶部记录：

```md
> alias: 记忆经纪人, Broker, Memory Broker
```

正文中首次出现时可使用 Obsidian 别名链接：

```md
[[Memory Broker|记忆经纪人]]
```

---

## 8. Agent 执行流程

### 8.1 开始前

Agent 应先判断本次请求属于哪类操作：

- 新增内容。
- 整理已有内容。
- 修改正史。
- 拆分或合并文件。
- 生成或维护 `.ink`。
- 检查冲突。
- 建立双链或 Wiki 页面。

随后只读取与该操作直接相关的文件。

### 8.2 执行中

根据内容类型放入对应目录：

- 新故事文本 → `story/`。
- 新设定资料 → `wiki/`。
- 新任务、对话、分支剧本 → `script/`。
- 新 include 片段或公共脚本内容 → `script/include/`。
- 新正史规则、时间线、冲突或未决问题 → `canon/`。
- 参考资料 → `reference/`。
- 废弃旧稿 → `archive/`。

如果任务涉及正史变更、重大命名变更、大范围迁移或删除，Agent 应先向用户确认。若用户已经明确要求执行，则不重复确认。

### 8.3 完成后

完成内容整理后，Agent 应检查：

- 文件是否放在正确目录。
- 文件夹名和英文文件名是否保持单数形式。
- 是否误用了三段扩展名，把 include 文件和 Markdown 文件合并成一个文件。
- 重要实体是否需要 Wiki 页面或双链。
- 新设定是否与 `canon/` 冲突。
- 新历史事件是否需要更新 `canon/timeline.md`。
- 新术语是否需要进入 `wiki/concept/`。
- 废弃内容是否已进入 `archive/`。
- 如果项目存在 `README.md` 或 `INDEX.md`，是否需要同步更新入口索引。

---

## 9. 子目录 AGENTS 规则

如果某个子目录有特殊规则，可以在该子目录下创建自己的 `AGENTS.md`。

例如：

```text
universe/wiki/AGENTS.md
universe/story/AGENTS.md
universe/script/AGENTS.md
universe/script/ink/AGENTS.md
universe/script/include/AGENTS.md
```

子目录 `AGENTS.md` 只补充该目录的特殊规则，不重复根目录规则。执行任务时，如存在父级和子级 `AGENTS.md`，应从父到子依次阅读。更具体目录的规则优先，但不得违反 `universe/AGENTS.md` 和上层项目规则。
