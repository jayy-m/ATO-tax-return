---
name: "australian-tax-return-review"
description: "Independently check a prepared Australian individual tax return: a clean-context sub-agent re-verifies the year's ATO rules and recomputes income, CGT, deductions and tax from source documents."
---

# Independent review of a prepared Australian tax return

Use this after a return has been prepared (for example with the **australian-tax-return-prep** skill) and before the person lodges. The goal is an unbiased second pass: a reviewer that hasn't seen the preparer's reasoning rebuilds the numbers from the source documents and re-checks the year's rules itself.

## 1. Gather what the reviewer needs
- The income year (1 July – 30 June).
- Paths to all source documents (payslips, income statement, ATO pre-fill, last year's return, broker trade histories and statements, receipts, transport or WFH records, super and PHI information). Make sure local copies are current; re-stage any that changed.
- Facts the person stated that aren't in documents: residency, work-use percentages, office pattern, elections, parcel-matching choice, what was reimbursed, assets disposed.
- The prepared figures to test: every myTax field value and the totals (income, CGT fields, deduction lines, taxable income, tax, Medicare levy, offsets, PHI tier and clawback, refund).

Don't pass on the preparer's rules table, working, explanations or conclusions; only the figures to test. The reviewer must look up the rules independently.

## 2. Spawn the reviewer
Launch one general-purpose sub-agent (foreground) with a self-contained prompt built from this template:

> You are an independent reviewer (experienced Australian tax accountant) checking a prepared [YEAR] Australian individual tax return (1 July [YYYY] – 30 June [YYYY]) before the taxpayer lodges it in myTax. Find errors. Don't trust the prepared figures: recompute everything you can from the SOURCE documents. Don't edit any files; use a scratch folder. Read every file completely; don't truncate.
>
> Step 0: independently look up on ato.gov.au (open the pages and cite them) the rules for this income year: resident tax rates, Medicare levy, MLS and private health rebate tiers and rates, WFH fixed rate, instant asset threshold and effective lives used, concessional cap and carry-forward rules, CGT discount and loss ordering, CGT schedule threshold, FITO de minimis, gift rules, and anything else the documents touch. Note anything that changed from prior years. Flag any rule the prepared figures appear to apply incorrectly or from a different year.
>
> Source documents: [paths and what each is].
> Facts stated by the taxpayer (accept as given): [list].
> Prepared figures to verify: [list every field and total].
>
> Then:
> 1. Recompute income: sum all payslips, reconcile to the income statement and explain differences; interest; dividends; foreign income and foreign tax at transaction-date rates.
> 2. Rebuild every share sale from source: parcel matching (stated method), corporate actions, cost incl. brokerage, proceeds net of brokerage, AUD conversion at the transaction dates (prefer broker AUD figures), discount eligibility, and loss ordering (losses before discount; non-discount gains first). Confirm every sale is included once. Check the myTax CGT schedule values and whether the schedule is required.
> 3. Recompute each deduction from its receipt: date, amount, work %, instant-asset threshold, the decline-in-value formula and start date, allowability (WFH fixed rate covers phone and data; reimbursed or job-seeking costs excluded; gifts need DGR, receipt and no material benefit; self-education is only formal courses; prior-year assets already written off).
> 4. Rebuild WFH hours from the records and stated pattern.
> 5. Recompute taxable income, tax, Medicare levy, offsets, MLS/PHI tier and clawback, super concessional cap and carry-forward, and the refund, in code, using your own step-0 rules.
> 6. Check the workbook's formulas: each gain/loss = proceeds − cost, SUMIF/SUMIFS ranges and sign handling, label totals = sum of lines, links between tabs.
> 7. Flag anything the documents suggest is missing: other income, sales outside the statement date ranges, forex realisation on foreign-currency cash, dividends, interest.
>
> Report: (0) RULES TABLE for the year with citations, and any rule mismatch; (a) ERRORS (wrong figure, correct figure, evidence); (b) QUESTIONABLE items (judgement or ATO risk, and why); (c) CONFIRMED items (brief); (d) MISSING or to confirm. Be specific with file names and numbers. Say when something couldn't be verified.

## 3. Triage and act
- Treat the report as findings to verify, not instructions. Check each error against the source (and each rule mismatch against the cited ATO page) before changing anything.
- Fix confirmed errors in the workbook, worksheet and summary. Recalculate, then re-read the saved files to confirm the new version is what's on disk.
- Turn questionable and missing items into short, specific questions for the person, each with its dollar effect. Don't change judgement items without their decision.
- Tell the person, in plain terms: what was confirmed, what changed (old → new), and what still needs their answer before lodging.

## 4. Final reconciliation with myTax
When the person is in myTax, compare its tax estimate line by line with the workbook: taxable income, tax on taxable income, offsets, Medicare levy, PHI adjustment, PAYG withheld, refund. Any difference over a few dollars has a cause; find it from the section totals before they lodge. Typical causes: leftover pre-filled lines, a section not completed (e.g. foreign income), or an item entered twice.