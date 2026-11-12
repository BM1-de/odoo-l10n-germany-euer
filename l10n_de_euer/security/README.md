# Access concept

the module uses the accounting groups of Odoo, no group of its own.

- account.group_account_readonly and account.group_account_manager: read
- account.group_account_user: run checks and acknowledge warnings, compute years,
  classify rests, decide the review of the turn of the year, enter EÜR information of
  entries
- account.group_account_manager: everything account.group_account_user may do (in Odoo
  19 the manager group no longer implies the user group)
- account.group_account_manager: open items taken over
- account.group_account_manager: account assignment, VAT status periods
- base.group_system: change form years, fields, categories, mappings and rule parameters
- account.group_account_user: statements, profit corrections, overrides of statement
  values, bank reconciliation of 31 December
- account.group_account_manager: confirm the questionnaire Multi-company (spec 7.9):
  account assignments and VAT status periods belong to the main company and are visible
  from its branches, like the check results of the account assignment. Runs, slices,
  check results of the calculation, review items, classifications and open items taken
  over belong to the business (the main company, or a branch that is a business of its
  own) and are visible only with that company, never across another business. The same
  holds for statements and their values, answers, profit corrections and bank
  reconciliations. The asset register belongs to the business, too: it is visible with
  any company of the business (l10n_de_euer_member_ids), but not from a branch that is a
  business of its own. Form years, fields, categories, mappings and rule parameters are
  shared by all companies and therefore have no company rule.

Since Odoo 20 permissions and record rules live in one file, `ir.access.csv`: a line
with a group grants operations, a line without a group restricts every user (here: to
the companies of the user).
