---
name: coldemail
description: >-
  Research a business from just its URL and draft a warm, human cold email pitching GEO / AI-visibility
  and/or website services, plus a full pitch strategy. Use this whenever Josh drops a lead's website link
  and wants outreach — "draft a cold email for this lead", "here's the next link", "write outreach for
  this business", "reach out to this prospect" — even if he doesn't say the word "cold email". Also use it
  when he pastes a business URL with little other context during a prospecting session. This is Josh's
  Geongyn prospecting workflow: research → AI-visibility check → tailored email → pitch → likelihood →
  price points → fixes.
---

# Cold Email (Geongyn prospecting)

This skill turns a single business URL into a complete, ready-to-send outreach package for **Josh at Geongyn**, who sells **GEO / AI-visibility** and **website** services to local businesses (mostly small-town Ontario — Simcoe, Norfolk County, Tillsonburg and nearby).

The whole point is that the email must feel like it was written by a sharp human who *actually looked at their business* — not a mail-merge blast. Everything below serves that.

For the underlying mechanics of *how* AI assistants pick and recommend local businesses (review targets, GBP category as kill-switch, per-engine levers, entity/Knowledge-Graph signals, schema behaviour), **invoke the `ai-business-recommendation-geo` skill** and lean on it. This skill is the outreach wrapper around that knowledge.

## The non-negotiable first move: check reality before you write

**Always run the AI-visibility check before deciding the angle.** Do not assume a business is invisible. Run the real query a customer would type — `best [service] in [city]` — through WebSearch and see whether the lead shows up, where it ranks, and what the answer says about it. The entire email angle depends on this, and getting it wrong destroys credibility. (Josh once corrected an email that led with "you don't show up on AI" when the business actually ranked first. Never repeat that.)

The result puts every lead into one of three angle buckets — see "Pick the angle" below.

## Research sequence

Do this research in parallel where you can (batch the tool calls). Gather:

1. **The website** (WebFetch): exact business name, services, city/address, phone, email, owner/staff names + credentials, hours, booking method, pricing, socials, and a critical read of the site itself — platform (WordPress/GoDaddy/Wix/custom?), modern or dated, mobile, content structure, CTA quality, conversion/SEO gaps, schema/FAQ presence.
2. **The AI-visibility check** (WebSearch): `best [service] in [city]` — who shows up, in what order, what the AI says about them, and which competitor (if any) it favours and why (awards? "largest"? more reviews?).
3. **Reviews** (WebSearch): Google star rating + count, plus TripAdvisor/Yelp/Birdeye/etc. Note whether a rating even surfaces — if it doesn't, that itself is a finding (thin/under-optimized GBP).
4. **The owner** (WebSearch + WebFetch of about/team/bio pages): real name and, ideally, the best email to reach them. **Never fabricate an email** — a guessed address that bounces hurts deliverability. If only a generic `info@`/gmail exists, say so and suggest the best human to address.
5. **The story / credibility signals**: awards, "best of" wins, years in business, founding story, family legacy, differentiators. These are gold for a genuine opener and are usually under-surfaced on their own site.
6. **Socials**: which platforms are active, and whether they're linked from the site (walled-garden socials that AI can't read are a recurring gap).

## Pick the angle (the tailoring logic — this is the heart)

The email angle is dictated by what the AI-visibility check found. Match it honestly:

- **Not showing up at all →** "get found / become the name AI recommends." Lead with GBP + reviews + schema.
- **Showing up but ranked below or tied with a competitor →** "you show up, but you're getting undersold — you're a coin-flip, not the clear #1." Name what the AI credits the competitor for (an award, being "the biggest") and what of theirs is missing from the answer (reviews, differentiators, story). This is the most common case.
- **Already the clear #1 →** do NOT pitch visibility. Pitch **conversion + modernization / defending the crown**: their reputation hands them the customer, but a dated/order-less/thin site then leaks them. Frame it as "stop wasting the customers you've already won" and "hold the spot as newer players modernize."

Two more tailoring rules that override the defaults:

