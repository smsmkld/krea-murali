# Lead sourcing filter sheet: independent sponsors and family offices for Murali

Goal: source new independent sponsors (IS) and family offices (FO) that fit Murali's rules, then hand the domain list to Claude for the site check, names and scoring. Nothing here sends anything.

Rule of thumb: pull wide, filter hard. Most of the first pull will fail the buyer test; plan for roughly 4,000 to 6,000 raw domains per 1,000 verified sponsor firms, and more for family offices (estimate from our sample of 150: about 45% of sponsors and about 25% of family offices showed clear buying evidence).

---

## 0. The gate every lead must pass (from CLIENT.md and Murali's long message)

| # | Check | Pass rule |
|---|---|---|
| 1 | Type | Independent sponsor or family office. PE goes to a separate parked file (only with Murali's approval, max 10 in the Dream list) |
| 2 | Country | US-based |
| 3 | Never contact | No search funds, first-time searchers, brokers or intermediaries posing as buyers, strategic buyers with corp dev, contingency-only buyers, large PE with in-house deal teams, SBA-financed or under-$1M-revenue buys, AMCA, past clients, personal-email people |
| 4 | Buys operating companies itself | Portfolio page lists operating businesses, OR a news item "[firm] acquires", OR an independent sponsor describing itself that way. Funds, real estate and startup-only investors fail |
| 5 | Deal size | Targets roughly $3M to $50M revenue and $1M to $8M EBITDA |
| 6 | Lean team | Best fit: no associates or analysts, under 10 people |
| 7 | Decision maker | Sponsors: Founder, Managing Partner, Principal. Family offices: CIO, Director of Private Investments, Managing Director (Principal also accepted) |
| 8 | Priority boosts | Deal in the last 18 months or "currently looking"; West/California focus; manufacturing, distribution or trades match |

Statuses used in our sheets: A = confirmed buyer (proof link), B = needs manual check, C = probably not a buyer. Score tiers: A 75+, B 55 to 74, C below 55.

---

## 1. Crunchbase (paid plan, use the export, do not scrape)

Crunchbase field names can differ slightly by plan; adjust to what your plan shows. Run two separate searches.

### 1a. Independent sponsors and small PE-style buyers (Organizations search)
- Organization Type / Investor Type: Private Equity Firm
- Investment Stage: Private Equity (NOT Seed, Early Stage Venture or Late Stage Venture)
- Headquarters Location: United States (run again with California, Washington, Oregon, Arizona, Colorado, Utah, Nevada for the West priority list)
- Number of Employees: 1 to 10, then 11 to 50 (skip 51+, they usually have in-house teams)
- Number of Investments: 1 or more
- Description keywords (any): independent sponsor, deal-by-deal, fundless, lower middle market, founder-owned, family-owned, buyout, majority, acquire
- Exclude keywords: venture, seed, startup, crypto, real estate, fund of funds, search fund, SPAC, wealth management, investment banking, M&A advisory, consulting
- Last activity within 24 months if the field is available (use the most recent investment or acquisition date)

### 1b. Family offices (Organizations search)
- Investor Type: Family Investment Office
- Headquarters Location: United States
- Number of Employees: 1 to 50
- Number of Investments: 1 or more
- Description keywords (any): direct investments, operating companies, control, majority, acquire, holding company, manufacturing, distribution, industrial, services
- Exclude keywords: venture, seed, startup, crypto, real estate only, hedge fund, wealth management, multi-family office, RIA

### Export columns to request
Organization name, website, description, location, number of employees, investor type, number of investments, last investment date, LinkedIn URL (for reference only, do not scrape it).

Crunchbase leans toward venture. Expect to drop 40% to 60% of rows on the keyword and website check.

---

## 2. Public listings and databases (manual lookups, exports or paid access; read each site's terms first)

| Source | What it gives | How to use it | Notes |
|---|---|---|---|
| SBIA independent sponsor deals page (smallbusinessinvestoralliance.growthzoneapp.com/independent-sponsor-deals) | Deal announcements naming the sponsor, the target and the advisor | Collect sponsor names from every deal; each one is a sponsor with a proven deal | Public pages. Good proof of buying |
| McGuireWoods Business & Private Equity directory and "Independent Sponsor Spotlight" series (bpe.mcguirewoods.com, mcguirewoods.com) | Sponsor names, focus, sometimes the principal's name | Pull sponsor and family-office names from the directory and the spotlight interviews | Interviews name the founder |
| LP Legal "Independent Sponsor Series" interviews | Sponsor, principal, criteria | Pull name, criteria, size range | Gives deal-size fit directly |
| Sadis & Goldberg "Earnout" newsletter and ISS attendee book (issuu) | Attendee lists from the independent sponsor conferences | Extract firm names | PDF; manual or copy-paste |
| Cassel Salpeter sponsor reports | State sponsor lists (for example Florida) | Extract firm names | Good for state-by-state sweeps |
| iGlobal Forum (events.iglobalforum.com) speaker, sponsor and agenda pages | Sponsors and capital providers speaking at independent sponsor events | Extract firm names; drop capital providers and service firms | Mixed list: filter by the gate |
| PR Newswire, Business Wire, GlobeNewswire, PE Hub, PE Professional, Citybiz | "[firm] acquires [company]" releases | Search the phrase "independent sponsor" or "family office" with acquires; collect the buyer | Best live-deal signal; date is on the release |
| PrivSource (privsource.com) and Mergr (mergr.com) investor and deal pages | Buyer profiles with deal lists | Check a firm's deals; useful to confirm "buys operating companies" | Aggregator terms: manual use or a paid plan |
| SEC EDGAR: Form D (full-text search) | Filings by sponsors raising deal-specific capital, with the named related persons | Search "independent sponsor" and "Form D", collect issuer and related persons | Free, official, structured |
| SEC IAPD / Form ADV | Registered advisers and exempt reporting advisers, including some family offices | Filter by state and "private fund adviser" | Use to confirm legitimacy |
| State secretary of state filings | Entity names and managers | Look up a firm to find the organizer or managing member when a site names no one | Manual |
| ACG chapter and SBIA member or event pages | Chapter sponsors and attendees | Extract firm names by region | West chapters first (LA, San Diego, Bay Area, Seattle, Denver, Phoenix) |
| Calder-style "acquisition criteria" pages on buyers' own sites | Stated revenue and EBITDA ranges | Use for the size check | Own-site proof |

---

## 3. Axial (axial.net)

Axial is the largest independent sponsor and buyer marketplace. Its public directory pages are organised by state, city and sector (for example "California independent sponsors", "Austin independent sponsors").

- Read Axial's terms of use before collecting anything in bulk. robots.txt permits fetching public company pages, but the terms may still restrict automated collection. If in doubt, collect manually or ask Axial about a data arrangement.
- Useful public fields on a company page: type (Independent Sponsor, Family Office, Private Equity), headquarters, stated EBITDA and revenue criteria, sectors, closed-deal count, a short description.
- Filters to apply when browsing:
  - Type: Independent Sponsor, then Family Office
  - Location: United States (browse California, Washington, Oregon, Arizona, Colorado, Utah, Nevada first)
  - Sector: industrials, manufacturing, distribution, business services, healthcare services, trades
  - Criteria: EBITDA overlapping $1M to $8M, revenue overlapping $3M to $50M
- Skip profiles that say search fund or searcher, M&A advisory, capital provider, or lender.
- Treat an Axial listing as "likely a buyer", not proof. Closed deals shown on the profile count as evidence; "0 closed deals" stays in status B until a deal is found.

---

## 4. Other sites with the same buyer profiles

| Site | What it has | Use |
|---|---|---|
| Altss (altss.com) | Family office and investor profiles | Find single-family and multi-family offices; verify with the firm's own site |
| PremierAlts | Investor profiles with deal history | Cross-check deal counts |
| TeaserClub | Investor mandates and criteria | Find buyers stating a size range |
| Praxisrock and Venture Capital Archive blogs | Lists of active family offices by city | Seed lists of firm names |
| privateequityinfo.com directory | PE and portfolio listings | Confirm owned companies |
| CT Acquisitions directory | Buyer profiles | Mandates and criteria |
| Dealroom, CB Insights, PitchBook, Preqin, Grata, SourceScrub, FINTRX | Deal history and family office data | Paid; best way to settle "buys operating companies" without manual searching |
| Firm-owned "acquisition criteria" or "for sellers" pages | Own-site proof | Strongest evidence of an operating-company buyer |

Do not use sites that list sellers (BizBuySell, BizQuest, DealStream) as buyer sources.

---

## 5. Apollo filters (use after you have domains; Apollo is for filtering and email, not for deciding who is a buyer)

Apollo's industry tags were unreliable in our data, so every Apollo result still goes through the site check.

### 5a. Company filters
- Company headcount: 1 to 25 (start at 1 to 10)
- Location (HQ): United States. Create a second saved search for California, Washington, Oregon, Arizona, Colorado, Utah, Nevada
- Industry: Venture Capital & Private Equity, Investment Management, Financial Services
- Keywords (include any): independent sponsor, deal-by-deal, family office, lower middle market, founder-owned, acquire, buyout
- Keywords (exclude): search fund, venture capital, real estate, wealth management, RIA, investment banking, M&A advisory, broker, consulting, staffing, SPAC, fund of funds, crypto
- Upload your domain list as "Company domains" to enrich and filter in place
- Exclude: companies already in your account lists, Murali's suppression list, AMCA, K.R. Abraham, Harbour Group, Krea

### 5b. People filters
- Job titles (include): Founder, Co-Founder, Managing Partner, Managing Director, Principal, Partner, President, Chief Investment Officer, Director of Private Investments, Owner
- Job titles (exclude): Associate, Analyst, Vice President (unless Murali approves VP entry points for PE), Intern, Assistant, Recruiter, Investor Relations, Marketing, Operations Associate
- Seniority: Founder, Owner, Partner, C-Suite, Director
- Email status: Verified (also keep "Likely to engage" off; verification is what matters)
- Exclude personal-email domains (gmail, yahoo, hotmail, outlook, aol, icloud)
- One primary contact per firm for the Dream list; a secondary in a separate column

### 5c. Export columns
Company, domain, website, headcount, HQ city and state, first name, last name, title, email, email status, LinkedIn URL (reference only).

---

## 6. Other ways to get data

1. Murali's own network: past buyers from his CIM and valuation work, referrals from the two buyers who later hired him, and anyone who signed an NDA on his listings (the Outreach contacts sheet records "NDA" in the deal column). These are the warmest and best-qualified leads.
2. Murali's Axial teaser activity (members who opened or received teasers).
3. Intermediaries: M&A advisors and lenders often publish "our buyers" or "capital partners" pages. Ask Murali's banker and broker contacts for buyer introductions.
4. Conference speaker, sponsor and attendee pages (iGlobal Forum, ACG, SBIA, family office forums).
5. Podcasts and webinars hosted for independent sponsors (guest lists).
6. Portfolio-company footers ("a portfolio company of [firm]") on recently acquired small companies.
7. Press release alerts: set alerts for "independent sponsor acquires", "family office acquires", "majority investment" with manufacturing, distribution and services; each release names a buyer with a fresh deal.
8. SEC Form D and ADV filings (see section 2).
9. Trade association member lists (SBIA, ACG chapters).
10. LinkedIn Sales Navigator used through its own interface and lead lists, for finding the decision maker at a known firm (do not scrape it).
11. Firm websites: contact and team pages are the source for the decision maker's name when Apollo has none.

---

## 7. Dedupe, suppress, verify

1. Normalise domains (lowercase, remove www and paths) and dedupe across all sources.
2. Remove anything already in data/leads-clean.csv, data/dream100-monday-100.csv and data/dream100-needs-check.csv unless you want to re-check it.
3. Remove suppressed firms: AMCA, K.R. Abraham & Co., Harbour Group, Krea Business, past clients (export pending).
4. Remove personal-email contacts and any address that is not a company domain.
5. Verify every email with a verifier before sending. Never guess an email address; if it is missing write "needs lookup".
6. Keep Dream list firms out of the normal campaign so nobody is emailed twice.

---

## 8. Hand-off spec for Claude (CSV)

One row per firm, columns: firm, domain, website, type_guess (independent_sponsor or family_office), source, source_url, hq_city, hq_state, employees, first_name, last_name, title, email, email_status.

Claude then returns: site status (up, down, login, robots), buyer evidence A/B/C with proof link, team flag, decision maker name and title (from the team page), West/California flag, deal-size fit, recent deal date, and the A/B/C score.

---

## 9. Yield tracking (fill in as you go)

| Source | Raw domains | After dedupe and suppression | Site reachable | A (confirmed buyer) | B | C | Verified emails | Notes |
|---|---|---|---|---|---|---|---|---|

Use the yield table to decide which sources to keep pulling and which to drop.

---

## 10. Compliance reminders (not legal advice)
- Use official exports, APIs and paid plans. Do not bulk-scrape LinkedIn, Crunchbase, Apollo, Axial or Google News.
- Respect robots.txt on firm sites and skip login pages.
- US-only targeting. Every email needs an unsubscribe option and the sender's physical address.
- Keep contact data private and inside the project.
