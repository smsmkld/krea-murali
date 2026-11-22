---
name: personalizations
description: Write genuinely personalized opening lines and one-to-one outreach for high-touch cold email, especially Dream 100 campaigns. Use this whenever the user asks to personalize emails, write first lines, research a prospect or company before reaching out, prepare Dream 100 outreach, warm up a named account, or make a message feel one-to-one. Also use it when they paste a list of companies or prospects and ask what to say to them, when they mention a dream client list, or when a high-value account needs a custom touch rather than a template. Trigger even if they do not use the word "personalization".
---

# Personalizations

Write the opening that proves a human looked at this specific company, then get out of the way.

This skill assumes it is running inside a Claude project dedicated to one client, holding their offer, proof points, lead magnets, and sales language. The personalization is about the *prospect*. The bridge is about the *client*. You need both, and they come from different places.

## The rule this skill exists to enforce

**Relevance beats personalization tricks.**

A line that proves you understood their business beats a line that proves you found their LinkedIn. "Congrats on the Series B" is a trick. "You raised in March and posted three SDR roles since, so I am guessing outbound is being built in-house right now" is relevance. One is a party trick, the other is a reason to reply.

The second rule is harder and matters more:

**Never invent a fact about a prospect.** A fabricated detail is worse than no personalization at all, because it destroys the credibility of the whole message and, in Dream 100, burns an account the client actually cares about. If you cannot find something real and specific, say so and flag it for manual research. A flagged prospect is a small cost. A hallucinated one is a lost dream account.

## What counts as a real personalization

Ranked by how well they work.

1. **A recent, dated action.** A launch, a funding round, a hire, an acquisition, an expansion, a new location, a system change.
2. **Something they said publicly.** A podcast line, a conference talk, a post, a quote in an article. Their own words are the strongest material available.
3. **A visible operational detail.** Their pricing page structure, a job posting's requirements, their tech stack, how their onboarding flow works, what their careers page implies about the team.
4. **A specific piece of their positioning.** How they describe themselves versus how the market describes the category.
5. **A structural fact.** Size, geography, business model, years in business. Weakest, but real, and better than a trick.

What does not count, ever: "love what you are building," "impressive growth," "big fan of the work," anything that could be pasted onto any company in the list.

## Structure of a Dream 100 email

Three lines. Resist the urge to add a fourth.

**Line 1, the proof of work.** The specific, verifiable observation. One sentence.

**Line 2, the bridge.** Connect that observation to the problem the client solves. One sentence. This is where most people fail, by jumping from a compliment to a pitch with nothing in between.

**Line 3, the value CTA.** Offer the asset. Not a meeting.

> "We put together [the asset] on exactly this. Want me to send it over?"

**No calendar link. No pitch deck. No meeting ask.** On a Dream 100 the ask is permission to give them something. The meeting comes later and comes easier. If the project has no lead magnet or case study on file, say so, because it is the missing ingredient and the campaign is weaker without it.

## Output format

For a batch, use a table so it can be pasted into a sheet and reviewed fast.

| # | Prospect | Company | Personalized line 1 | Bridge line 2 | Source | Confidence |
|---|---|---|---|---|---|---|

- **Source** names where the fact came from, specifically enough to verify. "Careers page, 3 SDR roles posted" not "their website."
- **Confidence** is High, Medium, or **FLAG**. Use FLAG when the fact could not be confirmed, and never write the line anyway.

For a single high-value account, write the full email and add a short note on why that angle was chosen.

## Workflow

1. **Read the client context.** The offer, the price point, the proof points, the lead magnets, and the language their own buyers use. This determines what the bridge can say.
2. **Research the prospect.** Website, careers page, LinkedIn, recent news, podcasts, their own content. Look for a dated action first.
3. **Find the connection.** The observation has to genuinely point at the pain the client solves. If it does not, keep looking rather than forcing a bridge.
4. **Write tight.** The personalization line is one sentence. Two is already a paragraph the prospect has to wade through.
5. **Mark your sources.** Every line, every time.
6. **Flag what you could not find.** Do not pad the batch to look complete.

## Batch triage

Realistic batches contain three tiers. Sort them and say so.

- **Tier 1, strong signal.** A dated trigger or a public quote. Write the full custom email.
- **Tier 2, workable.** An operational detail or positioning observation. Write a custom line 1, use a consistent bridge and CTA.
- **Tier 3, nothing found.** Flag for manual research or drop from the Dream 100 and put in a standard campaign. Do not fake a line to fill the row.

Tell the user the split. "Of 100, 22 are Tier 1, 51 are Tier 2, 27 flagged" is more useful than 100 lines of uneven quality presented as equal.

## Voice

Match how the client actually writes, pulled from their sales calls and their site, not a generic B2B register. Specifically:

- Lowercase, casual openers work better than formal ones in most B2B markets
- No corporate throat-clearing, "I hope this email finds you well" is a delete signal
- Short sentences. The whole email should be readable in a phone notification preview
- Write like a person who noticed something, not like a vendor working a list

## Common failures to avoid

- **The compliment sandwich.** Flattery, pitch, flattery. Transparent and gets ignored.
- **Personalizing the wrong thing.** Referencing their office dog when the email is about their sales pipeline. Cute is not relevant.
- **Burying the bridge.** If the prospect has to guess why you mentioned their funding round, the personalization did nothing.
- **A meeting ask on line 3 of a Dream 100.** That converts the whole effort into a normal cold email and wastes the research.
- **Personalizing at scale.** This is a low-volume, high-effort play. If the list is 5,000 people, this is the wrong skill, use segment-level relevance instead and say so.

## Reference

For the research checklist, source-by-source, plus worked examples of strong and weak lines, see `references/research-and-examples.md`.
