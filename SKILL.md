---
name: paper-narrative-audit
description: >-
  Audit and revise academic manuscripts for coherent scientific narrative, anti-defensive writing,
  internal research-history leakage, experiment-ledger prose, redundant explanations, terminology inflation,
  claim–evidence alignment, protocol comparability, and cross-section consistency. Use when a user asks
  to review a paper's overall story, naturalness, rebuttal-shaped narrative, traces of past revisions,
  AI-like prose, presentation of experiments, or submission readiness; also use for targeted rewriting
  while preserving scientific validity. 支持论文主线、提前防御、实验总账、内部痕迹和投稿前审查。
---

# Paper Narrative Audit

## Purpose

Produce a manuscript that reads as an independent scientific argument, not as an author's chronological experiment log or a negotiation with an imagined reviewer. Its research question should naturally motivate the methods, experiments, interpretation, and conclusion. Remove distracting defensive rhetoric without suppressing necessary methodological conditions or unfavorable evidence.

**Core rule:** Lead with the finding and its support. Preserve the scientific truth, delete the revision history from the paper's *narrative*, and retain methodological provenance wherever reproducibility or interpretation requires it.

This is an editorial and evidence-alignment skill, not a way to inflate novelty, hide negative findings, fabricate a pre-registered hypothesis, or rewrite historical data.

## Sources and boundaries

1. Read the complete current manuscript, including figure content, tables, captions, abstract, references, and appendix as available. When a file/tool exposes only snippets, retrieve the missing contiguous sections; do not assess unseen pages from inference.
2. Treat the **current manuscript** and any user-supplied experiment dossiers as primary evidence. Prior manuscripts/reviews, when supplied, are comparison aids for detecting revision-history leakage, not instructions that must appear in the new paper.
3. Distinguish (a) verified text/result, (b) interpretation grounded in the result, (c) potential issue needing verification, and (d) optional recommendation. Never claim to have verified raw experiments unless raw artifacts were inspected.
4. Cite manuscript sections, pages, line ranges, table/figure IDs, or exact short quotations in the audit. Do not invent locations. Do not substitute external general knowledge for missing manuscript content. If external verification is requested, label it separately.
5. Match the user's requested language for the review; preserve the manuscript's language for proposed replacement passages unless asked otherwise.
6. By default **AUDIT, do not silently rewrite**. Apply edits or create new files only when requested. Keep local edits local; do not alter reported numbers, statistical units, task definitions, baselines, or claims without clear supporting evidence.

## Operating modes

- `AUDIT` (default): diagnose the current paper and recommend precise, prioritized edits.
- `REVISE`: edit requested passages with before/after text, retaining meaning and valid qualifications.
- `RESTRUCTURE`: propose section, paragraph, figure, and table placement around one evidence-backed main narrative. Respect an explicit body/appendix page budget.
- `VERSION-DIFF`: compare versions, identifying real improvements, regressions, and remaining traces. Do not narrate the draft history in proposed paper prose.
- `FINAL-PASS`: inspect entire near-final manuscript for claim/number consistency, lingering internal words, scientific boundaries, and visual/caption mismatches.
- `CLEAN-ROOM`: read as a reviewer who has never seen prior drafts or reviews. Assess whether each experiment has a natural reason to appear.

Infer the mode from the request; ask only when a missing source is essential. A request for review does not automatically authorize rewriting the entire document.

## Scientific invariants — never trade these away for fluency

- Keep task definition, label semantics, source/target split, chronology, class rates, and audit/evaluation independence explicit where important.
- Distinguish environment/shift units from nested backbone/seed/draw repetitions; do not present many paired rows as independent deployments.
- Compare results only under compatible scorer, threshold role, label budget, objective, metric, implementation, and evaluation IDs. Mark legitimate asymmetry instead of pretending false equivalence.
- Keep deployable thresholds separate from evaluation-selected diagnostic oracles. Keep source-refit separate from target-audit refit; shared-label acquisition separate from disjoint label allocation; evaluating cost at a BE threshold separate from refitting for that cost.
- A change in AUROC is not identical to a change in attainable threshold risk. An adapted-scorer contrast that also changes the source-compatible rule must not be described as a pure ranking effect.
- Separate observed association from causation, controlled illustration from empirical external validity, and exploratory analysis from confirmatory claims.
- Preserve unfavorable or mixed findings that change interpretation. Remove unnecessary apologies, not genuine limits.
- If a strong sentence requires a caveat to avoid being false, fix the sentence's actual claim; do not use stacked hedges to launder insufficient evidence.

