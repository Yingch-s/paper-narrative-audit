# Paper Narrative Audit

A reusable skill for auditing academic manuscripts as independent scientific arguments, not chronological experiment logs or preemptive responses to imagined reviewers.

[中文说明](README.zh-CN.md) · [Skill specification](SKILL.md)

## What it checks

- Scientific narrative and the connection between the research question, claims, experiments, discussion, and conclusion.
- Premature defense, excessive hedging, rebuttal-shaped structure, repetitive explanation, and formulaic academic prose.
- Internal workflow and revision-history leakage (run ledgers, completion status, corrected-version chronology).
- Claim–evidence alignment, experimental comparability, figures and captions, statistical units, and consistency across sections.
- Accurate methodological boundaries, including unfavorable or mixed results, without turning them into repeated disclaimers.

The workflow uses **14 audit dimensions**, four deeper narrative tests, and three priority levels: **P0 scientific integrity**, **P1 structure**, and **P2 presentation**.

## Install

For a project-scoped installation in Codex:

```text
your-project/
└── .agents/
    └── skills/
        └── paper-narrative-audit/
            └── SKILL.md
```

For a user-level installation, place `SKILL.md` at `~/.agents/skills/paper-narrative-audit/SKILL.md`. For Claude Code, use `.claude/skills/paper-narrative-audit/SKILL.md` or its user-level equivalent. You can also supply the skill file as context to a compatible assistant.

## Modes

| Mode | Purpose |
| --- | --- |
| `AUDIT` | Diagnose and prioritize without silently rewriting (default). |
| `REVISE` | Rewrite requested passages while retaining facts and valid qualifications. |
| `RESTRUCTURE` | Reorganize argument, sections, figures, tables, and appendix. |
| `VERSION-DIFF` | Compare manuscript versions for improvements and regressions. |
| `FINAL-PASS` | Submission-stage close reading and consistency check. |
| `CLEAN-ROOM` | Review as a reader unfamiliar with earlier drafts or reviews. |

### Example requests

```text
Use paper-narrative-audit in AUDIT mode on this manuscript. Focus on
premature defense, revision-history leakage, the scientific narrative,
and claim–evidence alignment. Do not rewrite the paper yet.
```

```text
Use VERSION-DIFF to compare these two drafts. Identify new regressions,
but do not preserve an internal development timeline in proposed prose.
```

## Scientific guardrails

The skill removes *unnecessary defensiveness*, not limitations that determine validity or interpretation. It does not fabricate evidence, upgrade exploratory results to confirmatory claims, conceal incompatible protocols, or replace negative findings with positive spin. Source materials and the user's current manuscript remain the factual basis. Optional project-specific configurations can be placed in `references/PROJECT_PROFILE.md`; no private project configuration is bundled in this public repository.

## Acknowledgment

The anti-defensive editing principles are informed by [Kiterlin/anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing). This project extends those principles to manuscript-level scientific narrative, experiment-ledger prose, revision-history leakage, claim–evidence alignment, and cross-section consistency.
