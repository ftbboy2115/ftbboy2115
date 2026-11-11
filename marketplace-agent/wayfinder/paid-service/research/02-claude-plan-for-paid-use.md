# Research: Can Clay's Claude plan power a paid service?

Ticket: [`issues/02-claude-plan-for-paid-use.md`](../issues/02-claude-plan-for-paid-use.md)
Researched: 2026-11-11, against Anthropic's own pages only (anthropic.com, claude.com, support.claude.com, platform.claude.com, code.claude.com).
This is a reading of Anthropic's published text, not legal advice.

## Short answer

1. **A consumer plan (Pro/Max/Ultra) for paid work.** The terms neither clearly allow nor clearly forbid what the pilot does: Clay personally chats with Claude, then sells the Listing text he gets back. Anthropic assigns Outputs to the user and has no blanket "non-commercial" clause. But consumer plans are described as being "for individual consumers", and some things are **clearly forbidden**: letting Sellers use Clay's account, routing Sellers' requests through his subscription (an intake bot or app), and scripting claude.ai.
2. **Cheapest compliant route.** The **Claude API**, which runs under the Commercial Terms and explicitly lets a customer "power products and services" for its own customers. If Clay is on **Max, Ultra or Team**, the plan already includes **monthly API credits ($100 on Max, $200 on Ultra)**, so the API route costs **$0 in new spending**. If he is on **Pro**, there are no credits, and the API would be new spending. Estimated cost per Item: **about $1.00 on Opus 5.5 or $0.54 on Sonnet 5.5 with prompt caching** (about $5.18 and $2.63 without caching).
3. **Usage limits for 5–20 Items a week.** Anthropic publishes **no numeric** limits for Pro/Max, only "5x Pro" and so on, so the fit can't be verified from documentation. It has to be measured. On the API route, Start-tier rate limits and the $100 Max credit comfortably cover an estimated $22–87 a month on Opus 5.5 with caching.

---

## Q1. Can a consumer Claude plan be used to produce paid work for other people?

### What the Consumer Terms say

Source: Consumer Terms of Service, https://www.anthropic.com/legal/consumer-terms (page shows "Effective Oct 8, 2025")

- **Scope is individuals.** The Terms "govern your use of Claude.ai, Claude Pro, and other products and services that we may offer for individuals". The same preamble says "Our Commercial Terms of Service govern your use of any Anthropic API key, the Anthropic Console…", followed by "For clarity, this does not include Claude.ai or Claude Pro use for individuals or entities."
- **No general "personal use only" clause.** The only non-commercial limit found is about evaluation: "Use of our Services for evaluation purposes are for your personal, non-commercial use only." (Section 2)
- **Outputs belong to the user.** "Subject to your compliance with our Terms, we assign to you all of our right, title, and interest—if any—in Outputs." (Section 4) The Terms contain no clause restricting commercial use of Outputs. They also warn: "You should not rely on any Outputs or Actions without independently confirming their accuracy." (Section 4) That matters for prices and recall checks Clay sells.
- **No reselling the Services.** Section 3 prohibits using the Services "To develop any products or services that compete with our Services… or resell the Services", and prohibits helping "another person to access or use, our Services" in violation of the Terms.
- **No sharing the account.** "You may not share your Account login information, Anthropic API key, or Account credentials with anyone else. You also may not make your Account available to anyone else." (Section 2)
- **No automation.** "Except when you are accessing our Services via an Anthropic API Key or where we otherwise explicitly permit it", users may not "access the Services through automated or non-human means, whether through a bot, script, or otherwise." (Section 3, item 7)

### What the Usage Policy says

Source: Usage Policy, https://www.anthropic.com/legal/aup (page shows "Effective Nov 12, 2026"; see the flags below)

- It applies to "anyone who submits inputs to Anthropic's products or services", including "individuals using our apps".
- Under "Do Not Abuse Our Platform": "Resell, proxy, or otherwise provide access to Claude through unauthorized means, including services that route requests through consumer subscriptions, or misrepresent the product or client being used".
- Pricing secondhand goods is **not** a listed high-risk use. The high-risk areas are Legal, Medical, Finance, Credit, Insurance, Housing, Employment, Education and credentials, Healthcare access, Public benefits and services, and Legal status and adjudication. "Finance" means "a personalized recommendation to buy, sell, hold, or allocate among specific investment products…", not pricing a used item.
- Consumer-facing AI agents "must disclose to users that they are interacting with AI rather than a human". This matters only if Sellers or Buyers chat with an agent directly. The pilot's reply drafts are sent by Sellers themselves.
- It prohibits "actions or behaviors that circumvent the guardrails or terms of other platforms or services". This ties the Anthropic side back to Meta's terms (ticket 01).

