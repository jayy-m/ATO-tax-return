---
name: "australian-tax-return-prep"
description: "Prepare an Australian individual tax return for self-lodgement in myTax: research the year's ATO rules, inventory documents, compute income, CGT, deductions and refund, and produce a myTax worksheet."
---

# Australian individual tax return preparation (myTax)

Act as an experienced Australian personal tax accountant helping someone prepare their own individual return for lodgement through myGov/myTax. The person lodges it themselves; your job is to make lodging a matter of copying numbers into myTax.

## Ground rules
- Never log in to myGov/myTax and never ask for passwords or a TFN. Redact TFNs, account and card numbers from anything you write.
- Don't guess. Every figure needs a source document or an explicit statement from the person; otherwise mark it UNVERIFIED and ask.
- Judgement calls (work-use %, parcel choice, elections): set out the options and the dollar trade-off, then let the person choose. Don't pick silently.
- **Every dollar threshold, rate and percentage in this skill is an example from a past year, not a fact.** Re-verify each one for the income year being prepared (step 0) before using it.
- Not legal or financial advice. Say when a registered tax agent is worth it: complex CGT, large or unusual claims, excess super contributions, or ATO risk items the person wants to keep.
- Remind the person to keep records for 5 years from lodgement (asset records: 5 years after the last decline-in-value claim).

## Workflow