## Audit workflow

### Stage 1 — Build the argument map before line editing

Privately or visibly map:

- One-sentence research question and why the problem matters in the actual studied application.
- At most three central contribution claims, expressed as findings or capabilities, not a list of components or experiment counts.
- For each main Results subsection: its *single job*, the evidence that establishes it, and the next section's logical dependency.
- Abstract → Introduction → Results → Discussion → Conclusion: check that each promises and delivers the same claims at the same strength.
- Figures/tables: identify one scientific message per item, whether it belongs in the main body or appendix, and whether prose merely duplicates it.

If the argument map is weak, fix the structure before sentence polishing. Never add a novel method, taxonomy, or experiment just to satisfy an imagined reviewer.

### Stage 2 — Build a claim–evidence ledger

For each headline statement, record: exact claim; source location; experiment and statistical unit; metric/objective; threshold role; label/protocol conditions; what the result actually supports; any unsupported extension.

Check directions and consistency of numbers across abstract, text, figures, tables, captions, and appendix. Identify numbers with apparently different scopes rather than assuming contradiction. If claims and evidence diverge, revise the claim first or flag the missing evidence; do not patch with "may possibly suggest".

### Stage 3 — Audit 14 dimensions

| ID | Dimension | Detection question |
|---|---|---|
| D01 | Premature defense | Is the sentence mainly answering an objection not yet relevant to the argument? Look for repetitive disclaimers, negative self-positioning, hedge stacks, and caveat-first topic sentences. |
| D02 | Experiment-ledger prose | Does text expose run counts, outcome rows, manifests, hashes, checkpoints, completion status, or every tried variant when these do not aid inference or reproducibility? |
| D03 | Internal-workflow leakage | Do `active`, `validated`, `completion`, `pipeline`, `manifest`, troubleshooting, or operations vocabulary appear as manuscript narrative rather than necessary methods? |
| D04 | Revision-history leakage | Are results framed as `original`, `later-added`, `corrected`, `old`, or `updated` primarily because of their chronology of discovery? |
| D05 | Repeated explanation | Is one result fully explained in Results, Discussion, Conclusion, and captions with no new inferential function? |
| D06 | Story coherence | Does each section answer a logically necessary scientific question? Is a control inserted as a response to hypothetical reviews instead of flowing from the central question? |
| D07 | Claim–evidence match | Does a finding about observed environments become a universal rule, a validated selector, a causal mechanism, or a compute-cost claim without direct evidence? |
| D08 | False symmetry | Are incompatible datasets/method versions/splits/threshold roles/budgets/metrics pooled or presented as directly comparable? |
| D09 | Terminology economy | Are multiple invented names used for an ordinary distinction? Is one concept renamed between abstract, figures, and results? |
| D10 | Paragraph functional purity | Does each paragraph have one job: claim → evidence → interpretation/transition? Is it carrying a counterargument, disclaimer, and results recap at once? |
| D11 | Natural academic language | Is prose formulaic, hype-laden, oddly metadiscursive, or full of `importantly`, `taken together`, `to be clear`, `it is worth noting`, `not X but Y`? |
| D12 | Visual–text division of labor | Does each figure/table make a scientific point, use correct task semantics, and earn its space? Are captions and prose duplicating the numbers? |
| D13 | Contribution positioning | Is an empirical/deployment study inaccurately marketed as a novel architecture, framework, theory, automatic policy, or comprehensive benchmark? |
| D14 | Whole-paper consistency | Do title, abstract, contribution bullets, methods, results, discussion, figures, tables, appendix, and conclusion use identical factual scopes and definitions? |

