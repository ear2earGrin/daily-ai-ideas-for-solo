# Daily Idea: 2026-08-28 — AI Answer-Engine Mystery Shopper for Local Businesses

**One-sentence pitch**  
A one-person agent service that pretends to be a customer asking ChatGPT, Gemini, Grok, Perplexity, Google AI Overviews, and Maps "where should I eat / book / go," then compares what the models say against the business's real hours, menu, prices, booking link, and reviews — and sells the owner a weekly "this is what AI tells people about you" report plus a punch-list of listing fixes.

## Why this idea right now (from X / web scan)
- X this week is full of "I built a 6-person company with AI agents" posts (research → outreach → sales → builder → support → finance, human gate on send/spend). The realistic starting point people keep repeating is *one boring agent that solves one painful problem for $500–$2,000*, not a $1M autonomous company.
- Voice-agent-for-SMBs and no-code agent marketplaces (publish an agent, keep ~70%) are loud. Those are crowded. The quieter, paid gap is *what answer engines already tell customers about a shop before anyone calls*.
- Web/indie lists this week keep circling "AI mystery shopper for restaurants" because a large slice of diners now ask a model where to eat, and most kitchens have no idea they are being recommended with last year's hours, a dead booking link, or a hallucinated "closed Mondays."
- Same pattern exists for clinics, gyms, dentists, hotels, law offices, and local services. The product is a watcher + report, which matches the 2026 solo-agent playbook: overnight loop, human review on anything that goes to a client, subscription or setup + monthly.
- Distinct from ideas already in this repo (regulation briefing, SaaS crash-test, website+chat factory, FaceTime receptionist, Main Street OS). This one sells *visibility in the new front door*, not ops software.

## Core product
An "AI Mystery Shopper Desk" for one city first (Sofia), one vertical first (restaurants + cafes), then clinics and local services.

1. **Probe agents**  
   Every week, run a fixed battery of prompts in multiple engines, locales, and languages (BG + EN):  
   - "Best [cuisine] near [neighborhood] tonight"  
   - "Is [Business] open now? Do they take walk-ins?"  
   - "Book a table at [Business] for 2 at 20:00"  
   - "What do people complain about at [Business]?"  
   Capture answers, cited sources, maps cards, and screenshots.

2. **Ground-truth agents**  
   Pull the live site, Google Business Profile, Facebook, booking widget, menu PDF, and last 30 reviews. Store hours, phone, address, booking URL, price band, dietary tags. Hash pages so you know what changed.

3. **Diff + severity agents**  
   Score each mismatch: wrong hours, closed-when-open, missing booking, hallucinated dishes, dead phone, competitor recommended instead, review cluster the owner has never answered, model that never mentions them at all.

4. **Report agents**  
   Fixed 2-page template:  
   - How often you appeared in "best of" answers this week  
   - Exact quotes from each engine  
   - 5 ranked fixes (listing, site schema, GBP, review replies, one FAQ paragraph models can quote)  
   - Optional draft replies / schema / GBP copy  
   Quiet weeks still get a "nothing material changed" receipt.

Human (you) role: pick the first 20 venues, review the first reports so tone is "helpful inspector not scolding consultant," sell in person or via Instagram/X DMs, and do the 30-minute walkthrough when someone wants you to apply the fixes. Agents do the weekly probing.

## Monetization paths
- **Primary: Monthly mystery-shop subscription** — €29–€79/mo per location (weekly probes + report). €99–€149 for groups (2–5 locations).
- **Setup audit** — €99–€249 one-time: first full probe + fix list + you apply the top 3 listing changes with them.
- **Done-for-you fixes** — €150–€400 to rewrite GBP, add FAQ/schema, draft 10 review replies, fix booking link.
- **Agency / chamber channel** — sell a 20-venue pack to a hotel group, restaurant association, or local marketing shop.
- **Later** — self-serve dashboard. Keep high-touch setup human.

Realistic early target: 15 venues at €39 + 3 setup audits + one done-for-you pack → ~€1k/mo. Compute is cheap; the scarce part is a clean report a busy owner will actually read on their phone.

## How a one-person team with AI agents executes this

### Day 0–4 — Build the MVP harness
- Pick 5 Sofia restaurants you already know. Manually ask Grok / ChatGPT / Gemini / Maps the same 6 prompts. Save answers.
- Agent 1: run those prompts on a schedule, store raw text + screenshot.
- Agent 2: scrape/fetch GBP + site + menu, extract hours/phone/booking.
- Agent 3: write the 2-page diff report in the fixed template. You edit until it sounds like a local, not a slide deck.
- Delivery: PDF or Telegram. No app.

### Day 5–14 — First paying users
1. Walk into (or DM) 10 owners with one page: "This is what AI told a tourist about you on Thursday." That artifact sells better than a pitch.
2. Offer the first month free if they let you screenshot the before/after of their listing.
3. Charge the second month. Owners who forward the PDF to a manager are buyers.
4. Post anonymized "AI said you close on Mondays / you don't" comparisons on X. Local + bilingual content travels in founder and hospitality circles.

### Ongoing leverage
- Every accepted/rejected mismatch becomes few-shot memory ("this chain always has two GBPs").
- Add one engine or one vertical at a time.
- Productize outreach: an agent finds venues that never appear in "best of [neighborhood]" answers and drafts the DM.
- Do **not** promise ranking in ChatGPT. Sell *accuracy and presence of the facts you control*.

## Tech stack suggestion (agent-friendly & low-cost)
- Probes: your existing agents hitting each answer engine + Playwright for Maps / pages that need a browser
- Ground truth: requests + Playwright; reuse PDF→markdown patterns for menus
- Diff + write: Grok / Claude for first pass; you review anything that names a competitor unfairly
- State: SQLite or Supabase (venues, weekly snapshots, sent reports)
- Delivery: Resend or Telegram
- Billing: Stripe Checkout per location
- Guardrails: store raw model output, never invent a ranking guarantee, human queue when the model slanders the venue

## Fun / learning upside
You get a living map of how answer engines *actually* talk about a city. That corpus is useful for hospitality, tourism boards, and your own projects. It is also a fun personal tool: run it on your own sites and on friends' shops and watch listings drift.

## Next action if you want to start today
1. Pick one restaurant you like in Sofia. Ask four models: "Is [Name] open tonight and should I book?" Save the answers.
2. Compare to their Google listing and website. List every mismatch in 10 lines.
3. Send that one-pager to the owner (or a friend who knows them). Ask only: "Would a weekly version of this be worth €39?"
4. If one yes, write the probe agent tonight and add four more venues tomorrow.

---
Generated from X feed + web scan on 2026-08-28 (6-agent one-person companies with human approval; start with one paid boring agent not a fake unicorn; voice/SMB agents and agent marketplaces crowded; standing demand for AI mystery-shop / "what does ChatGPT say about this restaurant"; watcher + report pattern fits solo agent ops).
