# Paper Narrative Audit（论文叙事审查 Skill）

这是一个面向科研论文的通用审查 Skill：让最终稿读起来是一篇独立、自洽的科学论文，而不是实验总账、修订日志或提前写好的 rebuttal。

[English README](README.md) · [SKILL.md](SKILL.md)

## 检查范围

覆盖论文主线、提前防御、过度保留语气、内部工作痕迹、修订历史残留、重复解释、自造术语、实验协议可比性、证据与主张对应、图表语义，以及摘要到附录的全文一致性。

包含 14 项检查维度、4 项深层叙事测试，使用 P0（科学真实性）、P1（叙事结构）、P2（局部呈现）区分修改优先级。

## 安装

将 `SKILL.md` 放入对应目录：

- Codex 项目级：`.agents/skills/paper-narrative-audit/SKILL.md`
- Codex 用户级：`~/.agents/skills/paper-narrative-audit/SKILL.md`
- Claude Code 项目级：`.claude/skills/paper-narrative-audit/SKILL.md`

也可以直接把 `SKILL.md` 提供给支持读取上下文的助手。

## 工作模式

| 模式 | 作用 |
| --- | --- |
| `AUDIT` | 全文诊断，默认不直接修改。 |
| `REVISE` | 只对指定段落做精准改写。 |
| `RESTRUCTURE` | 重组主线、章节、图表及附录。 |
| `VERSION-DIFF` | 比较版本，定位修改回退和新增问题。 |
| `FINAL-PASS` | 投稿前的全文一致性检查。 |
| `CLEAN-ROOM` | 假设读者不知道任何旧稿和审稿历史，检查稿件是否独立成立。 |

示例：

> 按 paper-narrative-audit 的 AUDIT 模式检查这篇论文，重点看防御性写作、实验总账、内部工作痕迹和证据一致性。先诊断，不要直接全文重写。

## 核心原则

先审科学真实性，再审主线与结构，最后修语言。反防御性写作不意味着删掉必要限定，不得虚构实验、夸大因果、掩盖负结果或把不兼容的实验伪装成可直接比较。

如需针对单篇论文添加检查背景，可在本地创建可选的 `references/PROJECT_PROFILE.md`；本公开仓库**不包含**任何私人论文配置、论文正文或实验记录。

## 致谢

反防御性编辑理念参考 [Kiterlin/anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing)。在此基础上，增加论文主线、实验总账、修订历史、证据对应与全文叙事审查。