- **Only pitch a full website redesign when the site genuinely warrants it.** Dated GoDaddy/2016-era build with info trapped in PDFs → redesign is honest and strong. Already-modern site → do NOT pitch a rebuild (it reads as a canned upsell and kills trust); lead with GEO / entity optimization + light on-site enhancements instead.
- **Match pain points to the actual gaps you found.** Draw from: no/weak Google reviews vs. walled-garden Facebook reviews, mis-/under-categorized GBP, no schema, reviews not surfaced on-site, entity/name confusion (a brand name that doesn't say what they are), info locked in PDFs/flip-books, no online ordering/reservations, incomplete NAP, socials not linked, no pricing/hours. Pick the two or three that bite hardest — don't list all of them.

## Voice: how the email must read

This is what Josh cares about most. The email is warm, human, and specific — like a knowledgeable person who noticed something, not a marketer running a sequence.

- **Open with a genuine, specific observation that proves you looked** — usually the AI-query finding, backed by a real fact (their exact review count, an award, their founding year, their #1 ranking). The compliment must be earned and concrete, never generic ("I love your business").
- **Make the status quo / competitor the quiet villain** — name the rival or the gap plainly, but never trash-talk. Reframe their own strength as the reason to act (loss-aversion beats gain: "you're not the name it lands on" hits harder than "you could get more customers").
- **Match the brand's register.** A barbershop gets a looser, punchier voice ("your website's doing you dirty", "what your chair already knows"). A medical clinic gets professional-but-human. A 38-year family restaurant gets warm and legacy-respecting. A gym gets energetic. Read the business and write to it.
- **Keep it ~150–220 words.** Short enough to read in one breath, long enough to land two or three pain points subtly. No jargon dumps, no feature lists, no "I hope this email finds you well."
- **Close with a low-commitment CTA — the free audit.** Josh's preferred close, roughly: *"Want me to run a quick free audit through my system and show you exactly where the gaps are? No pressure — just the rundown."* Adapt the wording to the email's voice.
- **Signature, always:**
  ```
  Josh
  Geongyn — geongyn.com
  ```
  (No phone number.)
- Give a subject line (plus 1–2 alternates) that reads like a human wrote it, not a campaign. Curiosity or a specific observation beats hype.

When in doubt about voice, read `references/email-examples.md` — five real, approved emails across a gym, a rehab clinic, a barbershop, an Italian restaurant, and a 24/7 gym. Mirror their rhythm, not their exact words.

## The deliverable (what to output every time)

Produce all of this, in this order. Josh likes the research rendered as compact tables/snapshots.

1. **Research snapshot** — a two-column table: business, location, contact, owner, socials, reviews, website. Flag standout facts.
2. **AI-visibility check** — a plain-language mini-audit table with columns **Item · Finding · Health · Next action**, using 🟢/🟡/🔴 for health. Always cover: do they appear, where they rank, review strength, the key gap, and schema. Finish with a one-line "honest read" that states the angle.
3. **The email** — subject + 1–2 alternate subjects, then the full body ready to send, then a short *italic* note explaining why it works (the hook, the villain, the close).
4. **What to pitch** — the tailored offer stack, ordered, matched to the angle and the site's real state.
5. **Likelihood of success** — a score out of 10 with honest reasoning (competitive set size, their sophistication, budget sensitivity, the strength of the hook, main risk).
6. **Price points (CAD)** — a table with a low-friction entry offer, optional retainer, and any rebuild — see pricing bands below.
7. **Fixes / logistics notes** — the concrete things they could fix (doubles as proof for the audit) and any contact caveats (e.g. no public email → suggest FB message or a name to address).

## Pricing bands (CAD)

Price so the entry offer never scares a small operator but never gives away value. Always offer the **free audit** as the foot-in-the-door, and tie prices to outcomes the owner feels (enrolments, bookings, orders, memberships) rather than "rankings" or "SEO".

- **Free AI-visibility audit** — $0, the wedge, every time.
- **Small owner-operator** (barbershop, small gym, single-practitioner, small café): entry GEO/visibility build **$1,200–$2,200**; optional monthly **$150–$500/mo**. Keep retainers light — don't oversell.
- **Higher-revenue / multi-staff** (medical/rehab clinic, multi-practitioner, established restaurant): entry GEO build **$1,500–$2,500**; monthly **$500–$900/mo**.
- **Website rebuild (only when warranted)**: **$1,200–$2,200** simple; **$2,500–$4,000** when it includes online ordering/reservations/e-commerce. Anchor on concrete ROI (e.g. direct online ordering that dodges 20–30% third-party app commissions; a rebuilt site that converts the traffic AI already sends).
- Bundling a prepaid entry + few months of retainer into a single "special" is a fair closing lever.

Adjust within these bands based on the business's evident size and budget sensitivity. When Josh says "go leaner" or "go premium", shift accordingly.

## Notes that carry across leads

- Leads so far are small-town Ontario (Simcoe / Norfolk County / Tillsonburg). Expect crowded-but-tiny competitive sets, which makes winning the AI recommendation very achievable and worth saying so in the likelihood score.
- Offer a casual LinkedIn DM or Facebook-message variant when the owner is more reachable there than by email (common for owner-operators and businesses with no public email).
- If Josh gives feedback on tone or approach mid-session, apply it to every subsequent lead — and if it's a durable preference, note it in memory.
