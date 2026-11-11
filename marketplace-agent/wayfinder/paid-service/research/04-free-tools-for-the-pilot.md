# Research: free tools for the pilot's landing page, intake and payment

Ticket: [`issues/04-free-tools-for-the-pilot.md`](../issues/04-free-tools-for-the-pilot.md)
Researched: 2026-11-11

Every cost below is a **choice for Clay**, not a decision. "Free" means $0 to set up and $0 per month; per-transaction fees are listed separately.

## How this was researched (read first)

- Sources are the vendors' own pricing, help, docs and legal pages. Community forums are cited only where the vendor page was silent, and are marked **(forum)**.
- **Direct page fetches were blocked** in this session's network (`docs.github.com` and `stripe.com` failed to resolve; I stopped trying other hosts). Every claim below comes from search-engine excerpts of the cited vendor pages, not from reading each full page. Fees change; open each linked page before you sign up.
- Items marked **Unverified** are ones where the vendor's own text wasn't found or sources disagreed.

---

## 1. Landing page on Clay's existing domain

All three hosts below cost $0 on their free tier and include HTTPS for a custom domain. Pointing the domain is a DNS change at the registrar, which costs nothing extra. Domain renewal is an existing cost, not a new one.

| Host | Cost | Limits on the free tier | How the custom domain connects | Rule that could bite |
|---|---|---|---|---|
| **GitHub Pages** | $0 on a **public** repo with GitHub Free. Private-repo Pages needs Pro or higher. [1] | Soft limits: 100 GB bandwidth/month, 10 builds/hour [2] | Apex: four A records to `185.199.108.153`, `.109.153`, `.110.153`, `.111.153`. `www`: CNAME to `USERNAME.github.io`. GitHub redirects between them when both are set. "Enforce HTTPS" can take up to 24 h to appear. Don't use wildcard DNS records (takeover risk). [3] | **Yes, possibly.** GitHub says Pages is "not intended for or allowed to be used as a free web-hosting service to run your online business, e-commerce site, or any other website that is primarily directed at either facilitating commercial transactions or providing commercial software as a service". [2] A page whose main job is to sell a paid service and link to a payment page could fall under that. Clay's call. |
| **Cloudflare Pages** | $0 | Unlimited sites, requests and bandwidth on all plans [4]; 500 builds/month, 1 concurrent build, 100 custom domains per project [5] | **Subdomain** (e.g. `list.example.com`): CNAME at the current DNS provider to `<site>.pages.dev`; no move needed. **Apex** (`example.com`): the domain must become a Cloudflare zone, i.e. move nameservers to Cloudflare. Add the domain in the Pages dashboard *before* the CNAME, or you get a 522 error. [6] | No commercial-use rule found on Cloudflare's pages. **Unverified** (only forum opinions, which conflict). [5] |
| **Netlify** | $0. "You'll never be charged for the Free plan." [7] | 300 credits/month, hard cap. Bandwidth uses 20 credits/GB (so about 15 GB if nothing else uses credits; my arithmetic). If one project goes over, **all** projects pause until next cycle. [7] | Custom domains with SSL included on Free [7]. Apex: A record to `75.2.60.5`, or ALIAS/ANAME to `apex-loadbalancer.netlify.com`. Subdomain: CNAME to the site's `netlify.app` name. [8] | Netlify staff say Free may be used for commercial projects (forum, 2024) [9]; Netlify's 2024 blog says the same [10]. The agreement says Free can change or end at any time, with no service-level commitment. [11] |

Note: GitHub also says Pages sites must not be used for sensitive transactions such as sending passwords or card numbers [2]. That's fine as long as payment happens on the processor's own page.

## 2. Collecting a Seller's photos and note