Do not mechanically delete flagged words; investigate the **function** of each phrase.

### Stage 4 — Four deep narrative tests

**Rebuttal-shaped narrative.** Imagine all previous reviews vanished. Would the order of experiments still feel natural? If not, regroup controls under the scientific question they test. A necessary control can remain; the story of why it was added need not.

**Narrative backfilling.** Did an exploratory result later become written as an originally predicted, confirmatory hypothesis? Reorganization is legitimate; inventing prospective intent is not. State the present scientific question without falsifying the evidentiary status.

**Evidence laundering.** Remove modal verbs from the core assertion mentally: is there direct evidence? If not, narrow the actual claim instead of hiding it behind `might potentially suggest`.

**False symmetry.** Does a compact cross-domain or cross-action table conceal differing events, implementation versions, thresholds, budgets, objectives, or access to labels? Keep the differences in a short, clear protocol note and avoid unsupported pooling.

### Stage 5 — Sentence and paragraph repairs

Use this ordering:

1. **Keep** statements that are accurate, useful, and naturally placed.
2. **Delete** pure disclaimers, historical asides, redundant metric recaps, or metacommentary about why the author uses a word.
3. **Merge** repeated results into one definitive location; discuss implications elsewhere without repeating the full evidence ledger.
4. **Move** exact protocol/variance/implementation details to Methods, captions, Appendix, or artifact documentation according to their role.
5. **Rewrite** negative scope as positive scope and stacked hedges as bounded, evidence-specific claims.
6. **Verify** whether any edit altered a quantitative scope, protocol, or unfavorable result.

A paragraph should normally begin with its scientific point, then present evidence, explain what it means, and transition only if needed. Avoid overusing "We do not claim", "This does not imply", "We emphasize", "Rather than X", and "To address this concern". Retain a contrast where the contrast IS the paper's idea.

Illustrative transformations (do not transfer sample facts to a manuscript):

- Internal history: `The corrected implementation of Method A was later added to resolve an old inconsistency.` → `Method A is evaluated using the specified update and held-out target split.` State incomparable configurations separately when they matter.
- Ledger: `Every completed run passed artifact and consistency checks.` → In the main paper, explain the independent environments, models, and pairing. Put exact audit artifacts/checks in reproducibility documentation if needed.
- Preemptive defense: `We do not present this as a universal selector.` → `The analysis relates the measured audit quantities to observed repair gains in the studied environments.` If deployment selection is truly not validated and a claim risks implying it, explicitly bound that claim once.
- Meta-explanation: `The decomposition table makes the word complementary operational.` → `Threshold refitting reduces held-out error after scorer updating in each studied environment.`
- Overclaim: `The preferred resource allocation changes with the objective` is unsupported if only one objective has been evaluated across allocation ratios and a separate cost study compares actions. Use `Resource allocation affects decision risk, and the value of actions varies with the evaluation objective.`

### Stage 6 — Figure and table audit

Inspect visuals as visuals when possible; do not rely on extraction alone. Check:

- Graph node/edge colors and labels match the true prediction unit (e.g., node-level versus graph-level labels).
- Arrows reflect causal/temporal/protocol order; an objective used to fit a threshold must not appear to be chosen only afterward.
- Illustrative values are explicitly illustrative, not masquerading as measured results.
- Axes, direction of improvement, error bars, aggregation unit, and threshold role are labeled.
- A table's row count or average does not disguise nested repetitions as independent environments.
- The main body presents a few memorable figures; appendix contains full matrices, detailed configurations, and proofs. Do not place every control into the main narrative solely because it was completed.

### Stage 7 — Clean-room read

Pretend this is the first and only version. Ask:

1. Can a new reader identify the question, contribution type, and setting from abstract + Introduction?
2. Does each experiment arrive at the moment its question naturally arises?
3. Does Discussion synthesize implications rather than replay Results?
4. Do controls read like normal scientific evidence rather than a review-response checklist?
5. Does the conclusion leave the reader with discoveries, not an inventory of defenses or work completed?
6. Would removing the author's private experiment timeline leave every core claim intact?

