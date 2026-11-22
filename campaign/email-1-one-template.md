# Email 1: ONE template, one angle (founder dependence)

Last updated: Nov 22, 2026. Draft for review. Nothing here has been sent.

One email for everyone. Only the data columns change. There is no separate copy per variable.

**Subject:** `founder dependence at {firm}`

**Body**

> {Name} - saw {observation}. A pattern buyers know: the founder steps back, and pricing, key accounts and supplier terms turn out to have lived in one person’s head.
>
> Founder dependence rarely shows up in the CIM. I’ve written more than 24 CIMs and worked both sides of the table, so I know where it hides. I flag it, with other operating risks, in 5 business days, {diligence_phrase}.
>
> Worth a short call before {next_deal_phrase}?
>
> Murali

## The 4 fill-in columns
| Column | What goes in it | Where it comes from |
|---|---|---|
| `{Name}` | The first name to use | `greeting_name` in the master file |
| `{observation}` | One short fact that fits after the word "saw" | `observation` in `data/dream100-variables.csv` (one per firm, with a source link) |
| `{diligence_phrase}` | Independent sponsor: *before the LOI or full diligence*. Family office: *before the LOI or you commit family capital*. (Private equity, parked: *before the LOI or you commit fund capital*.) | firm type |
| `{next_deal_phrase}` | Sponsor: *your next deal*. Family office: *your next direct deal*. (PE, parked: *your next platform deal*.) | firm type |

## What goes in `{observation}`
The sentence always reads "saw ___", so each variable is written to fit that blank:

| Variable | Example filled in |
|---|---|
| Recent deal | saw **Drill-Tech closed in May** |
| Portfolio company | saw **Currier Plastics in your portfolio** |
| Live signal | saw **you’re looking for seafood acquisitions** |
| Buy box | saw **your $3–8M EBITDA range** |
| Founder background | saw **you spent time at Kelso** |
| Sector | saw **your focus on manufacturing** |

If a firm has no variable, the row is `NO_LINE` and no email is written.

## Why this works as one copy
- The "A pattern buyers know" sentence is the same for every lead, so the angle never changes.
- The observation only proves a person looked at the firm. It does not have to connect to the pattern.

## Trade-off
Because the pattern sentence is fixed, the link between the observation and the founder-dependence point is looser than in a hand-written line. That is the price of one copy. The first test send will show whether it matters.

## Checked
- Under 90 words for every lead (the longest is 90).
- First person, one question, call-only ask, no CIM request, no price, no promise, no joke.
- Murali's wording is in: "worked both sides of the table", "5 business days", "worth a short call".

## Result for the 105 first-contact firms
- 90 firms have an `observation` and a ready preview in the `email_1_preview` column.
- 15 firms are `NO_LINE` and need manual research.
