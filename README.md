# Kalyan Pathlab Business

Mobile-first PWA for pathology lab billing and business management.

## Calculation rules
- Multiple tests can be added to one bill.
- Total MRP = sum of test MRPs.
- Total B2B = sum of test B2B rates.
- B2C = one patient collection for the whole bill.
- Collection Charges = one bill-level charge.
- Report Charges = one bill-level charge.
- Discount = Total MRP - Total B2C.
- Profit = Total B2C - Total B2B - Collection Charges - Report Charges.

## Test Master
Add tests manually or import Excel with columns: `Test Name`, `MRP`, `B2B Rate`.
Typing a test name in New Bill or Edit Bill searches the Test Master and fetches MRP/B2B.

## Data
Billing/Test Master data is stored locally in the browser using localStorage. Keep regular Excel backups.
