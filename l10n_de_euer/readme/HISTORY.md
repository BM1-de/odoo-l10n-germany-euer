## 20.0.1.0.0 (2026-11-12)

- Migration to Odoo 20.
- Permissions and record rules are in one file now (`security/ir.access.csv`),
  with the same content as before.
- New dependency `mail_tracking`: Odoo 20 keeps the structured log of tracked
  changes in that module.
- The charts of Odoo 20 contain 30 new fixed asset accounts each (accumulated
  depreciation per asset class and a few sub-accounts). They are assigned to
  the category of their base account.
- Changed behaviour, caused by Odoo 20: reversing a bank or cash entry with
  the reversal wizard no longer reconciles the bank lines of entry and
  reversal with each other. A reversal over the turn of the year on a bank
  account that is not reconcilable therefore counts in both years (first
  year plus, second year minus) and C-48 is not raised for it. Reversals
  within one year and reversals on reconcilable accounts are unchanged.
- C-27 follows the renamed payment states (`paid`, `reconciled`).
- Reports: title and information block are handed to the layout the way
  Odoo 20 expects; amounts reach the templates as plain numbers.

## 19.0.1.0.0

- First version for Odoo 19: the forms 2024 to 2026 (*Anlage EÜR*, *AVEÜR*,
  *SZ*) as data with the account assignment for SKR03 and SKR04; the
  computation of a year by the payments, traced over the reconciliations to
  the documents; the asset register with depreciation, low-value assets, asset
  pools and *Anlage AVEÜR*; the statement of the year with questionnaire,
  profit corrections, bank reconciliation of 31 December, checks, finalisation
  with a hash chain and corrections as new versions; the fill-in aid for
  *Mein ELSTER*, the evidence per Kennzahl, the workbook, the list of the
  Kennzahlen, the data set, the data access package Z3, the check protocol and
  the template of the procedure documentation; the setup and takeover
  wizards; the synthetic reference cases PT-01 (small business) and RT-01
  (standard taxation).
