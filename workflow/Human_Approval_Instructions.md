# Human Approval Instructions

## Principle
The AI recommends; an authorized TargetOrate consultant approves material scoring and portfolio decisions.

## Approval required
Human approval is mandatory when the rubric or MASTER_PROMPT triggers review, including material NS conditions, Low confidence, stale/unverified roles, leadership triggers, inferred timeline/ACV/competitor facts, near tier cutoffs, fit failures, unhappy churn, contradictions, rubric ambiguity, strategic outliers, and unresolved self review discrepancies.

## Allowed dispositions
- **APPROVE:** Accept the AI result with no score change.
- **OVERRIDE:** Change a score only with documented evidence and the governing rubric band.
- **REQUEST DATA:** Hold the affected criterion/account until required evidence is supplied.
- **ESCALATE:** Send unresolved methodology/rubric ambiguity to the workflow owner; do not invent a local rule.

## Human input and correction
The consultant may also challenge any account or criterion, not only flagged ones. Inputs are submitted through the checkpoint in `prompts/07_Human_Input_Correction_Prompt.md`.
- **Data corrections and supplied data** need a source and a date. Without them the input is logged but not used.
- **Overrides** need the replacement score, the governing rubric band, and the evidence. If the evidence does not meet the band, the override is recorded as "differs from rubric band".
- **Changes to rubric bands, weights, tier cutoffs, or ICP benchmarks** are ESCALATE, not corrections.
- After any input, the AI rescores the affected criteria, reruns the self review checks on them, and recomputes totals, tiers, and review triggers. Accounts whose tier changes across a cutoff are flagged to the reviewer.
- Final tier assignment is approved by the consultant. The AI never marks an account approved on its own.

## Approval record
Record reviewer, date, company, criterion/account, AI result, final result, disposition, evidence, rationale, and any follow-up. Overrides must be auditable and must not be made solely to achieve a preferred ABM tier.

## Release rule
A portfolio may be released when all mandatory-review items have an approved disposition or are explicitly labeled provisional/pending data. Preserve the original AI result alongside any human override.