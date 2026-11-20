# Domain sourcing research: what works, what is blocked, and how to reach 3,000+ domains

Date: Nov 20, 2026. Goal: at least 3,000 raw domains of independent sponsors (IS) and family offices (FO) to send to Claude for filtering before Apollo.

## 1. What I tested (robots.txt, terms, and whether the page is fetchable)

| Source | Result | Verdict |
|---|---|---|
| Axial | robots.txt allows public pages, but a plain fetch returned HTTP 403 and no terms page was found | Not usable for bulk collection. Browse manually or ask Axial about a data arrangement |
| Altss | Page loads, but the terms prohibit "systematically extract, download, store or archive substantial portions" | Do not scrape |
| PremierAlts | Terms have a section "Prohibited Uses - Data Scraping and Automated Access"; deal pages returned 403 | Do not scrape |
| Mergr | Terms prohibit scraping, crawling and bulk downloading; pages returned 403 | Do not scrape |
| Praxisrock | Terms prohibit scraping and automated tools | Do not scrape |
| TeaserClub | Rate-limited (HTTP 429); terms do not mention automation | Manual lookups only |
| SBIA deals page | Returned HTTP 403 | Not usable by script; use by hand |
| PrivSource | Buyer lists sit behind a paid product (login and pricing) | Paid only |
| McGuireWoods BPE directory | It is a directory of individual professionals, not firms | Not a firm source |
| privateequityinfo.com | Pages load; the directory index has no crawlable list | Single lookups only |
| CT Acquisitions directory (ctacquisitions.com/directory) | One public page with about 950 firm profiles, robots.txt allows it, terms say nothing about automation | Usable with a polite crawler (1 request per second) |
| SEC Exempt Reporting Advisers and Registered Investment Advisers monthly files (sec.gov) | Official free CSV downloads with firm name, US state and website | Best free source. Usable now |
| SEC Form D quarterly data sets (sec.gov) | Free official zips, but no websites in the files | Useful for names only |

## 2. Files already produced
- data/domain-lists/sec-pe-advisers.csv: 836 US domains. Source: SEC exempt and registered adviser files (Nov 2026). Filter used: US main office, a website, private equity funds flagged, no VC, hedge or real-estate funds, private-fund assets at or under $1B, and wealth, trust, real estate, crypto and venture names dropped. These are mostly small private equity and sponsor-style firms. The Dream list rules say PE is parked unless Murali approves, so the site check will sort IS-like firms from true PE.
- data/domain-lists/ct-directory.csv: see section 4 (filled in after the crawl).

## 3. How to reach 3,000+ domains

| Route | Expected raw domains | Cost | Notes |
|---|---|---|---|
| Apollo company search export | 3,000 to 6,000+ | Plan credits | The main route. Use the filters in data/lead-sourcing-filters.md section 5. Split the search by state and keyword set so each export stays under the plan's cap, then merge |
| SEC adviser files | 836 (done) | Free | Official data, refresh monthly |
| CT Acquisitions directory | a few hundred usable (see section 4) | Free | Some profiles list a website; the rest need a name-to-domain match in Apollo |
| Search API discovery (Brave Search API, Exa or similar) | 500 to 1,500 | Low (per-query pricing) | Run 300 to 600 queries such as "independent sponsor" + state + sector, then collect unique result domains. Needs an API key from you |
| Paid list vendors (ListKit, Instantly SuperSearch, Clay, ZoomInfo) | 3,000+ in one export | Paid | Fastest if the Apollo cap is a problem; filter by industry, headcount, keywords |
| Murali's buyer lists | 100 to 500 | Free | Teaser and CIM distribution lists from the 24+ CIMs, NDA signers, Axial teaser activity. Best quality of all |
| Press release alerts | 100 to 300 per quarter | Free | Alerts for "independent sponsor acquires" and "family office acquires" |
| SBIA, McGuireWoods and conference lists | by hand | Free | Copy names into a sheet; Claude can match domains |

Realistic stack to reach 3,000: Apollo (3,000+), SEC (836), search API (500+), Murali's lists, CT directory. Expect about 40% to 60% of raw domains to drop at the site check.

## 4. CT Acquisitions directory crawl
Crawled 948 public profiles at one request per second (robots.txt allowed). Output: data/domain-lists/ct-directory.csv with firm, type (as the directory describes it), city, state, website domain where listed, and the profile URL. Search funds and venture firms were dropped. Rows without a domain need a name-to-domain match (Apollo can do this).
