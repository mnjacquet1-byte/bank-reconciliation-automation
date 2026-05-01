# Bank reconciliation automation

Automated bank reconciliation template built with **Power Query** in Excel. Paste raw data, hit refresh, and get matched/unmatched transactions instantly.

## What it does

- Loads raw bank statement and General Ledger exports.
- Cleans dirty data automatically (metadata rows, trailing spaces, date formats).
- Matches transactions by date + amount.
- Flags unmatched entries from both sides.
- Refreshes monthly with one click

![Bank Reconciliation Demo](assets/bank-reconciliation-demo.mp4)

## Sheets

| Sheet | Purpose |
|-------|---------|
| Bank Statement | RAW input — paste bank export here |
| GL — Acc. 572 | RAW input — paste ledger export here |
| Bank_reconciliation | Full outer join — all transactions |
| Entries in Bank NOT in GL | Items to post in accounting |
| Entries in GL NOT in Bank | Items to investigate |

## Power Query transformations applied

- Remove metadata rows.
- Trim and clean text columns.
- Convert date formats (DD/MM/YYYY vs YYYY-MM-DD).
- Combine debit/credit into signed amount.
- Filter out summary rows (closing balance).
- Merge queries (full outer join on date + amount).
- Anti-joins for unmatched items.

## Tools

Excel 365 · Power Query.

## How to use monthly

1. Paste new bank statement in the bank statement sheet.
2. Paste new GL export in the GL sheet.
3. Data → refresh all.
4. Review unmatched items.
5. Post adjustments → refresh again.

## Author

Mariano Jacquet — [LinkedIn](https://www.linkedin.com/in/marianoaccountant/)