| Tool | Cost | Photo limits | Friction / notes |
|---|---|---|---|
| **Email (Clay's existing Gmail)** | $0 | 25 MB of attachments per message on personal accounts; larger sends become a Drive link automatically. [12] Everything counts against the 15 GB free storage shared by Gmail, Drive and Photos. [13] | Lowest friction: Sellers already know how. Matches today's flow ("photos in chat with a short note"). Going over quota can stop Gmail sending and receiving. [13] |
| **Google Forms (file upload question)** | $0 | Owner sets max file size, max files per question, and a total cap for the form. Files go to a folder in the **owner's** Drive (uses Clay's 15 GB). [14] | **Respondents must sign in to a Google Account** to answer a file-upload question. [14] Sellers without one can't upload. |
| **Tally (free)** | $0 | **10 MB per file** on Free; no limit on number of files or total storage, under a fair-use policy. Unlimited forms and submissions. [15] Pro ($29/month) lifts the file limit. [15] | No sign-in needed by Seller (not stated by Tally; **Unverified**). Whether every phone photo fits under 10 MB is **Unverified**. |
| **Jotform Starter (free)** | $0 | 5 forms, **100 submissions/month**, **100 MB total upload space**, 500 stored submissions (older ones auto-deleted). [16] | 100 MB fills fast if each Seller sends 5–10 phone photos. Going over the submission limit disables all forms until reset. [16] Form-view limit is reported as 10,000 on the pricing page but 1,000 in support answers (**conflict**). [16] |

Privacy note (not from a vendor page): Seller photos may carry GPS data in EXIF. The agent already strips EXIF before posting; whichever tool is used, the raw photos sit in Clay's Gmail/Drive or the form vendor's storage.

## 3. Taking $5–10 payments

Fees worked out for a $5 and a $10 payment (rounded to the cent). "Seller" here is the pilot Seller paying Clay.

| Option | Setup / monthly | Fee per payment | On $5 | On $10 | Who can pay | Rules that matter |
|---|---|---|---|---|---|---|
| **Stripe Payment Link** | $0 setup, $0 monthly, no closure fee [17] | 2.9% + 30¢ (US cards) [17]; Payment Links add no fee of their own [18] | $0.45 (9%) | $0.59 (6%) | Anyone with a card; Apple Pay works on Payment Links with no setup [19]; Cash App Pay available for US customers [20] | Needs SSN (EIN optional for a sole proprietor) [21]. Prohibited list covers illegal goods, adult, gambling, debt relief, etc. — nothing found that matches a listing-writing service [22]. Extras: +1.5% international cards, +0.5% manually keyed cards [17]; optional custom domain ($10) and post-payment invoice (0.4%, max $2) fees [18]. **Dispute: $15 per dispute**, plus $15 more if you contest it (refunded if you win) [23]. |
| **PayPal business – payment link** | $0 setup (not stated explicitly; **Unverified**) | Card/Apple Pay: 2.99% + $0.49. PayPal/Venmo/Pay Later wallet: 3.49% + $0.49 [24] | Card $0.64 (13%); wallet $0.66 | Card $0.79; wallet $0.84 | Card or PayPal/Venmo wallet | US fixed fee is $0.49 [25]. Dispute fee $15, **waived when the payment is under twice that ($30)**, so it shouldn't hit $5–10 payments [26]. Card chargeback fee is $20 [26] (whether the under-$30 waiver also covers it is **Unverified**). |
| **PayPal personal – "goods and services"** | $0 | 2.99% [24] (no fixed fee shown; **Unverified**) | $0.15 | $0.30 | PayPal users | Never ask a buyer to send a commercial payment as "Friends and Family": PayPal can remove your ability to receive personal payments. [27] |
| **Venmo business profile** | **No monthly or setup fees** [28] | 1.9% + $0.10 on payments of $1 or more, paid by the receiver [29] | $0.20 | $0.29 | People with Venmo | Profile sits inside Clay's personal Venmo account [28]. One Venmo page quotes 2.99% for business-profile sales — **conflict**; the fee page and help article say 1.9% + $0.10. [29][30] |
| **Venmo personal, tagged "goods and services"** | $0 | 2.99% seller fee [31] | $0.15 | $0.30 | People with Venmo | Venmo's agreement: commercial payments to a personal account must be **tagged by the buyer** as goods and services; otherwise a personal account "may NOT" be used for business payments. [32] Relies on every Seller tagging correctly. |
| **Cash App for Business** | $0 (not stated explicitly; **Unverified**) | 2.6% + $0.15 per payment from a customer's Cash App [33] | $0.28 | $0.41 | People with Cash App | Personal accounts are for non-commercial payments; selling needs a Business account. [34] The fee page is over a year old (**check current rate**). [33] |
| **Square payment link (Free plan)** | $0/month [35] | 3.3% + 30¢ online [35] | $0.47 | $0.63 | Anyone with a card | Needs SSN or ITIN; EIN can be added later. [36] |