### How Anthropic positions the consumer plans

- Pro: "This article is about paid Pro plans for individual consumers." Organizations are pointed to Team/Enterprise. https://support.claude.com/en/articles/8325606-what-is-the-pro-plan
- Max: the article covers individual consumers only and points organizations to Team and Enterprise. https://support.claude.com/en/articles/11049741-what-is-the-max-plan
- The Claude Code legal page says Consumer Terms apply "for Free, Pro, Max, and Ultra users" and Commercial Terms apply "for Team, Enterprise, and Claude API users". It also says "Advertised usage limits for Pro, Max, and Ultra plans assume ordinary, individual usage of Claude Code and the Agent SDK", and "Anthropic does not permit third-party developers… to route requests through Free, Pro, Max, or Ultra plan credentials on behalf of their users." https://code.claude.com/docs/en/legal-and-compliance

### Reading

| Pilot activity | Status under the text above |
|---|---|
| Clay personally chats in claude.ai or Claude in Chrome, then sends the Seller the resulting Listing and charges for it | **Not explicitly prohibited.** Outputs are assigned to him, and no non-commercial clause covers it. But the consumer plans are framed "for individuals" and "individual consumers", so this is a **gray zone**, not an explicit permission. |
| A Seller signs in to Clay's account, or Clay shares his login | **Prohibited** (Consumer Terms Section 2) |
| An intake form, bot or app that forwards Seller requests to Clay's subscription | **Prohibited** (Usage Policy: "services that route requests through consumer subscriptions"; Consumer Terms Section 3, item 7 on automated access) |
| Scripting or automating claude.ai to process Items in bulk | **Prohibited** without an API key (Consumer Terms Section 3, item 7) |
| Selling access to Claude itself ("I'll run Claude for you") | **Prohibited** ("resell the Services") |

