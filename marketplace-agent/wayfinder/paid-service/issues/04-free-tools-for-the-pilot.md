# Which free tools can run the pilot's intake, payment and landing page?

Type: research
Status: resolved
Blocked by:

## Question

With no new spending allowed, which free options exist for:

1. A landing page on Clay's existing domain (free static hosting such as GitHub Pages, and how a custom domain connects).
2. Collecting a Seller's photos and notes (free form or upload tools, email).
3. Taking small payments of $5–10: Stripe Payment Links, PayPal, Venmo for business, Cash App, and so on. Give each one's fees, setup cost and any rules against this kind of service.

List every cost, including per-transaction fees, so Clay can decide on them. Cite the vendors' own pricing pages.

## Answer

Findings: [research/04-free-tools-for-the-pilot.md](../research/04-free-tools-for-the-pilot.md) (also on branch `research/free-pilot-tools`). Vendor pages were blocked, so claims rest on search excerpts of those pages; unverified points are marked in the file.

- **Landing page, $0:** Netlify Free, or Cloudflare Pages on a subdomain (one DNS record). GitHub Pages is free too, but its terms bar sites "primarily directed at… facilitating commercial transactions".
- **Intake, $0:** plain email to Gmail (25 MB per message, no sign-in for Sellers). Tally Free allows 10 MB per file. Google Forms makes Sellers sign in to Google to upload.
- **Payments:** no setup or monthly fees anywhere, only per-payment fees. Venmo business profile 1.9% + $0.10 (about $0.29 on $10), Cash App Business 2.6% + $0.15, Stripe Payment Link 2.9% + 30¢ (about $0.59 on $10), Square 3.3% + 30¢, PayPal 2.99–3.49% + $0.49. Venmo, Cash App and PayPal all forbid taking business payments as personal "friends and family" payments.
- **Tax forms:** a federal 1099-K starts above $20,000 and 200 transactions; some states set it lower.
- **Cheapest combo** (Clay still has to approve the fees): Netlify or Cloudflare page, email intake, Venmo business profile, Stripe link as the card fallback. About $1.45–2.95 in fees for 5 Sellers paying $10.