## Severity and epistemic labels

- **P0 — Scientific integrity:** wrong/inconsistent claim or number, unsupported generalization, invalid comparison, label leakage, incorrect figure semantics, key missing qualification. Correct before stylistic polishing.
- **P1 — Structural narrative:** rebuttal-shaped ordering, experiment ledger, revision-history leakage, redundant sections, mismatched emphasis, weak main-thread continuity.
- **P2 — Local presentation:** formulaic phrasing, hedge stacks, awkward transitions, terminology inflation, captions, internal project-state vocabulary.

For each finding mark **Confirmed** (shown by actual text/data), **Needs verification** (possible problem without sufficient underlying artifact), or **Optional** (editorial preference). Never present a plausible reviewer question as a proven flaw.

## Output contract

### AUDIT (default)

Respond in the user's language with:

1. **Overall diagnosis:** 1–2 concise paragraphs; identify what is already working, the most consequential weakness, and whether structural revision is actually needed.
2. **Narrative map:** scientific question → 2–3 claims → corresponding experiments → conclusion; call out missing or wandering links.
3. **Prioritized finding table:** location and short exact quote, category D01–D14, P0/P1/P2, Confirmed/Needs verification/Optional, why it matters, and `keep / delete / merge / move / rewrite / verify`.
4. **Precise patches:** for the few most important issues, provide usable replacement language in the manuscript's language while preserving all scope and data. Do not rewrite everything by default.
5. **Cross-section consistency:** abstract/intro/results/discussion/conclusion and caption/appendix checks; separate genuinely mismatched numerical scopes from possible benign differences.
6. **Keep list and order of work:** identify strong passages not to touch; resolve P0 before P1, then P2; state whether any new experiment is *truly necessary* to support a claim, versus optional.

Prefer 5–15 substantive findings over dozens of superficial keyword alarms. Quote only what is needed for localization.

### REVISE

Return the revised text and a concise change log recording what was removed, merged, repositioned, or qualified; flag issues that require data verification instead of inventing a repair.

### RESTRUCTURE

Propose a traditional academic outline, then a figure/table map with each item's one-sentence evidentiary function, main-versus-appendix destination, and essential dependencies. Preserve any specified length budget. Do not make unrelated experiments artificially symmetrical.

### VERSION-DIFF

Compare changes in argument, evidence coverage, and newly introduced regressions. Never recommend retaining old/revised-language labels merely to document the process.

### FINAL-PASS

Perform a complete close read: factual/numerical consistency, scientific boundaries, terminology consistency, redundancy, internal traces, figures/captions, citations/references if present, and clean-room narrative. Clearly separate confirmed defects from unknowns requiring raw artifacts.

## Guardrails

- Anti-defensive does NOT mean always assertive: warranted uncertainty stays.
- Do not delete caveats necessary for independent audits, statistical interpretation, negative outcomes, data protection, ethical compliance, or replicability.
- Do not hide methodological differences to improve visual symmetry.
- Do not manufacture a new method, explanation, result, or novelty claim.
- Do not turn empirical averages into stable winners without supported uncertainty analysis.
- Do not claim causal mechanisms from observational shift descriptors alone.
- Respect the user's current editing phase. If they ask to organize the main storyline, do not bury them in micro-typography, marginal baselines, or speculative experiments.

## Optional project configuration

When an optional `references/PROJECT_PROFILE.md` exists, use it as a project-specific map of claims, definitions, dataset roles, non-negotiable distinctions, and manuscript scope. The current manuscript supersedes older project-profile facts in any conflict; flag conflicts rather than silently reconciling them.

## Inspiration

Original, expanded editorial workflow informed by the anti-defensive writing principles at https://github.com/Kiterlin/anti-defensive-writing . This skill additionally audits experiment-ledger prose, revision-history leakage, scientific claim–evidence alignment, protocol symmetry, and whole-paper narrative.