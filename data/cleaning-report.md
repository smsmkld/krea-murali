# Cleaning report: leads-clean.csv

**Source:** `client-inputs/Krea_Buyer_Master_List_v2.xlsx`, sheet "Outreach contacts" (original not modified).
Note: `inputs/leads.xlsx` does not exist in the repo; this workbook is the only spreadsheet and its Outreach sheet matches the ~1,500-contact list described in CLIENT.md.
**Output:** `data/leads-clean.csv`

## Workbook sheets
| Sheet | Rows (excl. header) | Columns |
|---|---|---|
| Combined buyers | 1,975 | 23 (firm-level, with DM1/DM2) |
| **Outreach contacts** | **1,534** | 17, one row per contact (used) |
| Decision makers | 435 | 12 |
| Axial (no search funds) | 211 | 10 |
| IS directory criteria | 63 | 14 |
| Summary | 40 | 3 |

## Outreach contacts: column map
| Field | Column(s) |
|---|---|
| Name | `First name`, `Last name` |
| Email | `Email` |
| Firm | `Firm` |
| Title | `Title` |
| Website | `Website` |
| Location | `Location` |
| Other | Company type, Type basis, Source, Contact found via, Email status, Personal email?, LinkedIn, Deal(s) they saw, Last email contact, Apollo check |

## Audit (before cleaning)
- Rows: **1,534**
- Missing email: **0**
- Missing firm: **434** (all are personal-email contacts; `Personal email?` = Yes on 434 rows)
- Missing title: **1,149**
- Also missing: last name 48, website 435, location 1,158
- Duplicate emails: **0**
- Duplicate firms: 877 distinct firms among the 1,100 rows that have one; **196 firms have 2+ contacts (419 rows)**

## What was done
1. Trimmed and collapsed whitespace in every field; blanks set to empty. Emails lowercased.
2. Fixed capitalization of first and last names that were all-lower or all-upper (158 values), handling Mc/O' and hyphens. Initials of 3 letters or fewer (e.g. JD) were left alone.
3. Dropped rows with no firm (434) or no email (0). Rows kept: **1,100**.
4. Deduped by email: **0** removed.
5. Added `firm_id` (F0001... from the normalized firm name), `firm_contact_count` and `multi_contact_firm` (Yes/No). No multi-contact rows were deleted.

## Result
- **1,100 rows, 877 firms**, 196 firms flagged multi-contact (419 rows).

| Company type | Rows |
|---|---|
| Unknown (company email) | 575 |
| Family Office | 244 |
| Independent Sponsor | 150 |
| Private Equity Fund | 96 |
| Corporation | 22 |
| Holding Company | 6 |
| Venture Capital | 4 |
| Lender / mezzanine | 3 |

## Problems to handle before classification and scoring
- **The list is not mostly buyers.** 575 rows (52%) are "Unknown (company email)". Source for 670 rows is Outlook (direct replies, BizBuySell, BusinessBroker.net, DealStream), so many are likely sellers, brokers, vendors or inbound contacts, not buyers. They need classification and will mostly fail the CLIENT.md qualification rules.
- **~603 "firms" are just domains** (e.g. `thermofisher.com`, `amat.com`), because the firm was filled from the email domain. Their `firm_id` groups by domain, and several are large corporates (strategic acquirers/corp dev: never contact).
- **Messy name fields:** some first names hold an email address or role mailbox (e.g. `info@`, `postmaster@`), or a single initial. These were not rewritten; flag them in classification.
- **Title is blank on 715 of the 1,100 kept rows**, and Email status is blank on the same 715. Seniority can't be judged for them.
- **Not yet applied:** suppression (AMCA, past clients, search funds, brokers, large PE), classification, scoring. PE rows (96) should go to a separate file rather than be scored.
- The 434 dropped rows were not deleted from the source. If any are valuable (personal-email independent sponsors), they would need a firm added by hand.
