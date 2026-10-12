# TargetPath ABM Workflow Instructions

## Objective
Run a repeatable AI-assisted ABM account-scoring process with explicit human controls.

## Operating Chain
1. **Prepare inputs.** Complete the client ICP and account-data template; maintain the TargetOrate reference lists.
2. **Gate inputs.** Run `prompts/01_Input_Validation_Prompt.md`. STOP if the ICP is absent; otherwise resolve fatal errors and identify NS/review items.
3. **Score accounts.** Run `prompts/02_FIOR_Scoring_Prompt.md` using `MASTER_PROMPT.md` and the frozen scoring artifacts.
4. **Self review.** Run `prompts/06_Criterion_Self_Review_Prompt.md`. The AI rechecks every criterion for every account and the roll up math, corrects only what the rubric supports, and escalates anything the rubric does not settle.
5. **Handle exceptions.** Use `prompts/04_Exception_Handling_Prompt.md` for missing, contradictory, stale, ambiguous, or strategic-outlier cases.
6. **Decision gate.** If no mandatory review trigger exists, proceed to output. If a trigger exists, route only the affected accounts/criteria to consultant review.
7. **Consultant review and human input.** Run `prompts/03_Consultant_Review_Prompt.md` for flagged items. At the checkpoint in `prompts/07_Human_Input_Correction_Prompt.md`, the consultant approves, corrects data, supplies missing data, overrides scores with evidence, adds context, or escalates. The AI applies the input, rescores the affected criteria, and recomputes totals and tiers. Use `templates/Human_Review_Input_Template.csv` to submit input.
8. **Human approval.** Follow `workflow/Human_Approval_Instructions.md`. AI recommendations are not self-approving.
9. **Publish outputs.** Populate the portfolio and account-summary templates. Preserve audit rationale and data-gap flags.
10. **Validate changes.** When testing workflow/rubric changes, run `prompts/05_Validation_Adjudication_Prompt.md` against quarantined test assets only after the blind run. Human input is not accepted in a blind run.

## Source hierarchy
FIOR Rubric -> Completed Client ICP -> Client Target Reference Lists -> Account Dataset -> No unsupported assumptions.

## Production boundary
The included ICP, account data, and validation results are synthetic capstone assets. Replace client-specific examples in production; preserve the workflow controls.
