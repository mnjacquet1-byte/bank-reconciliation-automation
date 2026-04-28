# Bank Reconciliation Automation

Automated bank reconciliation template built with **Power Query** in Excel. Paste raw data, hit Refresh, and get matched/unmatched transactions instantly.

## What it does

- Loads raw Bank Statement and General Ledger exports
- Cleans dirty data automatically (metadata rows, trailing spaces, date formats)
- Matches transactions by Date + Amount
- Flags unmatched entries from both sides
- Refreshes monthly with one click

## Sheets

| Sheet | Purpose |
|-------|---------|
| Bank Statement | RAW input — paste bank export here |
| GL — Acc. 572 | RAW input — paste ledger export here |
| Bank_reconciliation | Full outer join — all transactions |
| Entries in Bank NOT in GL | Items to post in accounting |
| Entries in GL NOT in Bank | Items to investigate |

## Power Query transformations applied

- Remove metadata rows
- Trim and Clean text columns
- Convert date formats (DD/MM/YYYY vs YYYY-MM-DD)
- Combine Debit/Credit into signed Amount
- Filter out summary rows (Closing Balance)
- Merge queries (Full Outer Join on Date + Amount)
- Anti-joins for unmatched items

## Tools

Excel 365 · Power Query

## How to use monthly

1. Paste new bank statement in the Bank Statement sheet
2. Paste new GL export in the GL sheet
3. Data → Refresh All
4. Review unmatched items
5. Post adjustments → Refresh again

## Author

Mariano Jacquet — [LinkedIn](https://www.linkedin.com/in/marianoaccountant/)
