# Map: Turn the listing agent into a paid service

Label: wayfinder:map

## Destination

A ready-to-run **30-day pilot spec** for model B (a self-serve listing assistant: Sellers send photos and get back a priced, recall-checked, paste-ready Listing plus reply drafts, then post it themselves), ending in a go/no-go call.

## Notes

- **Vocabulary:** use `marketplace-agent/GLOSSARY.md` (Seller, Buyer, Item, Listing). ADRs go in `marketplace-agent/docs/adr/`.
- **Skills:** grilling tickets call `grilling` and `domain-modeling`; prototype tickets call `prototype`; research tickets call `research`.
- **No new spending.** The pilot runs on what Clay already pays for: his Claude plan and his existing domain. Any other cost (even per-transaction fees) is described to Clay and decided with him, never assumed.
- **Manual pilot.** For the 30 days, Clay runs the existing agent behind the scenes for each Seller. No app is built until the pilot shows demand.
- **Pass line:** at least 5 Sellers who pay something (even $5–10) by day 30, plus a believable path to about $500/month profit within 3 months.
- **Meta's rules are a hard constraint.** Nothing in the service may break Meta's Terms or Commerce Policies.
- **Capacity:** Clay alone, about 8 hours a week.
- **Pilot Sellers can be anywhere in the US**, recruited first through people Clay knows and his own channels. No paid ads.
- **Plan, don't do:** tickets produce decisions, except the one task ticket.

## Decisions so far

<!-- one line per closed ticket: [title](link): gist -->

- [What do similar listing tools offer, and what do they charge?](issues/03-competitors-and-prices.md): platforms now draft listings and suggest prices free; paid tools are $9–50/mo reseller subscriptions; nobody does recall checks, reply drafts with scam screening, or location-data removal, so sell the safety and judgment layer.
- [Which free tools can run the pilot's intake, payment and landing page?](issues/04-free-tools-for-the-pilot.md): $0 landing page on Netlify or Cloudflare (not GitHub Pages: commercial-use limit), email intake, and payment links with only per-payment fees (Venmo business about 29¢ on $10, Stripe about 59¢); those fees still need Clay's OK.

## Not yet specified

- **Go/no-go details:** exactly what gets measured during the 30 days, how, and what happens on a "go" (the next 60 days).
- **What the product becomes after the pilot:** a packaged Claude skill or project the Seller runs, a web app on Clay's domain, or something else. Depends on the pilot offer and on what Claude's terms allow.
- **Legal and business basics:** whether a sole proprietorship is enough, whether sales tax applies to the service, and Clay's liability if a price or recall check is wrong.
- **Better price comparisons:** eBay's Product Research shows sold prices free to sellers (per the competitor research), but whether the agent can use it for a Seller's Item is still open.
- **The know-how side channel (model C):** whether to package the know-how as content alongside the pilot, and when.
- **AI disclosure for Sellers:** what a Seller's Listing and replies should say about AI help, now that the posts are theirs, not Clay's.

## Out of scope

- **Model A, done-for-you local selling:** Clay chose the self-serve assistant (B). Picking up, storing or handing over Items is not part of this effort.
- **Model D, reselling for himself:** this has no Sellers paying for a service, so it isn't a paid service.
