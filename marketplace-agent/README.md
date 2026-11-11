# Marketplace agent: monetization

Can Clay's Facebook Marketplace listing agent become a paid service? This folder holds the planning for that question. The agent itself lives on Clay's PC at `C:\Dev\marketplace-selling` and is **not** in this repo, so cloud sessions can't read its files. This brief is their source.

Planning runs as a wayfinder map in `wayfinder/` (see "Next step" below).

## What exists today (as of 2026-11-11)

The agent was built Oct 24–25, 2026 as a **personal** helper ("Clay and his wife struggle to post items and manage the selling. This is personal use, not a business."). It's modeled on Chris Koerner's "garage machine" idea (video `JhyVSrQPVSg`, Way #2).

**One item is live; nothing has sold yet.** Item 01, "NEW in Box Camco Rhino 15 Gal RV Tote Tank Kit + Bonus Used Hose Kit", was posted 2026-11-10 at $125 (floor $100). It had 13 clicks and no messages by that evening.

### How one item flows

1. **Intake:** Clay sends photos in chat with a short note (item, floor, condition).
2. **Identify and check:** Claude identifies the product from the box or label plus a web search, then checks CPSC for recalls.
3. **Comps:** Facebook Marketplace (local asking prices), the eBay product page and retail prices. eBay *sold* data needs a sign-in and failed.
4. **Draft:** Claude writes the title, price, floor, category and description, then asks Clay a few questions (condition, bundling, floor).
5. **Approval:** nothing posts without Clay's OK.
6. **Post:** Claude strips EXIF/GPS from the photos, fills the form in Claude in Chrome on Clay's own signed-in profile, and reads the fields back to check them.
7. **Buyer chats** (designed, not used yet): Claude drafts each reply from 13 templates plus the item's fact sheet. Replies are signed "— Clay's assistant", and Clay approves every send. Each reply is logged so routine reply types could be auto-sent later.
8. **Price drops:** 10% per week if the item got 3 or fewer inquiries that week, never below the floor.
9. **Tracking:** `tracker.xlsx` has Items, Daily Log, Conversations, Routine Check and Settings sheets.

### Effort data from item 01

| Step | Time |
|---|---|
| Photos received → draft ready | ~14 min (comps took ~2 min) |
| Clay's involvement, photos → form filled | ~37 min window, about 6 short actions |
| Setup before the first item | 2 sessions, plus a 16-day wait for photos |

No cost or token figures were recorded.

### Friction seen

- The browser pane used for research can't upload files, so posting needs Claude in Chrome on the PC. That means two browsers.
- Facebook blocked the first post because the account was acting as a Page ("Pages can't use Marketplace"). Clay had to switch to his personal profile by hand.
- Typing in the browser timed out once, though the text came through. Facebook's category names don't match the draft's.
- Few local comps, and Facebook prices are asking prices, not sale prices.

### Guardrails already in place

- Clay signs in himself.
- Every post and message needs his OK.
- No home address anywhere.
- City-level location only.
- Own photos only.
- Honest AI disclosure.
- Scam checklist.
- Recall check before listing.
- A human pace ("a few listings per session, no bulk posting").

## Starting thoughts on monetization

These are unverified first ideas for the wayfinder session to test, not decisions.

**Possible models:**

- **A. Done-for-you local selling service.** People in Greenville hand over items or photos; the agent prices, lists and handles chats; you take a commission or a per-item fee. Niches: downsizing, moves, estate cleanouts, realtor referrals. The trust and logistics come from a human; the agent keeps the cost per item low.
- **B. Self-serve listing assistant (software).** Photos go in; out come a priced, recall-checked, paste-ready listing and reply drafts. The seller posts it themselves. This avoids automating anyone else's Facebook account, but the field is crowded: crosslisting tools, plus the AI listing features the platforms build in.
- **C. Sell the know-how.** A packaged skill or template, a guide, or content ("how AI sells my garage"). Low effort, likely low revenue. Fits the content channels Clay already runs.
- **D. Use it yourself as a reseller** (buy low, sell). This is monetization without customers.

**Biggest open questions (the fog):**

- **Platform risk.** What do Meta's Terms and Commerce Policies say about automated posting, and about listing other people's items from your profile? This was never checked against Meta's own text. It decides whether A can run on Facebook at all, and whose account it would use.
- **Unit economics.** What does an average item sell for, how many sell, and how much human and Claude time and money goes into each? There is one data point and zero sales.
- **Demand.** Who would pay, and how much? Do local competitors exist (consignment shops, estate sale companies, eBay drop-off stores)?
- **Channels beyond Facebook.** eBay has an official selling API; Marketplace largely doesn't for individuals (to verify).
- **Delivery.** Today the agent needs Clay's PC, his Chrome and his sign-in. A service needs a different setup.

## Next step: run wayfinder

Matt Pocock's wayfinder skill is copied into this repo (`.claude/skills/`), and its tracker is set to local markdown in `marketplace-agent/wayfinder/` (`docs/agents/issue-tracker.md`).

Start a **new** session on this repo (skills load at session start) and type:

```
/wayfinder Turn my Facebook Marketplace listing agent into a paid service. Context is in marketplace-agent/README.md.
```

Charting the map takes one session and is a conversation: it asks you questions to name the destination (for example, "pick one model and a spec for a 30-day pilot"), then creates the first tickets.
