# Australian tax return skills for Claude

Two Claude skills that help prepare an Australian individual tax return for self-lodgement in myTax.

| Skill | What it does |
|---|---|
| `australian-tax-return-prep` | Researches the income year's ATO rules first, inventories your documents, works out income, capital gains, deductions and the expected refund, and produces a workbook, a field-by-field myTax worksheet and a one-page summary. |
| `australian-tax-return-review` | Runs an independent sub-agent with a clean context. It re-checks the year's ATO rules and recomputes everything from your source documents, reporting errors, risky items and gaps. The prep skill calls it before the return is final. |

## Install

- **Claude (claude.ai / desktop app):** zip each skill folder (e.g. `australian-tax-return-prep/` containing `SKILL.md`) and upload it in Claude's skills settings.
- **Claude Code:** copy each folder into `~/.claude/skills/` (personal) or `.claude/skills/` in a project.

Install both: the prep skill refers to the review skill by name.

## Use

Start a conversation with something like: *"Help me prepare my 2026-27 Australian tax return. My documents are in this folder."* Attach or connect your payslips, ATO pre-fill, last year's return, broker statements and receipts.

## Notes

- The skills never log in to myGov/myTax and never ask for your TFN or passwords. You lodge the return yourself.
- Every rate and threshold is looked up on ato.gov.au for the year being prepared, so the assistant needs web access.
- This isn't tax advice. For complex situations, consult a registered tax agent.
- Keep your records for 5 years after lodging.
