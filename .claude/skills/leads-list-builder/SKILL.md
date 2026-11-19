---
name: leads-list-builder
description: Build targeted, ListKit-ready prospect lists and segment briefs for a cold email agency client. Use this whenever the user asks to build a leads list, define or refine an ICP, pick a target market, find a new segment or angle to test, decide who to email next, size a market, or prepare a list for client sign-off. Also use it when they paste an ICP description, say things like "who should we go after for this campaign", "we need a new list", "this segment is burnt out", or ask what filters to set in ListKit. Trigger even if they do not say the words "leads list" or "ICP".
---

# Leads List Builder

Turn what is known about a client into a targeting spec someone can execute in ListKit today, plus the sign-off doc that protects the invoice later.

This skill assumes it is running inside a Claude project dedicated to one client, containing the sales call, the onboarding form, the onboarding call, campaign history, and Slack threads. Read that context before answering. If the project is thin, say what is missing instead of inventing an ICP.

## Why the leads list matters more than the copy

Two reasons, and both cost money when ignored.

**Targeting beats copy.** A great script to the wrong list does nothing. A plain script to the right list books calls. When results are bad, suspect the list before the copy.

**Qualification starts here, not at the invoice.** The client signs off on the list before anything sends. When they later object that a booked prospect was not qualified, the signed list is the answer. A list that never got approved is an argument waiting to happen.

## The standard

- **1,000 leads minimum per campaign.** Smaller than that is not a standalone campaign and will not produce a readable signal.
- **One segment per list.** If the copy has to speak to two different buyers, it is two campaigns.
- **Every list gets sent for sign-off before launch.** No exceptions.
- **Suppressions applied before extraction**, not after someone embarrasses the client.

## Workflow

1. **Read the project context.** Pull the ICP, offer, price point, sales process, and, critically, the client's own words on what makes a prospect qualified and who they refuse to work with.
2. **Check campaign history.** What segments have run? What did they produce? Do not rebuild a list that already flopped, and do not re-mail a segment that was just contacted.
3. **Pick the segment.** One clear buyer, one clear reason they need this offer now.
4. **Write the spec** in the output format below.
5. **Size it.** If the filters yield under 1,000, widen one dimension at a time (geography first, then employee count, then adjacent titles) and say which one you widened and why.
6. **Produce the sign-off block** so it can be pasted straight into the client Slack channel.

## Output format

Use this structure every time.

```markdown
## Segment: [short name]

**The buyer:** [Title(s), and what they are accountable for]
**Why now:** [The trigger or pain that makes this segment worth emailing this month]
**Why this client wins here:** [The specific proof point or differentiator that lands with this buyer]

### ListKit filters
| Filter | Setting |
|---|---|
| Job titles | |
| Seniority | |
| Industry / keywords | |
| Employee count | |
| Revenue | |
| Geography | |
| Technologies / other | |

**Estimated list size:** [number]. If under 1,000, note what you widened.

### Suppressions
- [Existing customers, active pipeline, competitors, past-burnt segments, anyone contacted in the last 90 days]

### Angle this list supports
[One or two sentences. The list and the angle are one decision, not two.]

### Signals this is working or not
- Good: [what to expect if the targeting is right]
- Bad: [the specific failure mode for this segment, and what it points to]

### Client sign-off request
[Paste-ready Slack message asking for approval, naming the segment, the size, and a date.]
```

## Choosing a segment well

Rank candidate segments on three things, in this order:

1. **Proof.** Does the client have a case study, logo, or result from a company that looks like this? A segment with proof converts. A segment without proof is a test, and should be labeled a test.
2. **Reachability.** Are the decision makers findable by title, and is the buying decision made by one or two people? Committees kill cold email.
3. **Urgency.** Is there a reason to act this quarter? A trigger beats a general benefit.

If a segment scores well on proof and reachability but has no urgency, that is fine. Say so and let the angle carry it. If it scores badly on proof, cap the first list at 1,000 and call it a validation run.

## Widening a list that comes in short

In this order, because each step costs less relevance than the one after it:

1. Geography, expand to adjacent metros, then national
2. Employee count, loosen the upper bound before the lower
3. Adjacent job titles at the same seniority
4. Seniority, add second-in-command roles
5. Adjacent industries with the same underlying pain

Never widen by dropping the qualification criteria the client wrote down. That trades a short list for an invoice fight.

## When the client's ICP is too vague

Common, and worth pushing back on rather than guessing. "Small businesses" or "B2B companies" is not a spec. Give them a concrete proposal to react to instead of an open question, because reacting is easier than authoring:

> "Based on your best clients, I am reading your ICP as [specific spec]. I would start there and test [adjacent segment] second. Push back if that is off."

## What not to do

- **Do not invent an ICP the client never described.** If the context is missing, name what you need.
- **Do not stack six filters on a first list.** Over-filtering produces 200 leads and no signal. Start broad enough to learn.
- **Do not reuse a list because it is convenient.** Re-mailing a recently contacted segment burns the domain and the client's reputation.
- **Do not skip the sign-off step**, even when the client is fast and trusting. The document is the point.

## Reference

For the full targeting and segmentation checklist, including the 20 question bank items that feed a list build, see `references/targeting-checklist.md`.
