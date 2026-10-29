---
uid: '00002'
type: DOC
status: done
importance: p0
emergency: p0
updated-time: '2026-10-29T22:17:33+08:00'
updated-by: github.com/DDonlien
created-time: '2026-10-28T08:17:50.265765+00:00'
created-by:
start-time: '2026-10-28T08:17:50.265765+00:00'
closed-time: '2026-10-29T22:17:33+08:00'
created-version:
closed-version:
estimated-workhour:
actual-workhour:
commit-related: []
assignees:
- github.com/DDonlien
tags:
- agent-template
- tracking-policy
---
# Description

供App和Game项目使用的Issue与飞书协作规范。说明任务如何命名和拆分，怎样沿用项目已有表格，以及如何保留历史、版本和人工修改。

- [x] 以最终用户可直接或间接感知结果为唯一分类界限，功能性必须关联 Issue，事务性遵循项目原有记录要求。
- [x] 明确自动复用、修改、独立任务 / 子任务判断及仓库内 UID 规则，避免普通追踪判断反复询问。
- [x] 仅按项目明确配置维护外部 tracker；稳定键与链接双向对应，恢复时吸收最新人工修正，不覆盖成熟工作流。
- [x] 保留模型五维标识、提交关联与既有字段，完成本地规范文本和相称静态检查。

本记录的完成范围是规范文本及检查；本轮未提交或推送。不把准备工作当作外部同步，也未默认启用外部表格。本次未发现针对该规范维护需求的外部 tracker 映射，未写外部系统；业务任务仍按项目实际配置执行。提交尚未生成，commit-related 不填旧 HEAD 冒充本需求实现；本提交自身 SHA 留待下次实际 Issue 更新，不制造递归记录提交。

## 新增交付规范

本轮按用户要求补充产出命名、真实功能层级、已有飞书绑定的延续、全文Comments同步、创建/修改人及尊重人工版本/删列的规则。同步标准App/Game、用户全局及当前三项目/共享规则；不修改未关联项目的业务数据。

## 执行人与平台身份规范

- [x] 标准 App / Game、全局与82个Git工作区同步本次人员规则，保留原有项目规则和待提交改动。
- [x] Issue 模板加入 assignees 列表，本地创建/修改身份使用已核实的 GitHub/Gitea 账号；历史身份不猜填。
- [x] 实际执行且 Issue 已记录时，飞书执行人只追加对应用户，保留现有人；只做任务拆解或字段同步不认领未开工功能。
- [x] 校验同步覆盖、YAML、原文保留和修改边界；不将文档规范视为插件后台实现或远端提交。

本次标准维护实际执行用户已通过 GitHub 当前用户资料核实为 github.com/DDonlien；本维护 Issue 未绑定飞书记录，按项目既有约定不新建表格或虚报执行人外部写入。

# Comments


## 20261028-081750_Codex_GPT-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

将用户关于任务分类与双向追踪的明确要求落实到规范、模板说明和本任务记录。开始时重新读取了本工作副本当前规则与任务上下文；保留项目既有内容，未替项目创建外部追踪系统。本次只检查相关文档、YAML、引用、UID和diff，不做业务构建、GUI或视觉验收。

当前可核实Agent为Codex、厂牌为GPT；本次确切版本、规模、推理级别与用户加速选择无执行级元数据，使用UNKNOWN。全局默认配置与priority不作为本次或历史FAST证据。

> [本次任务分类与追踪协作规范的需求及执行对话](codex://threads/01a172bc-a59e-74ad-9553-ff4370c9a0f0)

## 20261029-142441_Codex_GPT-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

用户要求将本轮任务管理纠正规则加入标准并同步全局。保留根Issue模板已有的parent-issue人工改动，新增created-by/updated-by；标准根与子模板版本分别递增，Codex全局与Gitea共享规则及当前项目同步。模型确切版本、规模、推理及加速选择不可核实为UNKNOWN；本轮未提交/推送。

> [本次会话](codex://threads/01a1817c-faa5-7f40-880c-6f471387d72c)

## 20261029-150141_Codex_GPT-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

本轮完成标准、模板和全局规则同步。人模人样按真实功能改名并重整父子关系，45个已命名任务及1个未命名草稿保留；8个归并事项的完整说明与Comments已保留。三项目136个绑定任务的飞书最新进展记录与本地Comments逐条完全一致，最长50494字符，未截断。创建人和修改人均使用飞书内置字段，删除字段未用隐藏代替，人工版本、状态、负责人及日期保留。已检查UID、关系无环、历史、YAML和引用；未运行或验收游戏，未提交或推送。模型确切版本、规模、推理及加速选择不可核实，逐项UNKNOWN。

> [本次会话](codex://threads/01a1817c-faa5-7f40-880c-6f471387d72c)

## 20261029-151155_Codex_GPT-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

进一步将没有独立产出的素材授权核查归入试玩包分发条件，不再仅改名为清单任务。人模人样最终为44个已命名功能任务、1个未命名草稿，9个归并旧事项的UID和完整历史保留；原有已知预期工时468小时只是重分配，新AI任务仍未估算。此前45/8及三表136的记录是这次追加调整前的时点，不改写历史。当前三表共135个绑定活动任务。未提交或推送。模型确切版本、规模、推理和加速选择不可核实，逐项UNKNOWN。

> [本次会话](codex://threads/01a1817c-faa5-7f40-880c-6f471387d72c)

## 20261029-221733_Codex_GPT-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

按用户要求增加执行人与平台身份标准。60个Git common repository、82个工作区完成本地同步，共86份AGENTS.md和72份实际Issue模板；全局与Gitea共享规则已更新。assignees使用列表并仅追加，created-by/updated-by使用已核实的平台账号；飞书执行人先读后合并，不覆盖既有成员；飞书内置创建/修改人保留原类型。未因代建待办或字段同步而批量认领未开工功能。

本任务执行用户通过GitHub连接器当前用户资料核实为github.com/DDonlien，已追加到本Issue并用于本轮updated-by；历史created-by缺少可核实平台身份，保留空值，不回填当前用户。本维护任务没有飞书绑定，因此没有声称外部人员写入，也没有新建表格或改其他业务任务的执行人。

已核对86份规则内容一致性、72份模板YAML、旧属性值/顺序与Comments保留；82个工作区的目标路径diff检查通过。源模板版本更新为根v2.2.2、App/Game v2.1.2；未升级其他项目完整模板、产品版本或改变源码。上游参考仓库、构建/发布工作树与Git内部目录未改。

原生Perforce目录未写入：迷宫球配置服务不可达，跃入迷城服务可连接但认证无效，不能确认文件映射/打开状态，故未创建受控文件或pending change；两个项目对应Git协作文档和全局规则均已更新。本轮未commit/push/submit，也未实现myIssue插件或后台同步服务。确切模型版本、规模、推理级别与加速选择不可核实，分别为UNKNOWN。

> [本次会话](codex://threads/01a1817c-faa5-7f40-880c-6f471387d72c)