### Tax forms (only what the vendor pages say)

- **Federal 1099-K:** Stripe, PayPal/Venmo, Cash App and Square all say a 1099-K is issued only above **$20,000 and 200 transactions** in a calendar year, both required. [37][38][39][36]
- **Lower state thresholds:** PayPal lists $600 for Maryland, Massachusetts, Vermont and Virginia, and over $1,000 with four or more transactions for Illinois. [38] Square gives Illinois as over $1,000 and more than 3 transactions. [36] Clay's state isn't confirmed in the brief, so check which applies.
- **Backup withholding:** PayPal/Venmo issue a 1099-K regardless of volume if backup withholding applied. [38]
- Only goods-and-services payments count; Friends-and-Family payments don't. [38]
- **EIN:** Not required by Stripe or Square for a sole proprietor; both accept an SSN. [21][36]
- These pages only say when a form is issued. Whether and how the income is taxed is outside this ticket (see the map's "Legal and business basics").

---

## Bottom line for the pilot

Every option below has **$0 setup and $0 monthly**. The only possible new costs are per-payment fees and dispute fees. Clay decides.

1. **Landing page:** Netlify Free or Cloudflare Pages on a **subdomain** (one CNAME, no nameserver move) avoid the open question in GitHub Pages' commercial-use rule. GitHub Pages works technically and is free, if Clay reads its rule as allowing a simple landing page. Skipping the page entirely (a link-in-bio plus email) is also an option for a 5-Seller pilot.
2. **Intake:** Email to Clay's Gmail is the cheapest and simplest: no sign-in for Sellers, 25 MB per message, and it matches the current flow. Tally Free is the fallback if a structured form helps (10 MB per photo). Google Forms forces a Google sign-in; Jotform's 100 MB total is tight.
3. **Payment:** Lowest fee is a **Venmo business profile** (about $0.20 on $5, $0.29 on $10), but only Sellers with Venmo can pay. A **Stripe Payment Link** covers everyone with a card (about $0.45 on $5, $0.59 on $10) but carries a **$15 fee per dispute**, which would wipe out several $5 sales. PayPal payment links cost the most per payment on small amounts ($0.64–0.84) but waive the dispute fee under $30.
4. **Cheapest workable combo:** free landing page (Netlify/Cloudflare) → email intake → Venmo business profile, with a Stripe Payment Link as a card fallback. At 5 Sellers × $10, total fees would be about $1.45 via Venmo or about $2.95 via Stripe (my arithmetic).

---

## Sources

1. GitHub Docs, "Creating a GitHub Pages site" / GitHub plans: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site ; https://docs.github.com/get-started/learning-about-github/githubs-products
2. GitHub Docs, "GitHub Pages limits": https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits
3. GitHub Docs, "Managing a custom domain for your GitHub Pages site": https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
4. Cloudflare, Pages product page: https://www.cloudflare.com/en-gb/developer-platform/products/pages/
5. Cloudflare Docs, Pages limits: https://developers.cloudflare.com/pages/platform/limits/ ; (forum) https://community.cloudflare.com/t/cloudflare-pages-limits-free-plan/431961
6. Cloudflare Docs, Pages custom domains: https://developers.cloudflare.com/pages/configuration/custom-domains/
7. Netlify Docs, credit-based pricing plans and how credits work: https://docs.netlify.com/manage/accounts-and-billing/billing/billing-for-credit-based-plans/credit-based-pricing-plans/ ; https://docs.netlify.com/manage/accounts-and-billing/billing/billing-for-credit-based-plans/how-credits-work/
8. Netlify Docs, configure external DNS: https://docs.netlify.com/manage/domains/configure-domains/configure-external-dns/
9. (forum) Netlify Support, "Can we use Netlify free plan for commercial purposes?": https://answers.netlify.com/t/can-we-use-netlify-free-plan-for-commercial-purposes/41545
10. Netlify blog, "Introducing Netlify's Free plan": https://www.netlify.com/blog/introducing-netlify-free-plan/
11. Netlify Self-Serve Subscription Agreement: https://netlify.com/legal/self-serve-subscription-agreement
12. Gmail Help, "Send attachments with your Gmail message": https://support.google.com/mail/answer/6584
13. Gmail Help, "How your Google storage works": https://support.google.com/mail/answer/9312312
14. Google Docs Editors Help, question types (file upload): https://support.google.com/docs/answer/7322334 ; Workspace tips: https://support.google.com/a/users/answer/13138098
15. Tally Help, "Collect free file uploads": https://tally.so/help/file-uploads ; Tally features: https://tally.so/features
16. Jotform, Starter plan limits: https://www.jotform.com/answers/11835461-starter-free-plan-limits ; https://www.jotform.com/answers/15246361-whats-included-in-the-starter-plan
17. Stripe pricing: https://stripe.com/pricing ; Stripe Payments: https://stripe.com/payments
18. Stripe Payment Links: https://stripe.com/payments/payment-links ; https://stripe.com/resources/more/payment-links
19. Stripe Docs, Apple Pay: https://docs.stripe.com/apple-pay
20. Stripe Docs, wallets: https://docs.stripe.com/payments/wallets
21. Stripe Support, sole proprietor without EIN: https://support.stripe.com/questions/signing-up-for-stripe-as-a-sole-proprietor-without-employer-id-number
22. Stripe, Prohibited and Restricted Businesses: https://stripe.com/legal/restricted-businesses
23. Stripe pricing (disputes): https://stripe.com/pricing ; Stripe Docs, respond to disputes: https://docs.stripe.com/disputes/responding
24. PayPal US business fees: https://www.paypal.com/us/business/paypal-business-fees
25. PayPal US business pricing: https://www.paypal.com/us/business/fees
26. PayPal US business fees (dispute and chargeback fees): https://www.paypal.com/us/business/paypal-business-fees ; PayPal User Agreement: https://www.paypal.com/us/legalhub/paypal/useragreement-full
27. PayPal User Agreement: https://www.paypal.com/us/legalhub/paypal/useragreement-full
28. Venmo for Business: https://venmo.com/business/profiles ; https://venmo.com/business/start
29. Venmo Help, "Business Profile Transaction Fees": https://help.venmo.com/cs/articles/business-profile-transaction-fees-vhel221
30. Venmo Purchase Protection (seller): https://venmo.com/purchaseprotection/seller/
31. Venmo, "About Venmo Fees": https://venmo.com/resources/our-fees
32. Venmo User Agreement: https://venmo.com/legal/us-user-agreement ; Venmo Help, buying and selling FAQ: https://help.venmo.com/cs/articles/buying-and-selling-on-venmo-faq-vhel138
33. Cash App Help, 1099-K FAQ (fee figures): https://cash.app/help/us/en-us/6499-tax-reporting-1099kfaq ; Cash App for Business fees: https://cash.app/help/US/EN-US/6521-cash-for-business-fees
34. Cash App Help, create a Business account: https://cash.app/help/us/en-us/6522-switch-to-cash ; Cash for Business Payment Terms: https://cash.app/legal/us/en-us/cash-payment-terms
35. Square pricing: https://squareup.com/us/en/pricing ; Square Payment Links: https://squareup.com/us/en/payment-links
36. Square Help, "Manage your Form 1099-K": https://squareup.com/help/us/en/article/5048-1099-k-overview ; sole proprietor onboarding: https://squareup.com/help/us/en/article/8329-onboard-your-sole-proprietorship-to-square
37. Stripe Support, 1099-K tax forms: https://support.stripe.com/questions/1099-k-tax-forms ; https://support.stripe.com/questions/whats-new-for-the-2026-tax-season
38. PayPal Help, "Current Form 1099-K Reporting Thresholds": https://www.paypal.com/us/cshelp/article/current-form-1099-k-reporting-thresholds-2025-update-help1131 ; Venmo Tax FAQ: https://help.venmo.com/cs/articles/venmo-tax-faq-vhel137
39. Cash App Help, 1099-K FAQ: https://cash.app/help/us/en-us/6499-tax-reporting-1099kfaq
