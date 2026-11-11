# Research: What do Meta's rules allow for a self-serve listing assistant?

Ticket: [01-meta-terms-for-self-serve](../issues/01-meta-terms-for-self-serve.md)
Researched: 2026-11-11

Scope: the ticket's three questions (Q1–Q3), plus three the coordinator added mid-research for the case where the agent **posts** the Listing for the Seller (Q4–Q6).

## Read this first: what could and couldn't be verified

**The Meta pages couldn't be opened from this session.** The cloud session's network refuses `www.facebook.com` and `transparency.meta.com` (the egress proxy returned `connect_rejected` / 403). So none of the text below was read directly from the live page.

What was possible: web searches limited to Meta's own domains (`facebook.com`, `meta.com`, `about.fb.com`). Every claim below links to the **Meta page the search engine matched**, and the wording comes from the search engine's index of that page. That makes these leads to primary text, not verified quotes. Wording marked "search excerpt" may be paraphrased or out of date.

**Before treating any answer as final, open the five URLs in [Verify before the pilot](#verify-before-the-pilot) in a normal browser and confirm the quoted lines.** That takes about 15 minutes and closes the gap.

Confidence key used below:

- **High:** several Meta pages agree, and the excerpt reads like Meta's own wording.
- **Medium:** one Meta page, or the excerpt looks paraphrased.
- **Low / unverified:** inference, or a page whose content didn't come through.

---

## Q1. Looking up Marketplace Listings as price comps for paying Sellers

### Automated lookups (scripts, bots, or an AI agent driving a browser): not allowed without Meta's written permission

1. **Meta Terms of Service** ([facebook.com/terms](https://www.facebook.com/terms/)) prohibit accessing or collecting data from Meta Products "using automated means (without our prior permission)", and the search excerpt says this applies **even when the automated access happens while logged in**. *Confidence: high* (the same wording turns up in the ToS, Meta's developer docs and Meta's robots.txt).
2. **Automated Data Collection Terms** ([facebook.com/legal/automated_data_collection_terms](https://www.facebook.com/legal/automated_data_collection_terms), version dated **7 Oct 2024** per the search index):
   - Automated collection needs Meta's **express written permission**. Search excerpt: "acceptance of these Terms alone does not constitute the required written permission … such permission must be obtained separately through Meta's formal authorization process."
   - "Automated" is defined broadly: "web scrapers, bots, robots, spiders, crawlers, **user-agents, and other automated or programmatic mechanisms**" (search excerpt).
   - Even with permission, the allowed uses are narrow (search results and link previews). Search excerpt: collectors may not "transfer, sell, license or sublicense Collected Data to third parties."
   - *Confidence: high on the permission requirement; medium on the exact wording.*
3. **Meta's robots.txt** ([meta.com/robots.txt](https://www.meta.com/robots.txt), matched by title): "Collection of data on Facebook through automated means is prohibited unless you have express written permission from Facebook." *Confidence: medium.*
4. **Meta for Developers** ([Automated Data Collection doc](https://developers.facebook.com/documentation/development/terms-and-policies/automated-data-collection.md)): Platform APIs are "the only allowable means to access data programmatically, unless you have our prior written permission", and the terms apply "even if the conduct is not intentional or if you're unsuccessful" (search excerpt). *Confidence: medium.*

**What this means for the agent:** step 3 of today's flow, where Claude reads Facebook Marketplace asking prices in a browser, is very likely "automated means" under these terms. An AI agent driving a browser fits "user-agents and other automated or programmatic mechanisms," and the ToS says being logged in doesn't change that. This is already a risk under Clay's personal use. Doing it for paying Sellers adds a second problem (below). *Confidence: medium. Meta's text doesn't name AI browser agents; this is my reading of the definition.*

### Selling what you collected: the ToS "no selling data" clause

**Meta Terms of Service** ([facebook.com/legal/terms](https://www.facebook.com/legal/terms)), search excerpt: "Except as provided in the Platform Terms, you may not sell, license, or purchase any data obtained from us or our services, regardless of whether such data was obtained while logged-in to a Facebook account." *Confidence: high on substance, medium on exact wording.*

If Clay hands Sellers a list, table or screenshots of other people's Marketplace Listings as part of a paid deliverable, that looks like selling data obtained from Meta. This applies whether the comps were collected by hand or by an agent.

### Looking by hand, in a normal signed-in browser

I found **no Meta text that forbids a person browsing Marketplace and forming a price opinion**, including on someone else's behalf. Browsing listings is ordinary use of the product. The line to stay behind is the "sell, license … any data" clause above. **Low confidence:** this is an inference from the absence of a rule, and the full ToS wasn't readable.

Safer pattern: Clay (a human) looks at Marketplace himself and writes a **price recommendation in his own words** ("similar tanks nearby are asking roughly $90–140"). The deliverable doesn't include copied listings, links, photos, seller names or screenshots.

### An alternative that sidesteps it

Meta's own tools now suggest a price from nearby Listings. Meta's newsroom says the Marketplace AI tool proposes a price "based on similar items listed in your area" ([about.fb.com, March 2026](https://about.fb.com/news/2026/03/facebook-marketplace-new-meta-ai-tools-make-selling-faster-and-easier/)), and the **Seller** app does the same ([about.fb.com, July 2026](https://about.fb.com/news/2026/07/introducing-seller-app-facebook-marketplace/)). The Seller can get the Facebook comp inside Meta's own product, and Clay's comps can come from eBay and retail sources. *Confidence: medium (newsroom pages, matched by search only).*

---

## Q2. A Seller posting AI-written Listings and replies, written for a fee

### Short answer: allowed. No Meta rule found against AI-written text, and no disclosure rule for AI-written text

1. **Meta does this itself.** Meta's newsroom says Marketplace's Meta AI tools draft the **title, description, price suggestion and category** from photos. Meta AI can also "draft and send an auto reply using information from your listing" when buyers ask whether an item is available ([March 2026 post](https://about.fb.com/news/2026/03/facebook-marketplace-new-meta-ai-tools-make-selling-faster-and-easier/); [Seller app, July 2026](https://about.fb.com/news/2026/07/introducing-seller-app-facebook-marketplace/)). A rule against AI-written Listings would contradict Meta's own product. *Confidence: medium (search-matched; the posts couldn't be opened).*
2. **Meta's AI-disclosure rules cover media, not text.** As far as the search turned up, the self-disclosure duty covers **photorealistic video and realistic-sounding audio** that was digitally created or altered, posted as organic content. Meta "may apply penalties" for failing to disclose ([Meta, "Our Approach to Labeling AI-Generated Content," Apr 2024](https://about.fb.com/news/2024/04/metas-approach-to-labeling-ai-generated-content-and-manipulated-media/); the label is now called "AI info"). Separate disclosure rules apply to **political/social-issue ads** ([Transparency Center: SIEP ads](https://transparency.meta.com/policies/ad-standards/SIEP-advertising/SIEP/)). I found **no requirement to disclose AI-written listing text or messages**. *Confidence: medium. The Help Center's own disclosure article didn't appear in results, and Meta says it is considering a standalone AI-content Community Standard after an Oversight Board case, so this could change.*
3. **No Meta text found about paying a third party to write a Listing.** That arrangement happens off Meta's products. *Low confidence (absence of a rule).*

### The rules that do bind the content

- **Must not be misleading.** ToS ([facebook.com/terms](https://www.facebook.com/terms/)): you may not use the Products "to do or share anything … that is unlawful, misleading, discriminatory or fraudulent," or help someone else do so (search excerpt). Commerce Policies item 14 ([facebook.com/policies_center/commerce](https://www.facebook.com/policies_center/commerce)): "Commerce content may not contain misleading, violent or hateful products and offers" (search excerpt). AI-written text is fine; **inaccurate** AI-written text is the risk. That covers wrong condition, invented specs, a fake "new" claim, or a stock photo passed off as the item. *Confidence: high.*
- **Photos must be real.** Generating or "enhancing" item photos with AI would run into both the misleading rule and Meta's AI-media labeling. Keep the guardrail "own photos only" for Sellers. EXIF stripping is fine; nothing found against it. *Confidence: medium.*
- **The Seller's account is the Seller's.** The ToS (plain-text version, [facebook.com/legal/terms/plain_text_terms](https://www.facebook.com/legal/terms/plain_text_terms)) says you must not share your password, give others access to your account, or transfer it, and must not request or collect other users' passwords (search excerpt). **Clay must never sign in to a Seller's account, post for them, or send their replies.** Model B already assumes this. *Confidence: high.*
- **Don't advertise the service on Marketplace.** Meta's Offers policy page ([facebook.com/business/help/358970040838616](https://www.facebook.com/business/help/358970040838616)): "Non-physical items are prohibited on Facebook Marketplace, including but not limited to services, subscriptions, digital products, or rentals" (search excerpt). Commerce Policies "Restricted Content" says services are allowed only on WhatsApp Business or through Appointments (search excerpt). Recruit Sellers through Clay's own channels, not Marketplace Listings. *Confidence: medium-high.*
- **Marketplace is meant for consumer-to-consumer sales.** The Commerce Policies (search excerpt) say Marketplace is for consumer-to-consumer selling. In the EEA, Philippines and India, people "acting in a business capacity" may lose access. The US pilot isn't in those regions, but a Seller flipping volume as a business is a weak fit. *Confidence: medium.*

### Disclosure: what the Seller's Listing and replies should say

No Meta rule found requires a disclosure line for AI-written text. Today's replies are signed "— Clay's assistant." For model B, replies go out from the **Seller's** account, so that signature is wrong. It suggests a third party is operating the account. Drop it, or make it optional and the Seller's choice (e.g. "drafted with AI help"). This is a product decision, not a Meta requirement. It belongs to the map's "AI disclosure for Sellers" fog item.

---

## Q3. Items the service should refuse

Every Marketplace Listing must follow the Commerce Policies **and** the Community Standards. Search excerpt: "Commerce content on Facebook and Messenger … must comply … with Facebook's Community Standards"; prohibited item 1 is any listing that violates the Community Standards ([Commerce Policies](https://www.facebook.com/policies_center/commerce)). The Facebook Help Center ([sell in buy and sell groups](https://www.facebook.com/help/1557451221155310)) also says "items like animals, drugs, weapons, counterfeits and other items that infringe intellectual property rights aren't allowed in buy and sell groups or on Marketplace."

### Commerce Policies prohibited categories found (numbering per search excerpt)

| # | Category | What it bars (search excerpt) | Confidence |
|---|---|---|---|
| 1 | Community Standards | Anything that violates them | High |
| — | Adult products | Buying/selling adult products; sexually suggestive positioning | Medium |
| — | Alcohol | Buying/selling/trading alcohol | Medium |
| — | Animals ([sub-page](https://www.facebook.com/policies_center/commerce/animals)) | Live animals incl. pets and livestock, animal parts, some animal products; vet medicines/devices. Cages, toys, collars allowed | Medium (the sub-page is old in the index) |
| 4 | Body parts and fluids | Human body parts or fluids | High |
| 9 | Hazardous goods and materials | "hazardous materials and substances" | High |
| — | Jobs | "may not promote job opportunities" | Medium |
| — | Medical and healthcare products | incl. medical devices and ingestible supplements (per one search summary; the exact phrase wasn't confirmed by a second search) | Low-medium |
| 14 | Misleading, violent or hateful | Misleading products and offers | High |
| 15 | No item for sale | News, humor, anything with no product | High |
| — | Prescription products, drugs, drug paraphernalia | | Medium |
| 17 | Recalled products | "may not promote the buying, selling, or trading of recalled or banned products" | High |
| 18 | Stolen goods | "items that have been stolen or otherwise acquired unlawfully or without authorization" | High |
| 19 | Digital products / subscriptions | "downloadable digital content, digital subscriptions or digital accounts" | High |
| 20 | Third-party infringement | Counterfeits; IP, copyright or trademark violations | High |
| — | Tobacco | Tobacco and related products | Medium |
| — | Weapons, ammunition, explosives | | Medium |
| — | Restricted, not banned: event tickets, gift cards | Approved sellers only, so effectively not for a normal Seller | Medium |
| — | Services, rentals, other non-physical items | Not on Marketplace (Offers policy page) | Medium-high |

I couldn't confirm the complete numbered list. There are about 30 entries, and the search excerpts surfaced roughly 20 of them. Facebook's dedicated help page listing what can't be sold on Marketplace ([facebook.com/help/153832041692242](https://www.facebook.com/help/153832041692242)) was matched only by title. Its contents didn't come through.

### What changes for the service's refuse list

The current agent already refuses recalled Items (its CPSC check). The Commerce Policies widen that in four ways:

1. **"Recalled *or banned*."** The CPSC recall check stays, and the refuse list should also cover products banned outright, not only recalled.
2. **Ownership.** "Acquired … without authorization" means the Seller must own the Item or be authorized to sell it. This matches the glossary (the Seller "owns the Item"). Add a one-line ownership confirmation at intake.
3. **New refusal categories** the agent doesn't screen for today:
   - Live animals.
   - Anything medical or healthcare (devices, supplements, and anything ingestible: food, vitamins).
   - Hazardous materials (fuel, chemicals, batteries as hazmat, propane tanks with gas in them; exact scope unverified).
   - Weapons and ammo (incl. likely bladed items; scope unverified).
   - Alcohol and tobacco/vape.
   - Adult products.
   - Counterfeit/"replica" branded goods.
   - Digital goods, accounts and subscriptions.
   - Gift cards and tickets.
   - Services and rentals.
4. **Accuracy is a policy issue, not just quality.** Item 14 ("misleading") makes the agent's identify-and-describe step a compliance step. A wrong model number or condition is a Commerce Policies violation on the Seller's account.

Enforcement lands on the Seller. Listings get rejected or removed, and repeated violations can limit or suspend the Seller's Marketplace access ([Commerce Policies](https://www.facebook.com/policies_center/commerce); [listing rejected help](https://www.facebook.com/help/2193854224216494)). So a bad draft from Clay costs a paying Seller their account standing. *Confidence: medium-high.*

---

## Q4. Can Clay post Listings and send buyer messages on a Seller's own personal account?

### Short answer: no, not through shared logins, shared sessions, or an AI driving the Seller's browser

**1. Sharing a password or account access is barred.** The Meta Terms of Service ([facebook.com/terms](https://www.facebook.com/terms/); plain-text version [facebook.com/legal/terms/plain_text_terms](https://www.facebook.com/legal/terms/plain_text_terms)) contain these lines (search excerpts):

- Users must "not share your password, give access to your Facebook account to others, or transfer your account to anyone else (without our permission)."
- Users must "create only one account (your own) and use it for personal purposes."
- Users may not request, collect or proxy other users' passwords or misappropriate access tokens.

The ban covers "give access … to others," not only passwords. A shared session (the Seller signing in on a browser profile Clay controls, exported cookies, remote desktop) is still giving access, so it is barred too. It is also a breach for the **Seller**, whose account is at risk. *Confidence: high (the same wording turns up in the main and plain-text ToS and in other Meta product terms).*

**2. Browser automation runs into the "automated means" clause.** The ToS bars accessing or collecting data from the Products "using automated means (without our prior permission)," even while logged in. The Automated Data Collection Terms define automated tools to include "user-agents, and other automated or programmatic mechanisms" (see Q1 for links). An AI filling the Listing form, reading the fields back, and reading and answering buyer messages accesses Meta Products through a programmatic mechanism. I found **no ToS line that expressly bans automated *posting*** as opposed to automated *access/collection*. Posting through a browser agent can't avoid accessing pages, though, and the agent reads them back. *Confidence: medium. Meta's text doesn't name AI browser agents; this is a reading of the definitions.*

This also bears on **Clay's own current setup**: Claude in Chrome posting on his personal profile has the same exposure, even before any Seller is involved.

**3. The Spam rules weigh against automated volume.** The Community Standards on Spam ([transparency.meta.com/…/spam](https://transparency.meta.com/policies/community-standards/spam/)) cover "Posting, sharing, engaging with content or creating accounts, Groups, Pages, Events or other assets, **either manually or automatically, at very high frequencies**" (search excerpt). A few Listings per Seller is unlikely to be "very high frequency." One operator posting many Sellers' Listings through automation trends toward it, and multi-account operation is a separate spam signal (coordinated, "when an actor uses multiple accounts"). *Confidence: medium.*

**4. Buyer messages raise the misleading problem.** If Clay or his agent writes and sends messages from the Seller's account, the Buyer believes they're talking to the Seller. The ToS bars using the Products to do anything "misleading … or fraudulent." I found no Meta text addressing an assistant answering on someone's behalf. This is an inference. *Confidence: low-medium.*

**Meta's own exception:** the auto-reply in Marketplace and the Seller app ([March 2026](https://about.fb.com/news/2026/03/facebook-marketplace-new-meta-ai-tools-make-selling-faster-and-easier/), [July 2026](https://about.fb.com/news/2026/07/introducing-seller-app-facebook-marketplace/)) is Meta's sanctioned way to automate replies and drafting. It runs inside Meta's product, not through a third party. *Confidence: medium.*

---

## Q5. Is there a sanctioned route for a third party to list on Marketplace for someone else?

### Short answer: none found that works for an individual selling used household Items

| Route | What it is | Works for model B? |
|---|---|---|
| **Marketplace Integration Terms** ([facebook.com/legal/marketplacepartnerprogram](https://www.facebook.com/legal/marketplacepartnerprogram)) | Lets an **online classifieds marketplace** surface "certain of your Listings … within FB Marketplace **within the European Economic Area**" (search excerpt). Partners must meet eligibility rules, make reasonable efforts to ensure sellers are **consumers**, and may not charge sellers extra fees to display on FB Marketplace. | **No.** EEA-only, for established classifieds platforms, and bars the kind of display fee Clay would charge. *Confidence: medium-high.* |
| **Commerce Manager / Shops catalogs** ([Shops catalog eligibility](https://www.facebook.com/business/help/1205792533104321); [About Shops](https://www.facebook.com/business/help/2343035149322466)) | A **business** uploads a product catalog. It needs a Business Manager admin, a business-owned catalog, and product links on the business's own website domain. Products "can be visible to buyers on Marketplace if the shop has checkout" (search excerpt). A Meta developer doc says **Shops checkout on Facebook and Instagram ended 4 Sept 2025**, with buyers sent to the seller's website ([developers.facebook.com, FBE deprecation](https://developers.secure.facebook.com/docs/facebook-business-extension/fbe/deprecation)). | **No.** It's for a retail business selling its own catalog. One-off used Items owned by different people don't fit. If checkout is gone, so is the Marketplace surface. *Confidence: medium. The 2025 checkout end wasn't confirmed against a dated announcement.* |
| **Retail / Home / Vehicle inventory partners** ([Home Inventory on Marketplace](https://www.facebook.com/business/help/127319601299513); [Sell Vehicles on Marketplace](https://www.facebook.com/business/help/143800203032002)) | Feeds for property-rental partners and vehicle dealers. | **No.** Category-specific programs for businesses. *Confidence: medium (matched by title).* |
| **Pages, Page roles, Meta Business Suite** | Page roles let others post **as a Page**. But Facebook Help ([sell in buy and sell groups](https://www.facebook.com/help/1557451221155310)) says "if you're posting as a Page, you won't see the option to create a listing on Marketplace" (search excerpt). Clay hit this with item 01 ("Pages can't use Marketplace"). | **No.** Delegation exists only for Pages, and Pages can't list on Marketplace. *Confidence: high.* |
| **"On behalf of" in Business Manager** ([facebook.com/business/help/350066115746201](https://www.facebook.com/business/help/350066115746201)) | Agencies placing **ads** for another business. | **No.** Ads only, not Marketplace Listings. *Confidence: high.* |
| **A public API for personal Marketplace Listings** | None found. The only Marketplace-related developer docs found are the EEA integration above, commerce catalogs, and the read-only **Meta Content Library** for approved researchers ([developers.facebook.com](https://developers.facebook.com/docs/content-library-and-api/content-library-api/guides/fb-marketplace)). | **No.** *Confidence: medium. Absence of evidence, consistent with the README's "to verify" note.* |

The only routes that let an individual's used Item onto Marketplace are the **Seller posting it themselves** (by hand, or with Meta's own AI tools and Seller app) and **Meta's own features**.

---

## Q6. Can Clay list a Seller's Item from his own personal profile?

### Short answer: not as a paid, repeat service

I found **no Help Center article that directly addresses selling an item you don't own** on Marketplace. The Help Center search surfaced nothing on "selling for someone else." The relevant text all points the same way:

1. **"Use it for personal purposes."** The ToS requires one account "(your own)" used "for personal purposes" (search excerpt, [facebook.com/terms](https://www.facebook.com/terms/)). Running a fee-based selling service for many people through Clay's personal profile is a commercial use of it. *Confidence: medium-high on the text; the application is an inference.*
2. **Marketplace is consumer-to-consumer.** The Commerce Policies ([facebook.com/policies_center/commerce](https://www.facebook.com/policies_center/commerce)) say Marketplace is "intended for consumer-to-consumer sales" (search excerpt). In the EEA, Philippines and India, people "acting in a business capacity" may have Marketplace access suspended or Listings removed. The Integration Terms likewise tell partners to screen out business or professional sellers. Selling other people's goods for a fee is acting in a business capacity, closer to a consignment shop. *Confidence: medium.*
3. **Ownership and authorization.** Commerce Policies item 18 bars items "acquired unlawfully or without authorization" (search excerpt). Read narrowly, an item sold with the owner's authorization isn't stolen. So an **occasional favor** (selling a friend's item with permission) doesn't clearly break this line. A repeat paid service still runs into points 1 and 2. *Confidence: low-medium.*
4. **Misleading.** A Listing from Clay's profile implies Clay is the owner, and meetup/pickup involves someone who isn't. The "misleading" rules (ToS; Commerce item 14) argue for stating it plainly if it ever happens. *Confidence: low (inference).*

This is model A (done-for-you), which the map already rules out of scope. The research supports that call: from what Meta's text says, model A has no compliant way to run on Facebook Marketplace at volume.

---

## Verify before the pilot

Open these in a normal browser and check the quoted lines. They are the five pages the answers lean on most.

1. https://www.facebook.com/terms: the "automated means … without our prior permission" clause, the "may not sell, license, or purchase any data" clause, the "misleading … fraudulent" clause, and the password/account-sharing clause. Note the "Last revised" date.
2. https://www.facebook.com/legal/automated_data_collection_terms: the definition of Automated Data Collection (does it name AI agents or "user-agents"?), the written-permission requirement, and the effective date.
3. https://www.facebook.com/policies_center/commerce: the full numbered prohibited list (the table above is partial), the "Restricted Content" section, and the consumer-to-consumer language.
4. https://www.facebook.com/help/153832041692242 (things that can't be listed on Marketplace): any Marketplace-only additions to the list.
5. Meta's Help Center page on AI disclosure / "AI info" (search the Help Center for "AI info"): confirm it still only requires self-disclosure for photorealistic video and realistic audio, not text or still images.

6. https://www.facebook.com/legal/marketplacepartnerprogram: confirm it's still EEA-only and for classifieds platforms.
7. https://transparency.meta.com/policies/community-standards/spam/: the "manually or automatically, at very high frequencies" line.

Also unverified:

- Whether Meta's newer Marketplace AI and Seller-app posts (about.fb.com, March and July 2026) say anything about third-party AI tools.
- Whether Shops checkout really ended on 4 Sept 2025.
- Whether any Help Center article addresses selling items for another person.

## Bottom line for the pilot

- **Comps:** stop having the agent read Facebook Marketplace for comps. Meta's terms bar automated collection, even when logged in, without written permission, and an AI-driven browser almost certainly counts. Use eBay and retail comps through allowed routes. For the Facebook view, either Clay glances by hand and writes a price range in his own words, or the Seller uses Meta's own price suggestion. Never deliver copied Listings, screenshots or data tables to Sellers.
- **AI-written Listings and replies are fine.** Meta builds the same feature itself, and no Meta rule found requires disclosing AI-written text. The binding rule is "not misleading": accuracy and real photos are compliance, not polish.
- **The agent must not post for Sellers.** Shared logins or sessions break the ToS ("not … give access to your Facebook account to others"). An AI driving the Seller's browser falls under the "automated means" clause. There is no sanctioned third-party route for individuals' used Items: the partner program is EEA classifieds only, Shops is for businesses, and Pages can't use Marketplace. Posting from Clay's own profile conflicts with "use it for personal purposes" and Marketplace's consumer-to-consumer intent. The posting scope change doesn't survive Meta's terms; keep model B as **draft-only**.
- **Hands off Sellers' accounts.** The Seller signs in, posts and sends every reply, by hand or with Meta's own AI and auto-reply tools. Drop the "— Clay's assistant" signature for Seller replies, or make it the Seller's choice.
- **Side finding:** Clay's current personal setup, Claude in Chrome posting and reading Marketplace on his own profile, carries the same "automated means" exposure. Consider posting by hand.
- **Refuse list:** CPSC recalls plus banned products, live animals, medical/health and ingestibles, hazmat, weapons, alcohol/tobacco, adult items, counterfeits, digital goods/gift cards/tickets, services/rentals, and anything the Seller doesn't own.
- **Don't market the service on Marketplace.** Services aren't allowed there.
- **Caveat:** every quote above came through a search index, not the live page. Do the 15-minute check in [Verify before the pilot](#verify-before-the-pilot) before relying on it.
