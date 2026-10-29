---
uid: "00003"
type: DOC
status: done
importance:
emergency:
updated-time: '2026-10-29T20:52:44+08:00'
updated-by: Codex
created-time: '2026-10-29T19:59:45+08:00'
created-by: Codex
start-time:
closed-time: '2026-10-29T20:14:58+08:00'
created-version:
closed-version:
estimated-workhour:
actual-workhour:
commit-related: []
tags:
- godot
- csharp
- agent-template
---
# Description

Godot 项目默认使用 Godot .NET / C# 的脚本规范。除非用户明确特别要求其他语言，否则自有运行逻辑、编辑器工具、Godot 导入与生成脚本、自动测试均使用 C#，原型或首阶段不构成自行改用 GDScript 的理由。第三方依赖与参考原件保持原语言；Shader 和原生资源配置使用引擎格式。

- [x] App / Game 模板加入同一 Godot 语言要求，保留其余规则与未提交改动。
- [x] Codex 用户全局规则及 Gitea 共享规则加入同一要求。
- [x] 完成模板公共部分一致性、目标差异与规则读回检查。

工程命名同时保留 Godot 固定入口 `project.godot`，实际项目名写入 `application/config/name`，C# 工程和解决方案按对应项目名命名，不建立重复的 `.godot` 配置。

本任务交付规范文本；各 Godot 项目的具体 C# 迁移与运行检查由对应项目 Issue 记录，不据此宣称游戏已通过验收。本仓未配置本任务的外部 tracker，不创建外部表格。本次按用户授权交付规范文本，提交和推送结果分别核实。

# Comments

## 20261029-200109_Codex_GPT-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

按用户要求将 Godot 默认 C# 的约束写入 Codex 用户全局、Gitea 共享规则及 App / Game 标准模板。已有 Issue、飞书和版本管理条款及未提交改动保留；标准根和子模板仅按本仓要求递增自身补丁版本。App / Game 公共部分逐字一致，四处 Godot 默认条款读回各一份，`git diff --check` 通过。本任务只验证规范文本，游戏迁移、编译、headless 和用户验收由各项目独立记录。未提交或推送。

执行 Agent 为 Codex；厂牌 GPT，确切模型版本、型号档位、推理级别和加速选择无可核实的执行元信息，逐项使用 UNKNOWN。

> [本次会话](codex://threads/01a18781-7177-7d61-8773-65d49c725e6c)

## 20261029-201458_Codex_GPT-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

用户追加要求 Godot 工程采用对应项目名称。核对 Godot 官方文件路径说明后，保留引擎固定识别的 `project.godot` 入口，将实际名称和 C# 工程 / 解决方案命名方式补入全局、共享规则及 App / Game 模板。Feature Vault 对应的工程文件将使用 `godot-feature-vault.csproj` / `.sln`；此业务迁移的实际结果以该项目记录为准。官方依据：[Godot 文件路径](https://docs.godotengine.org/en/stable/tutorials/io/data_paths.html)。规范文本读回及公共部分一致性检查通过，未提交或推送。确切模型版本、型号、推理级别和加速选择仍无可核实元信息，各写 UNKNOWN。

> [本次会话](codex://threads/01a18781-7177-7d61-8773-65d49c725e6c)

## 20261029-205244_Codex_GPT-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

用户明确授权将本次 C# 默认规则与工程命名要求按仓库分别提交并推送。仅纳入 App / Game 的 Godot 小节、相应规范版本、README 的 C# 说明及本记录；此前未提交的 Issue / 飞书协作规则、模板属性和旧任务改名继续保留在工作区。混合文件使用私有 Git index 从 HEAD 合成，仅提交本轮差量，不覆盖真实工作区或原暂存。已核对 App / Game 公共规则一致、Godot 条款一致及目标差异。提交自身 hash 待后续实际更新再记录，推送结果在本次会话核实后报告。执行 Agent 为 Codex，厂牌 GPT；确切模型版本、型号档位、推理级别和加速选择不可核实，各为 UNKNOWN。

> [本次会话](codex://threads/01a18781-7177-7d61-8773-65d49c725e6c)