**Unclear and unverifiable from published text:** whether Anthropic regards a one-person paid service run by hand on a consumer plan as acceptable "individual" use. No published page answers this directly. Only Anthropic can confirm it, through support or sales (https://www.anthropic.com/contact-sales).

## Q2. Cheapest compliant route, and the API cost of one Item

### The API runs under the Commercial Terms, which allow serving customers

Source: Commercial Terms, https://www.anthropic.com/legal/commercial-terms (page shows "Effective Jun 17, 2025")

- "They govern Customer's use of Anthropic API keys…" and "Services under these Terms are not for consumer use."
- A.1: "Anthropic gives Customer permission to use the Services, including to power products and services Customer makes available to its own customers and end users ('Users')."
- B: Customer "owns its Outputs". D.4: Customer may not "resell the Services except as expressly approved by Anthropic". Selling Listings is selling Outputs, not reselling the Services.
- Individuals may use it: "Yes, individuals and hobbyists are welcome to use the Claude API." API use is subject to the Commercial Terms "regardless of whether you are an individual or representing a company." https://support.claude.com/en/articles/8987200-can-i-use-the-claude-api-for-individual-use

### Max, Ultra and Team already include API credits (no new spending)

Sources: https://platform.claude.com/docs/en/about-claude/api-credits-for-subscribers, https://support.claude.com/en/articles/17154008-monthly-api-credits-for-max-ultra-and-team-plans, https://claude.com/pricing

- "Claude Max, Ultra, and Team plans include monthly credits for the Claude API… you can use them to build and run your own applications and agents. You don't need to add a payment method to Claude Platform."
- Amounts: "$100 USD (Max), $200 USD (Ultra), up to $500 USD (Team, pooled)". "Free, Pro, and Enterprise plans aren't eligible." New subscribers can claim after 7 days.
- Covered: "Claude API, Claude Managed Agents, the Claude Agent SDK, and playground". Not covered: "Claude Code, extra usage in the Claude apps".
- Credits expire "at the end of each billing cycle… with no rollover".
- **No surprise bills:** "If the organization has no credits left, API requests stop until your next monthly API credits arrive. Usage is never charged to your Claude plan."
- Program terms (https://www.anthropic.com/legal/credit-terms) say "Credits may only be used by the holder of the Anthropic account to which the Credits are associated" and "Customer may not transfer or sell Credits." No commercial-use restriction was found there. Clay running the agent himself fits this.

**Flag:** the ticket doesn't say which plan Clay has. Claude in Chrome is available on Pro and above (https://claude.com/pricing), so the README doesn't settle it. **On Pro, the API route is new spending** at the per-Item prices below. Upgrading to Max ($100/month vs. Pro's $20) is also new spending. Clay has to decide this.

**Flag:** published pages don't say whether the Console Playground supports the web search tool, so a no-code Playground workflow is unverified. The covered Agent SDK, or a small Messages API script, does support it.

### Published prices used

Source: https://platform.claude.com/docs/en/about-claude/pricing (fetched 2026-11-11)

| Model | Input | 5-min cache write | Cache read | Output |
|---|---|---|---|---|
| Claude Opus 5.5 | $4 / MTok | $5 / MTok | $0.20 / MTok | $20 / MTok |
| Claude Sonnet 5.5 | $2 / MTok | $2.50 / MTok | $0.10 / MTok | $10 / MTok |
| Claude Haiku 5.5 (prompts ≤100K) | $0.10 / MTok | $0.125 / MTok | $0.01 / MTok | $0.50 / MTok |

- Web search: "**$10 USD per 1,000 searches**, plus standard token costs for search-generated content. Web search results retrieved throughout a conversation are counted as input tokens…"
- Web fetch: "**no additional charges** beyond standard token costs".
- Batch API: "50 percent discount". Not used here because the run is interactive.
- Images: on Claude 4.7 and later models, a large photo is downscaled to a long edge of 2,576 px, which caps it at **about 4,784 tokens** (https://platform.claude.com/docs/en/build-with-claude/vision).

### Assumptions for one Item

No token figures were recorded for Item 01 (README), so these are estimates.

| Assumption | Value | Basis |
|---|---|---|
| Model | Opus 5.5 (default); Sonnet 5.5 as the cheaper option | Current models on the pricing page |
| Photos | 5 photos × ~4,784 tokens ≈ 24K tokens | Vision page cap for high-resolution models |
| Instructions, templates, fact sheet | ~10K tokens | Guess |
| Agent turns (API requests) in ~14 minutes | 20 | Guess: identify → recall check → comps → draft → Q&A |
| Average context re-sent per turn | 60K tokens (grows from ~35K to ~80K as search and fetch results pile up) | Guess |
| Unique content written to cache over the run | 80K tokens | Final context size |
| Total output (thinking, tool calls, draft) | 15K tokens | Guess |
| Web searches | 8 (product ID, recall check, several comps) | Ticket says "several" |
| Web fetches (eBay, CPSC, retail pages) | Free beyond their tokens, which are included in the context above | Pricing page |

Total input processed = 20 turns × 60K = **1,200,000 tokens**.

### Arithmetic

**Opus 5.5 without caching:**
- Input: 1,200,000 × $4/M = $4.80
- Output: 15,000 × $20/M = $0.30
- Search: 8 × $0.01 = $0.08
- **Total ≈ $5.18 per Item**

**Opus 5.5 with prompt caching** (each turn re-reads the earlier context from cache):
- Cache writes: 80,000 × $5/M = $0.40
- Cache reads: (1,200,000 − 80,000) = 1,120,000 × $0.20/M = $0.224
- Output: $0.30
- Search: $0.08
- **Total ≈ $1.00 per Item**

**Sonnet 5.5 without caching:** 1,200,000 × $2/M = $2.40, plus output 15,000 × $10/M = $0.15, plus search $0.08. **Total ≈ $2.63.**

**Sonnet 5.5 with caching:** writes 80,000 × $2.50/M = $0.20, plus reads 1,120,000 × $0.10/M = $0.112, plus output $0.15, plus search $0.08. **Total ≈ $0.54.**

Monthly totals use 52/12 ≈ 4.33 weeks per month.

| Scenario | 5 Items/week | 20 Items/week | Per month at 5/wk | Per month at 20/wk |
|---|---|---|---|---|
| Opus 5.5, cached | $5.02 | $20.08 | ~$22 | ~$87 |
| Sonnet 5.5, cached | $2.71 | $10.84 | ~$12 | ~$47 |
| Opus 5.5, uncached | $25.90 | $103.60 | ~$112 | ~$449 |
| Sonnet 5.5, uncached | $13.15 | $52.60 | ~$57 | ~$228 |

With prompt caching, every scenario fits inside the **$100/month Max credit**, which ends in an unbilled stop rather than a charge. Without caching, Opus at 20 Items a week does not fit. The biggest uncertainty is how many turns a run takes and how large the context gets. Measure them on the first real run from the `usage` fields in API responses, or on the Console's Cost page.

## Q3. Do the plan limits fit 5–20 Items a week?

### Consumer plans (claude.ai / Claude in Chrome)

- Anthropic publishes **no numeric** limit. Pro: "The number of messages you can send will vary based on message length, including the length of files you attach, the length of your current conversation, and the model or feature you use." Pro has "a five-hour limit and a weekly usage limit that applies across all models." https://support.claude.com/en/articles/8325606-what-is-the-pro-plan
- Max gives "five times the Pro plan's usage every five hours and every week". Ultra gives "10x Pro usage every week" with "No 5-hour limit" for verified accounts. https://support.claude.com/en/articles/11049741-what-is-the-max-plan, https://claude.com/pricing
- Windows: "The period starts when you send your first message, and your limit resets in full five hours later." "Weekly limits reset at a fixed time each week that is assigned to your account." Usage on all surfaces counts toward one limit. "Tools and connectors are token-intensive." "We may adjust usage limits at our discretion…" https://support.claude.com/en/articles/11647753-how-do-usage-and-length-limits-work
- Heavy-usage factors: "Multi-step tasks, like running code, creating files, or browsing websites", "Tool usage (e.g., Research, web search)", "Model choice", "File attachment size". https://support.claude.com/en/articles/9797557-usage-limit-best-practices

**Verdict: unverifiable from documentation.** 5–20 Items a week is about 1–3 runs of ~14 minutes a day, which is light for one person, and Max's 5x headroom makes a fit likely. But each run is the usage-heavy kind (photos, web search, browsing), and Item 01's share of the weekly limit wasn't recorded. **To check:** after the next Item, read Settings > Usage and multiply that Item's share of the weekly limit by 20. In model B the Seller posts the Listing, so the Claude in Chrome form-filling step, the heaviest browsing step, drops out.

### API route

- Organizations linked to an eligible plan "move up to at least the Start tier" (https://platform.claude.com/docs/en/about-claude/api-credits-for-subscribers). Start tier allows Opus 5.5 at 4,000 RPM, 2,000,000 input tokens per minute and 400,000 output tokens per minute, with a $500/month spend cap (https://platform.claude.com/docs/en/api/rate-limits). An Item at roughly 1.2M input tokens over 14 minutes is a tiny fraction of that.
- So on the API, the binding limit is **money (the credit balance), not rate limits**. Per the table above, 5–20 Items a week costs about $22–87 a month on cached Opus 5.5.

## Flags and gaps

- **Usage Policy date:** the page reads "Effective Nov 12, 2026", one day after this research. Its version-history link had no URL to check, so the policy in force today may differ slightly. Recheck after Nov 12.
- **Consumer Terms preamble:** the fetch tool returned the preamble in fragments ("For clarity, this does not include Claude.ai or Claude Pro use for individuals or entities"). Its meaning, that Commercial Terms don't cover Claude.ai or Pro, is consistent with the rest of the page, but read the original sentence.
- **Clay's current plan is unknown.** The no-new-spending API route exists only on Max, Ultra or Team.
- **Token profile is estimated, not measured.** No usage was logged for Item 01.
- **Playground and web search:** not confirmed.
- **Data handling:** not researched. Seller photos would go into Clay's account, under the consumer data settings or the Commercial Terms depending on the route.
- **Out of scope here:** Meta's rules (ticket 01).

## Bottom line for the pilot

- **Manual and run by Clay personally, on his consumer plan:** not explicitly banned, and Outputs are his to sell, but it sits in a gray zone because consumer plans are "for individual consumers". It is defensible only if Sellers never touch Claude or his account and nothing is automated. For certainty, ask Anthropic.
- **Clean, compliant route:** the Claude API under the Commercial Terms, which explicitly lets him power services for his own customers. **On Max, Ultra or Team it costs $0 in new spending** via the included monthly API credits ($100 on Max), which stop rather than bill when exhausted.
- **Cost per Item on the API:** about **$1.00 on Opus 5.5 or $0.54 on Sonnet 5.5 with prompt caching** (roughly 5x more without caching). 5–20 Items a week costs about $22–87 a month on Opus 5.5, within the Max credit.
- **Consumer usage limits** can't be checked against 5–20 Items a week from published data. Measure one Item's share in Settings > Usage.
- **Decision for Clay:** confirm his plan. On Pro, choose between the gray-zone manual pilot on Pro and new spending (API credits or a Max upgrade). Never build an intake app on the consumer plan.