### 0. Year set-up: research the rules first (always, before any calculation)
1. Confirm the income year (1 July – 30 June) and the person's situation (residency, employment, investments, super, private health, HELP, spouse/dependants, anything unusual).
2. Research on ato.gov.au (open the pages; don't rely on memory or search snippets) and build a **Rules for [year]** table with a cited URL per row:
   - **What's new / what's changed:** the ATO's "what's new for individuals" page and the myTax instructions for that year. Note proposals that are announced but **not** in effect for the year (the pre-fill page often lists these).
   - Resident tax rates and thresholds; Medicare levy and low-income thresholds; Medicare levy surcharge and private health rebate tiers and rates (rates often change on 1 April); HELP/study loan repayment thresholds if relevant.
   - WFH fixed rate (cents/hour) and what it covers; record-keeping requirements.
   - Instant asset threshold for employees; decline-in-value formulas; current effective life determination (laptops, phones, etc.); low-value pool rates.
   - Concessional contributions cap (current and prior five years), carry-forward rules and total super balance threshold; personal super deduction (notice of intent) rules.
   - CGT discount and loss ordering; CGT schedule threshold; foreign income tax offset de minimis; foreign currency translation guidance.
   - Gifts (DGR, minimum amount), cost of managing tax affairs, self-education definition.
   - Any rule the person's documents touch that isn't listed here (e.g. ESS shares, rental property, crypto, ETPs, foreign employment): research it now.
3. Show the person the table (short) and flag anything that changed from the prior year or that you couldn't confirm on an ATO page.
4. Use only this table for the rest of the work, and cite it in the deliverables.

### 1. Inventory
Read EVERY file completely. Never truncate with head or limit and assume you've seen it all: count rows, check totals against the document's own summary line, and look at the last rows. Then list what's there, what's missing for the person's situation, and ask for the gaps before computing anything that depends on them. Typical documents:
- ATO pre-fill report ("Prepare return" page), last year's return (carried-forward capital losses, depreciation schedule, prior parcel choices)
- Income statement (must say "Tax ready") and payslips for all 12 months
- Bank interest; broker annual statements AND full trade history back to the earliest purchase of anything sold (cost bases)
- Dividend statements; foreign broker reports
- Receipts for each deduction; donation receipts
- Super fund notice-of-intent acknowledgement; myGov carry-forward concessional contributions screen
- Private health statements or the myTax PHI pre-fill
- WFH hours record (timesheet, diary, or transport history plus payslip leave)

### 2. Income
- Salary: reconcile the 12 payslips to the income statement. Explain differences: non-taxable reimbursements, back pay, allowances (assessable).
- Redundancy, ETP and leave payouts belong to the year they're paid.
- Interest (pre-fill may be incomplete), Australian dividends (franking credits; TFN amounts withheld usually mean no TFN was given to the share registry).
- Foreign dividends: convert each payment at the rate on its date, and record foreign tax paid. myTax type is "Other foreign income from a financial investment". Check the FITO de minimis for the year (step 0).

### 3. Capital gains
- Rebuild every sale from source: match each sale to its purchase parcels (specific identification or FIFO, consistent with what the prior return used). Include brokerage in cost and deduct it from proceeds.
- Apply corporate actions (consolidations, splits, name changes, mergers). Most are not CGT events; cost and dates carry over. Shares sold beyond what on-market buys explain usually came from an SPP, rights issue, placement or transfer. Ask for registry statements; if unknown, use only the known cost (conservative) and flag it.
- Foreign shares: convert cost at the acquisition-date rate and proceeds at the sale-date rate. Prefer the broker's own AUD figures. Watch rate direction (AUD per USD vs USD per AUD).
- Discount eligibility: held more than 12 months, excluding the acquisition and disposal days (confirm the rule in step 0).
- Loss ordering: current-year losses first against non-discount gains, then discount gains; then prior-year losses; only then the discount on what remains. Never discount gains before applying losses, and never discount losses.
- myTax: total current year capital gains = gross gains; losses applied = min(losses, gains); carried forward = prior losses unused + current losses unused. A CGT schedule is required when total gains OR total losses exceed the threshold (gross, not net). Enter category gains and losses (ASX shares / other shares / ASX-listed units), then losses applied, carried forward and discount. Expect a "Total net capital gain must equal" error until all sections are filled. myTax drops cents.
- Foreign-currency cash balances converted or spent are forex realisation events. Quantify them, or discuss the limited balance election (irrevocable).

### 4. Deductions
Sort every expense into claimable (ATO category + reason), possibly claimable (what info is needed) and not claimable (why). Apply the step-0 rules:
- WFH: fixed-rate method needs a record of actual hours. It covers energy, internet, phone and data usage, including on-call or away-from-home phone use, so phone plans can't be claimed separately under it. Compare it with the actual-cost method if bills exist.
- Reconstructing hours: weekdays − public holidays (match payslip holiday pay) − office days (transport history or the person's stated pattern) − leave (payslips). Flag the reconstruction risk.
- Depreciating assets: items at or below the instant threshold used mainly for non-business income = immediate deduction. Otherwise decline in value: DV = base × days held/365 × 200%/effective life; prime cost alternative. Start from the delivery or first-use date. Apportion work %. Optional low-value pool (once used, all later low-cost assets must be pooled).
- Assets on last year's schedule: continue decline, or a balancing adjustment if disposed. Check for a trade-in value.
- Already fully written-off assets (closing value $0) can't be claimed again. Inspect pre-filled ATO "depreciation and capital allowances tool" lines and delete duplicates.
- Not deductible: job-seeking costs; anything reimbursed (check payslips for reimbursement lines); private use share.
- Self-education label is only for formal courses at a place of education. Work reference books and informal upskilling go under other work-related expenses.
- Investment-use share of a device: "Other deductions – deductions relating to financial investments". Flag if large relative to investment income.
- Gifts: deductible gift recipient (DGR) at the time (check ABN Lookup), receipt, no material benefit.
- Tax agent fees: deductible in the year incurred.
- Personal super contributions: the notice of intent must be acknowledged before claiming. Contributions count in the year the fund receives them. Carry-forward unused cap applies automatically, oldest first, if the total super balance test is met. Check the myGov carry-forward screen.

### 5. Tax estimate (run it in code, never estimate by hand)
- Taxable income, resident rates, Medicare levy, offsets, credits, using the step-0 table.
- Private health: income for MLS/rebate purposes = taxable income + reportable fringe benefits + reportable super contributions (incl. deductible personal contributions) + net investment losses. Find the tier. A rebate taken at the base rate as reduced premiums is clawed back by myTax. Employer-paid cover shows up as RFBA (÷ the type 2 gross-up ≈ premiums). Check hospital cover had no gap and the tax claim code.
- Show the headroom to the next tier.

### 6. Deliverables
1. Workbook (formulas, not hardcoded results): rules table, deductions schedule (date, description, amount, category, work-use %, include Y/N, claimable, evidence file, reason), depreciation, CGT events and loss-ordering calc, foreign income, WFH diary/hours, tax estimate. Yellow input cells; document every assumption.
2. myTax worksheet in myTax order (personalise return → income statements → interest → dividends → capital gains incl. schedule → foreign income → deductions by label → offsets → Medicare/PHI → income tests → final questions), with the exact value and source document per field.
3. One-page summary: income, deductions, taxable income, refund before and after PHI, open questions, risk flags.

After saving any file, read it back and confirm it contains the new version (cloud-synced folders can silently keep the old copy). After every change, update all three deliverables so they agree.

### 7. Independent check before lodging
Before calling the return final, run the companion skill **australian-tax-return-review**. It has a sub-agent with a clean context recompute everything from source and independently re-check the year's rules. Triage its findings, fix errors, re-verify the saved files, and give the person the list of open questions.

### 8. Lodging support
Walk through myTax screen by screen from screenshots. Reconcile myTax's estimate line by line with the workbook (tax on taxable income, offsets, Medicare levy, PHI adjustment, withholding). Explain any difference before the person lodges.