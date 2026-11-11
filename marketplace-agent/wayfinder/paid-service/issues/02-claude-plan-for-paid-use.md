# Can Clay's Claude plan power a paid service?

Type: research
Status: resolved
Blocked by:

## Question

The pilot uses Clay's existing Claude subscription (no new spending). Against Anthropic's own terms and usage policies:

1. Can a consumer Claude plan (Pro or Max) be used to produce paid work for other people, like listings Clay sells to Sellers?
2. If not, or if it's unclear, what is the cheapest compliant route (for example the API), and roughly what would one Item's run cost at current published prices? Assume about 14 minutes of agent work with several web searches.
3. Do the usage limits on those plans fit roughly 5–20 Items a week?

Cite each answer to the Anthropic page it comes from.

## Answer

Findings: [research/02-claude-plan-for-paid-use.md](../research/02-claude-plan-for-paid-use.md) (also on branch `research/claude-plan-terms`).

1. **Consumer plan for paid work:** a grey area. Clay chatting with Claude himself and selling the resulting Listing is neither allowed nor forbidden (outputs belong to him; no non-commercial clause, but the plans are "for individual consumers"). Clearly forbidden: letting Sellers into his account, routing their requests through his subscription, scripting claude.ai, and reselling access to Claude.
2. **Compliant route:** the API, whose Commercial Terms allow powering services for your own customers. Max, Ultra and Team include monthly API credits ($100 on Max), so on those plans this costs nothing new; Pro has no credits. Rough estimate per Item: about $1.00 on Opus 5.5 or $0.54 on Sonnet 5.5 with caching (about $5.18 / $2.63 without), so 5–20 Items a week fits inside Max's $100 credit. No token counts were logged for Item 01, so these are guesses.
3. **Usage limits:** Anthropic publishes no hard numbers for Pro or Max. Measure one Item's share of the weekly limit in Settings > Usage.

Open: **which plan Clay is on decides whether the no-new-spending API route exists.** The Usage Policy changes on Nov 12, 2026; recheck it after that date.
