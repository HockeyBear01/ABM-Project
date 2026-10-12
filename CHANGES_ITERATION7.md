# Iteration 7 Change Summary

Responds to TargetOrate's (Karen's) feedback on the Iteration 6 workflow. All changes are proposals pending TargetOrate confirmation. Open questions are in `workflow/Competitive_Lock_Gate_Open_Items.md`.

## What changed
- **Competitive Lock Gate.** Locked competitor contracts now affect the recommended tier. Renewal under 12 months: scored normally. 12 to 24 months inclusive: capped at Tier 3. Over 24 months or no date: disqualified. A dissatisfied incumbent moves the account up one band, a satisfied one moves it down one, unknown changes nothing. A cap never raises a tier. CloudBridge moves from Tier 1 to Tier 3 (`examples/CloudBridge_Before_After.md`).
- **New inputs.** Incumbent Contract Status field and a required Scoring As Of Date for every run. C8 wording clarified so "locked" no longer overlaps other bands.
- **AI self review.** After first pass scoring, the AI re derives all 14 criteria for every account and rechecks the math before a human sees anything (`prompts/06_Criterion_Self_Review_Prompt.md`).
- **Human input checkpoint.** Consultants can approve, correct data, supply data, override with evidence, add context, or escalate. The AI rescores and recomputes (`prompts/07_Human_Input_Correction_Prompt.md`, `templates/Human_Review_Input_Template.csv`).
- **One review rule.** Replaces three conflicting rules. Missing Company Name, Industry or Target ACV holds the account. Any other missing value is tested at 2 and at 10; the account goes to a consultant only if the tier differs. Every trigger is justified by four tests (judgment, uncheckable evidence, could flip, costly to be wrong).
- **Review ceiling and sign off.** Proposed ceiling of 25 percent of accounts per run. `Acceptable` accounts skip individual review but the consultant approves them as a group after a 10 percent sampled check (at least 3). Flagged accounts are approved one by one.
- **Metrics relabeled.** 97.5 percent and 98.9 percent are now "rule conformance after author adjudication", not accuracy. 91.1 percent raw agreement is the cleaner figure.
- **Smaller fixes.** Totals ending exactly in .5 round up. C6 can reach 10 with two semicolon separated trigger entries. Output table gains Review Reason and Low/High Bound Tier columns. Input template gains five optional legacy fields.
- **Ground truth removed from scoring data.** `data/20_Company_Dataset_Iteration7.csv` no longer has the answer column (moved to `validation/`). `tools/split_ground_truth.py` does this for new datasets.
- **New test documents.** `validation/Competitive_Lock_Gate_Test_Scenarios.md` (22 gate scenarios), `validation/Failure_Analysis_Template.md`, `validation/Repeatability_Protocol.md`.

## Not done yet
- Regenerate the answer key's review statuses on the 100 company set (the current key sends 10 of 20 to review, above the 25 percent ceiling).
- Commit the Iteration 6 run output with the AI, version and date that produced it.
- Vendor event reference list (Karen said this can follow).
- A running automated workflow, if TargetOrate requires more than a prompt chain used by hand in Claude or ChatGPT.
- Rerun the MVP acceptance test on the Iteration 7 toolkit.

## Ask Karen
Gate boundaries and satisfaction rule, whether production data has a lock indicator, the 25 percent ceiling and 10 percent sample, the .5 rounding rule, two triggers per account, running workflow expectations, and what commercialization means.
