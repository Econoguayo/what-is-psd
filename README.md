# Coding annex — additionality in World Bank private sector operations, FY24–25

This repository holds the per-operation coding record behind Section III of "The Exempt Window: A Rule for World Bank Private Sector Subsidies" (Center for Global Development). The paper reads the appraisal documents of the Bank's reported private sector portfolio against a three-hurdle additionality test and reports how many of the operations that place Bank capital in a commercially supplied market can demonstrate, from their own documents, what that capital purchased. This annex is the record on which those counts rest.

## What the file contains

`PSD_coding_annex_FY24-25.xlsx` carries two sheets.

**`Adjudication`** holds one row for each of the 122 operations that carry theme code 120000 as a major theme in fiscal years 2024 and 2025 and that have a publicly disclosed appraisal-stage document. Sixteen columns record, for each operation, its identifier, country, name, fiscal year, instrument, and commitment; the basis on which the commitment amount was taken; the gate decision, which records whether the operation is substantially a private sector operation; the verdict returned by the deterministic application of the protocol, together with the hurdles at which it failed; the result of an independent machine reading; the source of any adjudication that departed from the deterministic verdict; the final verdict, the first hurdle at which the operation failed, and the failure mode; and the market failure that the appraisal itself names.

**`Summary`** recomputes a set of totals from the `Adjudication` sheet and carries the change log for the workbook's version chain.

## How the workbook's totals relate to the paper's

**The `Summary` sheet does not report the paper's frame, and a reader should not expect it to.** It computes over all 122 coded operations under the protocol as it stood on 24 July 2026, before the amendments described below, and it reports 48 failures, 26 passes and 48 gated-out operations at a failure rate of 64.9 percent. The paper reports a smaller frame and a different rate. The difference is not a correction of any verdict; it is the effect of four rules adopted after the coding was complete, each of which removes operations from the denominator without changing what any appraisal was found to contain.

The chain from the workbook to the paper runs as follows.

| Step | Operations | Rule |
|---|---|---|
| Coded in this workbook | 122 | Theme code 120000 as a major theme, FY24–25, disclosed appraisal-stage document |
| Less operations coded from a Project Information Document | 111 | Step 0, the protocol-eligibility sweep: the protocol excludes that document type by name |
| Less operations that are not substantially private sector | 68 | The gate |
| Less budget support and results-based lending | 45 | Clause A: these operations are governed by the rule-writing test rather than by the three hurdles |
| Less operations placing no Bank capital in a commercially supplied market | 35 | Clause B, measured at component level in the companion census |
| Less operations carrying no Bank commitment | 29 | Amendment 6 (M6): financing recorded under Non-World Bank Group Financing is not Bank commitment |

Of the 35 operations at the second-to-last step, 27 cannot demonstrate additionality. The final row is the frame the paper reports: 29 operations enter a commercially supplied market and 21 of them cannot demonstrate additionality. P173890 is counted as entering on its 29.6 percent upper-bound commercial share, and it leaves the frame at the final row under M6.

## What is not in this file

The annex is deposited as a set. This workbook carries the author's per-operation verdicts and nothing else, and three further records are required to reproduce what the paper reports.

- **The component-level commercial-share census.** The measurement of how much of each operation's commitment enters a commercially supplied market is held separately, in `clauseB_operations.csv` (60 operations) and `clauseB_components.csv` (382 components with paragraph citations). The Clause B step in the table above cannot be reproduced without them.
- **The reliability record.** The paper reports four independent readings of a 30-operation subsample, with agreement statistics and bootstrap intervals. Those readings are held in `claude_second_coding_P30.csv` and `verdict_template_completed.xlsx`. Table III-1 cannot be reproduced from this workbook.
- **The gate rule as applied.** An operation is treated as entering a commercially supplied market unless both its measured entering amount and its upper-bound commercial share are zero. The rule is not stated in the workbook and must be read from this file.

Three adjudications applied after this version of the workbook was saved are also not reflected in its cells: the instrument for P509948 is Development Policy Lending; the verdict for P505177 is Gated out; and the verdicts for P178254 and P505241 are Fail. Their hurdles and failure modes should be recorded here alongside them.

## Provenance and method

Operations were identified through the World Bank Projects API and appraisal documents retrieved through the Bank's Documents and Reports API. Each operation was read by hand against the financing-rationale passage of its appraisal. The coding protocol, the dated addendum of 20 July 2026 that defines budget-support treatment and the "substantially private sector" threshold, and the amendments that govern the commitment basis are described in the paper and in its protocol amendment register.

The paper states that the level of the count is sensitive to the reader and that its direction is not. That claim is testable against the reliability files named above, and the annex is deposited so that it can be tested.

## Citation and correspondence

Cite the paper rather than this repository. Discrepancies between the workbook and the figures printed in the paper are worth reporting, and a note of what was checked, which file was used, and which figure did not reconcile is more useful than a general report of disagreement.
