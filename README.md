# Kalyan Pathlab Business

Mobile-first PWA for pathology lab billing and business management, redesigned to match the reference mockups.

## Screens (bottom nav)
- **Dashboard** — Today's Summary (Bills, B2C, B2B, Today's Profit) + Monthly Summary card.
- **New Bill** — Bill No. (auto), Date, Patient Name, test search/add, auto Total MRP / Total B2B, B2C Amount, Collection Charges, Report Charges, auto Discount, auto Profit, Save Bill.
- **Bills** — search by patient/bill no., From/To date range, All / Today / This Month quick tabs. Tap a bill to open **Bill Details** (view, with Edit/Delete) → **Edit Bill** (change tests, amounts, and recalculate).
- **Reports** — Daily / Monthly / Business tabs (Monthly has a month navigator), Export to Excel.
- **More** — Test Master, Profit Analysis, Import Tests from Excel, Export Test Master, Export All Bills, About.

## Profit Analysis tab (More → Profit Analysis)
Dedicated tab with a period selector (Today / This Month / All Time / Custom range), the calculation formula, and a full breakdown: Bills, Total MRP, Total B2C, Total B2B, Collection Charges, Report Charges, Total Discount, Net Profit, and Profit Margin %, plus a simple visual comparison bar for B2C vs B2B vs Profit.

## Adding multiple tests to one bill
In New Bill / Edit Bill, search and add tests one after another — each added test becomes its own editable line with:
- Test Name
- MRP
- B2C (customer charge, with discount already applied)
- B2B (business-to-business cost)
- Collection Charges
- Report Charges
- Line Profit = B2C − B2B − Collection − Report (auto)

Once all tests are added, the bill automatically totals every column (Total MRP, Total B2C, Total B2B, Total Collection, Total Report, Discount) and shows the **Final Profit** for the whole bill.

## Calculation rules
- Total MRP = sum of each test line's MRP.
- Total B2C = sum of each test line's B2C.
- Total B2B = sum of each test line's B2B.
- Total Collection Charges = sum of each test line's collection charge.
- Total Report Charges = sum of each test line's report charge.
- Discount = Total MRP − Total B2C.
- Final Profit = Total B2C − Total B2B − Total Collection Charges − Total Report Charges.

## Test Master
Test Master stores just **Test Name, B2C, B2B** for each test. Add/update a test with the Save Test form, or import a "Test Master" Excel file (Test Master → Import from Excel, or More → Import Tests) with columns: `Test Name`, `B2C`, `B2B`. Export the current master anytime as `Test_Master.xlsx`.

Typing a test name in New Bill or Edit Bill searches the Test Master and adds a new line pre-filled with that test's B2C and B2B (MRP defaults to the B2C value) — every field stays editable per line so charges can be adjusted per patient/bill. Tap a test row in Test Master to load it back into the form for editing.

## Navigation
Tapping the logo/app name in the top bar from any main screen takes you back to the Dashboard (Home).

## Duplicate protection
- Test Master never stores two tests with the same name — saving a name that already exists updates that test instead of creating a duplicate row.
- A test can only be added once per bill — trying to add the same test twice to one bill shows a warning instead of adding a second line.

## Sharing a bill (WhatsApp / Email)
As soon as a bill is saved (or updated), the app opens **Bill Details**, where you'll find **WhatsApp** and **Email** buttons:
- **WhatsApp** opens `wa.me` with the bill (patient, tests, amount) pre-filled as a message — pick the patient's contact to send it.
- **Email** opens your mail app with the same bill pre-filled in the body, and automatically CCs the lab's own email (`kalyan.pathlab.21@gmail.com`) so a copy is kept for records — just add the patient's email as the recipient.

The lab's contact details (WhatsApp **+91 98700 20674**, email **kalyan.pathlab.21@gmail.com**) are included at the bottom of every shared bill.

## Install on mobile
The app is a installable PWA. Go to **More → About / Contact → Install App** to add it to your phone's home screen (Android/desktop Chrome shows a one-tap install; iPhone Safari: tap Share → "Add to Home Screen"). Once installed it opens full-screen, like a native app, and still works offline for already-loaded data.

## Credits
Developed by **Swapnil Mokal**. © 2026 Swapnil Mokal. All rights reserved. See **More → About / Contact** in the app.

## Language
The app UI is in English by default.

## Icons
All icons (navigation, buttons, stat cards) are original, hand-drawn SVG icons built specifically for this app — no third-party icon packs or logos are used, so there are no copyright/licensing concerns.

## Data
Billing/Test Master data is stored locally in the browser using localStorage. Keep regular Excel backups (Bills → ⋮ icon, or More → Export All Bills / Export Test Master).
