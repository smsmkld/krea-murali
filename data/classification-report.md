# Suppression and classification report

Input: `data/leads-clean.csv` (1,100 contacts, 877 firms). Rules from CLIENT.md ("Who we never contact"). Original workbook untouched.

## 1. Suppression (`data/suppression-log.csv`)
5 contacts at 3 firms removed before classification:

| Suppressed as | Contacts | Why |
|---|---|---|
| AMCA (amca.co) | 2 | Client instruction "Dont contact AMCA" |
| K.R. Abraham & Co. (krabraham.com) | 2 | Named in onboarding as a client/buyer; CLIENT.md says never name; past clients get a personal note only |
| Harbour Group (harbourgroup.com) | 1 | Same as above |

Matching used exact email domain and firm name, not substrings (a substring match on "amca" wrongly hits Amalgam Capital and Spring Stream Capital). **Judgment call:** K.R. Abraham and Harbour Group were suppressed as past clients because the onboarding form names them as past buyers; say so if Murali wants them kept. **No past-clients export was in the repo**, so the list was built without one (he said he can export it from GoHighLevel). Muncie Business Brokers' "Ralana Abraham" is a different entity and was not suppressed on that rule; she is removed later as a broker.

## 2. How firms were classified
- Fetched the homepage of each firm's website (the Website column, else the email domain): 723 of 874 firms returned a page. Read the title, meta description and body text, plus the contact titles and, where present, the Apollo description in the workbook.
- A category needs phrase evidence in those sources (e.g. "family office", "independent sponsor", "business brokers", "search fund"). Firm name alone is never used. A website that never mentions the firm name is sent to review as a possible wrong entity.
- Where a source list (Axial, ACG profile, firm's own site, 2019 family-office list) types a firm as an independent sponsor and its site describes private investing without fund language, it is typed independent_sponsor at **medium** confidence. Guess-based list tags ("Apollo keyword tag", "Guess from company name") are not relied on.
- `strategic` means an operating company (a manufacturer, software or service company) with no investor or intermediary language. It also covers vendors and service companies. Either way the contact is not a buyer.
- Country: confirmed from the location column or the site's country-code domain. Rows with no country evidence stay `unverified` and are kept; only confirmed non-US rows are removed.

## 3. Counts per category
| Category | Firms | Contacts |
|---|---|---|
| independent_sponsor | 39 | 54 |
| family_office | 85 | 127 |
| private_equity | 101 | 127 |
| search_fund | 2 | 2 |
| broker_or_advisor | 20 | 22 |
| strategic | 73 | 94 |
| unknown | 554 | 669 |

Disposition after rules (firms = 874; contacts = 1095; plus 5 suppressed = 1,100):

| Outcome | Firms | Contacts |
|---|---|---|
| Kept → leads-classified.csv | 121 | 177 |
| Parked → leads-pe-later.csv | 100 | 125 |
| Review → needs-human-review.csv | 527 | 640 |
| Removed: strategic | 71 | 92 |
| Removed: broker/advisor | 20 | 22 |
| Removed: search fund | 2 | 2 |
| Removed: non-US (any category) | 33 | 37 |

Review reasons (firms):

| Reason | Firms |
|---|---|
| Website text has no clear signal. | 261 |
| Website unreachable or has no readable text, and no corroborating evidence. | 163 |
| Mixed signals between categories | 98 |
| Website does not mention the firm name, so it may belong to a different entity (e.g. a sponsor or parent); needs a human check. | 3 |
| Site reads like an operating company, but the firm name suggests an investor; needs a human check. | 2 |

## 4. Files
- `data/leads-classified.csv`: 177 contacts at 121 firms, independent sponsors and family offices, high or medium confidence, US or country unverified.
- `data/leads-pe-later.csv`: 125 contacts, 100 firms. Column `note` flags 82 contacts whose site has no fund language and could be independent sponsors.
- `data/needs-human-review.csv`: 640 contacts, 527 firms (unknown or low confidence; includes non-removed rows with mixed signals).
- `data/classification-removed.csv`: removed rows with the category and reason, so every removal can be checked.
- `data/suppression-log.csv`

## 5. Caveats
- **Only 177 contacts (121 firms) pass.** CLIENT.md targets 400 to 600 contacts for the normal campaign. The gap is mostly 527 firms in review, where the website was missing, JavaScript-only or ambiguous. I did not widen the list by guessing.
- 37 kept contacts are independent sponsors typed from a source list rather than the site's own wording (see `note`). Skim them first; some may be funds (Lazer Properties looks like a property manager).
- Contacts at kept firms still carry `Last email contact` dates in some rows: those were reached before. Not suppressed; decide whether to treat them as warm.
- No size, deal-range or "live deal" test was applied yet; that belongs to scoring.
- Classification is rule-based on keywords, not a human read. Medium-confidence rows are the ones to spot-check.
