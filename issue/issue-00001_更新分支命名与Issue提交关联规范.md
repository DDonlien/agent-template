---
uid: '00001'
type: DOC
status: done
importance: p0
emergency: p0
updated-time: '2026-10-28T06:44:28.615063+00:00'
created-time: '2026-10-28T05:12:01+00:00'
start-time: null
closed-time: '2026-10-28T05:17:17+00:00'
created-version: null
closed-version: null
estimated-workhour: null
actual-workhour: null
commit-related:
- f8c17ae124a79a857bb7b2b8d55b5819338a128c
- 070c03b565a24fecdb587b3e9890bddb458d7629
- 5aa803d1a449561cef7bac127b9ce7f7fe6c49a7
tags:
- agent-template
- collaboration
---
# Description

在 agent-template 源仓库落实用户确认的分支命名、Issue 元数据和提交关联规范，并仅提交本任务文件。

- 分支名采用 `user-name/target-branch-name[/usage-name]`；仅人工明确授权 Agent 创建时适用，已有分支不重命名，名称不代表实际 Git 祖先。
- UID 为仓库内唯一的五位十进制字符串；同一 Git common repository 的分支和 worktree 共用命名域，既有 id、parent、completed-time 和历史数据保留。
- 提交消息使用 Summary、Detail，空一行后以单行 `Issues: issue-00001` 关联真实任务；同一 Issue 可跨提交，一次提交可列多个去重 UID。不创建或移动原生 Git tag。
- 源模板保留用户新增字段、Comment 首尾引用和附件路径；commit-related 反向记录实际完整 hash，未知时间、版本和工时留空。
- `732bc1fa0d74586aea519e8ba7e8ee05eb448589` 是用户手写模板的输入提交，不冒充本轮适配实现提交。

- AI Comment 的 Model-Detail 记录厂牌、确切版本、规模/型号档位、推理级别与加速选择五维；不可核实项用 UNKNOWN，不用系列名或响应速度猜填。

## 当前范围与状态

- [x] 确认最终 Issues trailer、多对多关联及仓库内 UID 域。
- [x] 保留现有内容更新检查、按需文档维护和授权边界；普通任务不自动升级远端模板。
- [x] 完成源规则、三份模板及本 Issue 的最终一致性检查并提交。
- [x] 将本次记录前已产生的真实适配提交完整 hash 录入 commit-related 和对应 Comment。

本 Issue 的实现范围仍只覆盖源仓库。后续用户明确授权全库刷新并推送，跨仓库文档写入与正常推送的审批复核已通过；现有工作副本的适配由各项目对应 Issue 记录。13 个未检出本地分支未更新；my-issue/main 的 merge、第三方、生成及 demo 副本保持不动。

commit-related 记录填写时已存在的相关提交；后续记录提交自身的 hash 延至下一次实际 Issue 更新补入，不为追写自身 hash 继续制造提交链。

# Comments

## 20261028-051201_Codex_UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

依据用户最终确认，将提交内关联统一为单行 Issues trailer，移除待确认载体及原生标签移动表述。此时尚未产生本轮实际适配提交，因此 commit-related 暂为空列表，不填写伪造或占位 hash；真实 hash 在提交生成后记录。

本次执行环境未提供完整模型标识，未补造 Model-Detail。未执行 GUI、引擎或业务构建验收。

> [本次规范适配需求与执行对话](codex://threads/01a172bc-a59e-74ad-9553-ff4370c9a0f0)

## 20261028-051717_Codex_UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

> f8c17ae124a79a857bb7b2b8d55b5819338a128c

源规范实现提交已完成，实际修改四份规则、三份模板及本 Issue；提交末尾为 `Issues: issue-00001`。三份模板、App/Game 通用规则、UID 字符串与 YAML / 标题结构检查通过，scoped diff 检查通过；原有内容更新检查和按需文档维护条款保留。未进行 GUI、引擎或业务构建验收。

本次记录将上述已存在的完整实现 hash 反向写入 commit-related。承载本条记录的提交尚未生成，因此其自身 hash 留待下一次实际 Issue 更新补入；本轮不会为追写自身 hash 追加第三次提交，也不改写历史。源仓库范围已完成；跨仓库推广仍未执行，不能将本条状态理解为全库完成。

执行环境未提供完整模型标识，未补造 Model-Detail。

> [本次规范适配需求与执行对话](codex://threads/01a172bc-a59e-74ad-9553-ff4370c9a0f0)

## 20261028-061441_Codex_UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

> 070c03b565a24fecdb587b3e9890bddb458d7629

用户明确恢复全库规范刷新及推送后，源仓库的 f8c17ae124a79a857bb7b2b8d55b5819338a128c 与上述记录提交已普通推送，origin/main 读回为上述完整 SHA。该后续执行纠正 Description 中此前全库推广受阻的过期事实，并将已存在的记录提交反向补入 commit-related；不更改源规则、模板或历史 Comments。各项目的适配和剩余边界在各自 Issue 及推广报告中分别记录，不能将源范围完成理解为全部分支完成。

本条记录提交自身的 SHA 仍留待下一次实际更新补入；未运行 GUI、引擎或业务构建验收，模型详情未提供。

> [本次规范刷新需求与执行对话](codex://threads/01a172bc-a59e-74ad-9553-ff4370c9a0f0)

## 20261028-064428_Codex_GPT-UNKNOWN-UNKNOWN-UNKNOWN-UNKNOWN

> 5aa803d1a449561cef7bac127b9ce7f7fe6c49a7

落实用户对 AI Comment 模型详情的五维要求：厂牌、确切版本、规模/型号档位、推理级别、用户是否选择加速。当前系统只可核实 Codex / GPT 家族；运行环境没有提供确切模型版本、型号档位、推理级别或用户加速选择，四项均为 UNKNOWN，不根据响应速度或服务优先级猜测。历史执行参数无法重新核实，因此本轮既有缺项标题仅补全 UNKNOWN 五维，原时间、Agent、正文、来源与记录事实保留。

原缺项标题：`20261028-051201_Codex`, `20261028-051717_Codex`, `20261028-061441_Codex`。

仅修正规范、模板说明与本次适配记录，保留人工 Comment 规则。上列记录更新前已存在的实际提交；本提交自身 SHA 留待下一次实际 Issue 更新，不为自引用额外追加提交。只做文档、YAML、标题与 diff 检查，未做业务构建或视觉验收。

> [本次规范修订需求与执行对话](codex://threads/01a172bc-a59e-74ad-9553-ff4370c9a0f0)
