# Iteration 7 Change Summary

Responds to Karen's feedback. All changes are proposals pending TargetOrate. Open questions: `workflow/Competitive_Lock_Gate_Open_Items.md`.

## What changed
- **Competitive lock gate:** under 12 months to renewal scores normally, 12 to 24 months is capped at Tier 3, over 24 months or no date is disqualified. Dissatisfied moves up a band, satisfied moves down. CloudBridge drops from Tier 1 to Tier 3.
- **New inputs:** Incumbent Contract Status and a required Scoring As Of Date.
- **AI self review:** the AI re derives all 14 criteria per account before a human sees results.
- **Human input checkpoint:** consultants approve, correct, supply data, override with evidence, or escalate; the AI rescores.
- **One review rule:** replaces three conflicting rules. Missing Company Name, Industry or ACV holds the account. Other missing values go to a consultant only if the tier changes between a value of 2 and 10. Ceiling of 25 percent of accounts per run; 10 percent sampled check of the rest; consultants still approve every tier.
- **Metrics relabeled:** 97.5 and 98.9 percent are "rule conformance after author adjudication", not accuracy.
- **Smaller fixes:** .5 rounds up, C6 can reach 10, new review columns in the output, ground truth moved out of the scoring data (`tools/split_ground_truth.py`).
- **New test documents:** 22 gate scenarios, failure analysis template, repeatability protocol.

## Not done yet
- Regenerate review statuses on the 100 company set.
- Commit Iteration 6 run output with AI, version and date.
- Vendor event list; running automated workflow (if required); rerun the MVP acceptance test.

## Ask Karen
Gate boundaries and satisfaction rule, lock indicator in production data, 25 percent ceiling and 10 percent sample, .5 rounding, two triggers per account, running workflow expectations, meaning of commercialization.
