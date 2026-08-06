---
name: personalreview
description: Internal-only prospect review and quote for Geongyn — fit check, baseline AI visibility, prioritized jobs, job price sheet, 2-3 good-better-best packages (upfront + monthly) priced per niche, website/hosting add-ons, internal quote math with margin, and a TAKE/RAISE/PASS verdict. Use when Josh says "/personalreview [business]", "quote this prospect", "should I take this one", "price this deal", or names a package after a review (which switches to fulfillment mode). Never send any part of this to a prospect — the client-facing version is /clientreview.
---

# /personalreview — Internal Prospect Review & Quote

**This is the internal-only version. Never send any part of it to a prospect.** It does the honest assessment: fit, real work needed, package scope, price with margin math, and a take/raise/pass verdict. The client-facing `/clientreview` is a filtered, polished view of sections 2–4 plus one price.

## Invocation

`/personalreview [business name] [website] — [category], [city]`
Optional adds: est. revenue, # locations, who referred them, anything already known.

If a field is missing, research it. Don't ask Josh to fill in what you can find.

## Sources of truth (in this order)

1. The **ai-business-recommendation-geo** skill — for how engines actually retrieve and who gets recommended. Follow its priority order (GBP + reviews first for local; **for the primary building-products ICP the order is different — see the addendum at the end**; listicles are *corroboration only*, never a primary lever).
2. **`C:\Users\joshr\geongyn-marketing\plan\final_plan.md`** — for ICP (§2), pricing logic (§8), and positioning. This is the live source. Section 2 also carries the correction that building products is *not* an unoccupied vertical — never pitch it as empty.
3. Live research on the prospect (below).

> **Note, 2026-07-28:** earlier versions of this skill cited a `geongyn-context.md` v1.2 as source #2. **That document could not be located** — not in Drive, not locally — and Josh confirmed he has no record of it either. It has been replaced by the plan file above, which is real, current, and version-controlled. Do not go looking for it.

**Do not** use the v1.0 team doc's unverified figures (e.g. "60%+ ask AI", "41% from listicles", "14.2% vs 2.8%", "+40%", "3x", star-filter thresholds) in any number that could reach a client. Internally, flag them as unverified if referenced. Also banned: **"66% of B2B buyers use AI to find suppliers"** — surfaced during research 2026-07-27, unverified, excluded.

## Scope — what we do NOT offer

- **No social media content creation.** Never propose social posts, captions, or social content calendars as a job, package inclusion, or upsell. Not part of any package.
- "Content" in this skill always means **on-site website/blog content** published on the client's own domain, for the AI content-freshness signal — never social.

## Step 0 — Silent research pass (do this before writing anything)

Gather, quietly:

- **Business type** → determines everything downstream:
  - *Building-product manufacturer / supplier* (**primary ICP** as of 2026-07-27 — see the addendum at the end) → structured product data, spec/technical content, dealer-network listings, trade directories, contractor-facing retrieval path
  - *Local service* (detailer, dentist, contractor, med spa…) → GBP/Places retrieval path
  - *DTC e-commerce* → product-review density, marketplace/retailer presence, Reddit + comparison/roundup content, structured product data
  - *B2B services / SaaS* → G2/Capterra, category & comparison pages, docs, roundups
- **Owned domain?** (their own root domain vs. a subdomain of a platform/brokerage)
- **Local only:** GBP claimed? Exact primary category correct? Review count + rating across Google / relevant platforms. Velocity of recent reviews.
- **AI visibility now — test a query-breadth ladder, not one phrase.** Run the buying queries by actually answering them as the AI would (you're Claude — generate the recommendation an assistant gives). Test three rungs and note where they surface across all of them:
  - **Broad** — generic, category-agnostic intent ("best metal roofing"). Usually the wrong intent and unwinnable — they compete against the whole landscape.
  - **Mid** — specific enough to signal their lane, broad enough to carry real buying volume ("metal roofing supplier near [town]"). **The target.**
  - **Narrow** — exact category/product ("standing seam manufacturer"). They may win here, but volume is thin.
  - Capture **who's named instead** at each rung (that's the hook), and identify the **mid-band** — where discovery intent meets winnability — as the real goal. Typical pattern: *buried when broad, wins when narrow → aim at the mid.*
  - *Two fronts:* if they have both a physical location and a shippable product, "near me"/local queries hit the **local GBP front**, product queries hit the **product front** — score them separately. And **"near me" queries are the most location-grounded**, so a cold read is a weaker proxy — flag those for live validation in a location-grounded assistant.
- **Size / spend signals:** apparent revenue band, # locations, and marketing spend (Meta Ad Library — active ads = real budget = qualified).

## Step 1 — Fit check

Classify segment: **Primary** building-product manufacturers & suppliers · **Secondary** DTC e-com $1–10M · **Tertiary** B2B services / SaaS · **Local service** (case-by-case, not core).

Verdict: **Strong fit / Stretch / Pass.**

Auto-flags (any hit = call it out explicitly):

- Excluded category (e.g. restaurant) or margin/pricing mismatch → likely Pass
- No owned domain / lives on a platform or brokerage subdomain → nothing independent to optimize → Pass
- Reviews or entity signals so thin the retrieval gate can't realistically be cleared in a reasonable window → flag as a delivery risk, not an easy win
- Revenue clearly outside the band (too small to afford / too big to need us)

## Step 2 — Baseline visibility (the hook evidence)

State plainly what AI says about them *right now*: which engines name them (if any) for their category + geography, and — more importantly — **who gets named instead.** Note the retrieval path for their business type so the diagnosis is honest about *why* they're invisible. This is the raw material `/clientreview` turns into the wake-up moment.

## Step 3 — Jobs to be done (prioritized, branched by business type)

List the actual gap-closing work *this* prospect needs. Tag each with **effort** (Low/Med/High) and **impact**. Order by leverage, following the GEO skill.

**Building-product manufacturer / supplier** (primary ICP):

1. Machine-readable product & spec data — get gauge/profile/span/finish/warranty attributes out of PDFs and into extractable on-page content
2. `Organization` + `Product` + `Offer` + FAQ structured data
3. The client's EXISTING spec sheets and technical documentation republished as HTML, not PDF-only (we republish what they have; we do not author it)
4. Dealer / distributor / where-to-buy pages so regional queries can resolve
5. Trade directory + association + supplier-listing presence (the corroboration layer engines cite)
6. Front-loaded factual category and product pages, entity-clear
7. Review signal where it exists (Google, industry platforms) — weaker lever here than for local services, but not zero
8. Contractor-facing decision content (comparison, sizing, spec guidance) on their own domain

**Local service** (in order):

1. Claim + correctly categorize GBP (silent kill-switch if wrong)
2. Review volume at high rating + velocity (targets from the GEO skill; verify per category)
3. NAP consistency across GBP, site, booking, directories
4. Front-loaded factual site + LocalBusiness/FAQ schema
5. Independent corroboration (local news, Chamber, genuine Reddit, legit awards)

**DTC e-commerce:**

- Product-review density + rating on the pages engines actually read (own PDPs + where they aggregate)
- Presence in the third-party comparison/roundup/"best X for Y" content engines cite for the category — earn genuine inclusion, don't fabricate
- Reddit / community mentions for the category (a real retrieval source for ChatGPT)
- Structured product data + plain, front-loaded, extractable copy on category & PDP pages
- Marketplace / retailer presence where relevant

**B2B / SaaS:**

- G2 / Capterra / category-directory presence + reviews
- Clear comparison & category pages, docs, plain extractable copy
- Third-party roundups & analyst/blog corroboration

## Step 4 — Job price sheet (the T-chart)

Turn the prioritized jobs into a two-column sheet, split by billing type. Each job gets a plain-English name a layperson understands (say what it *does for them*, not the technical term) and a price. Keep it tight.

**One-time jobs**

| Job | Price |
|---|---|
| … | $ |

**Recurring jobs (monthly)**

| Job | Price/mo |
|---|---|
| … | $/mo |

This sheet is the à-la-carte breakdown behind the packages — used on a call only if the prospect asks "what's each piece?"

## Step 5 — Packages (what you actually sell)

Bundle the jobs into **2–3 good-better-best packages built for THIS prospect** (not a fixed global menu). Each package = **one upfront fee + one monthly fee**, both pitched together, with a plain-English "what you get" list Josh can read straight off a sales call. Mark the recommended one with ⭐.

Standard shape (rename per prospect):

- **Launch — get found:** the foundation fixes + monitoring. The "yes but smaller" option.
- **⭐ Growth — get recommended:** Launch + active outreach + fresh on-site content. The one that moves them into AI answers. This is the anchor.
- **Dominate — own the category:** Growth + aggressive outreach/PR + weekly reporting.

Write each package as:

**NAME — one-line promise**
**$X upfront + $Y/mo**

- **plain-language inclusion** — *one short line: what this is and why it helps them*
- **plain-language inclusion** — *one short line: what this is and why it helps them*

Rules:

- **Every inclusion gets a one-line sub-description** underneath — what the thing is and what it does for them, in words a layperson gets. Keep it to a single line.
- Use a **build-on structure** to avoid repetition: describe each unique item once. Growth reads "Everything in Launch, plus:" then only its *new* items (with their sub-descriptions); Dominate reads "Everything in Growth, plus:" then only *its* new items.
- Keep inclusions jargon-free: "Rewrite your product pages so AI can read and quote them," not "PDP schema extraction."

## Step 6 — Quote math (INTERNAL ONLY — never show the prospect)

**Price by niche — every time.** Identical scope is worth wildly different amounts depending on the prospect's economics; two prospects with the same job list should often get *different* prices. Never reuse a prior prospect's numbers as a template — re-derive from *their* niche. First establish two things:

- **What one new customer is worth to them** — deal size × margin × repeat / lifetime value. For building products this is almost always an **account**, not an order (see addendum).
- **How healthy their margins are** — fat-margin service niches price on value; thin-margin volume businesses price closer to cost + a modest premium, because the number has to survive their P&L. A great value story a prospect's margins can't digest still doesn't close.

Then build the number in three moves:

1. **Production floor** — cost *to you* to deliver (hours × loaded rate + API + tools). Low, because production is AI-leveraged. Sets margin and walk-away.
2. **Value ceiling** — keyed to their niche: (AI-referred customers you can plausibly win per month) × (what one is worth to them). This is why a high-LTV niche ceiling sits far above a low-margin one for identical scope.
3. **Recommended** — between floor and ceiling, positioned by margin health: nearer the ceiling for fat-margin niches, nearer the middle for thin ones.

Rough niche calibration (a starting instinct, not a rule — always sanity-check against the prospect's real numbers):

- **High-margin / high-LTV** (med spa, cosmetic & dental, PI law, custom builders): premium.
- **Mid** (HVAC, roofing installers, boutique B2B services): moderate.
- **Thin-margin / volume** (material wholesalers, manufacturers, lumber, commodity supply): leaner on a per-order read — **but see the addendum: price these on account value, not unit margin, or you will systematically underprice the primary ICP.**

Output as a short list:

- **Recommended (⭐ package):** $ upfront + $/mo · margin ~__%
- **Floor / stretch:** upfront $–$ · monthly $–$
- **Room:** how far you can flex before margin thins
- **Value anchor:** the niche-specific fact that justifies it — what one customer is worth to them
- **Motion:** which package to pitch first, and the fallback

**No hard floor exists** → end with a verdict:

**TAKE / RAISE / PASS** — is (recommended × margin) worth Josh's time given effort + delivery risk? If winning them means dropping below that point, say PASS and why.

## Step 6b — Website add-on (one-time, stacks under any retainer)

Geongyn also builds full websites — GEO/AEO/SEO-native and conversion-engineered (behavioral psychology: attention direction, authority framing, trust signals, one dominant CTA). Not a template shop's site: a Geongyn build *raises* the AI-visibility score instead of being the thing that needs fixing later. Offer it as a one-time add-on beneath the chosen package — never a fourth package.

Tiers (present as options; **price each per niche in the quote math — no fixed menu**):

- **One-Page** — clean single-scroll
- **Multi-Page** ⭐ — 4–8 pages
- **Product/Catalog** — full line + quote/cart flow (the manufacturer and DTC lane)
- **+ Motion graphics** — animation add-on, any tier (premium up-sell, fattest margin)

Rules:

- **Niche-priced like the retainer** — anchor to what a converting site is worth to them.
- **Absorb the page-rewrite job** — if they buy a build, the one-time page-rewrite line disappears; don't double-bill.
- **Motion vs. extraction:** keep all real content in server-readable HTML; motion is enhancement only, or you'd ship a site that scores *worse* on the thing you optimize for.

**Recommend the build only when the site warrants it** (site-quality trigger):

- **Broken / thin / DIY / template site** (e.g. placeholder text, Squarespace stub) → **lead with the build** — it's the wedge.
- **Solid existing site, or they already have a web agency** → **soft-offer or skip.** Pushing a rebuild on a working site (or poaching another agency's client) reads pushy and can sink the whole deal. Fold the readability fix into the page-rewrite instead.

### Hosting & Care (recurring, its own line — only if we build/host)

Tier by **how often the site changes, not its size.** Keep it a separate line from the GEO retainer so if they ever pause GEO, the site stays up and the hosting revenue holds. Niche-flex the Care tiers, but hosting has hard costs so it carries a real floor (~$50/mo).

- **Host-Only** — static sites (rarely changes)
- **Standard** ⭐ — occasional edits / monthly publish
- **Active** — weekly menu / product / price updates (e.g. rotating catalogs)

*Note:* a website + Active Care deal can make sense for an **excluded-niche** business (e.g. a restaurant) even when the full GEO retainer doesn't — it's a standalone product decision.

## Step 7 — Expansion path

Where the account grows: per-location pricing, added service/product pages, a corroboration/PR push, additional brands the owner controls, moving from retainer into a higher tier of scope. Give a rough timeline (e.g. revisit at month 3 / month 6).

## Step 8 — Watch-outs (internal candor — the stuff the client never hears)

Be blunt here. Cover:

- **Can you actually deliver the promise?** Is the category winnable? Can the review/entity gap realistically be closed in a sane window? Is retrieval gated by something you *can't* fix (no GBP eligibility, walled-garden-only presence, a dominant incumbent with 900 reviews)?
- **Payment / scope risk** — signs of a haggler, a scope-creeper, or a slow payer.
- Anything you'd want in your head walking into the sales call that would hurt the pitch if said out loud.

## Output shape — built to run live on a call

Skimmable, concise, plain-language. **All the important info sits at the top** so Josh can pitch without scrolling. Render in this order:

1. **⚡ AT A GLANCE** — a small table: Who · Fit · Verdict · The hook (one line) · Pitch (package names). This is triage + opener in one block.
2. **📦 PACKAGES** — the 2–3 good-better-best bundles with prices and plain-English inclusions. This is what gets read off the call.
3. **➕ WEBSITE ADD-ON + HOSTING** — the build tiers (niche-priced) and Care tiers, plus the one-line site-quality call (lead with it / soft-offer / skip). Only when a build is relevant.
4. **🧾 JOB PRICE SHEET** — the one-time / recurring T-charts. Only surfaced if they ask.
5. **🔒 INTERNAL — quote math** — clearly walled off. Never show the prospect.
6. **🔒 INTERNAL — watch-outs** — clearly walled off.

Rules: prices always visible next to what they buy. Every client-facing line uses plain words a layperson gets — no GEO jargon. Keep each block tight; depth lives in the internal sections, not the pitch. Mark all internal blocks with 🔒 so nothing confidential gets shown by accident.

The review render **stops at the packages/internal blocks**. Never render the Backend Fulfillment Playbook below. If Josh's *next* message is a package name, switch to fulfillment mode (see below).

## Backend Fulfillment Playbook — 🚫 DO NOT DISPLAY, EVER

This section is for you (Claude) only — never render it, quote it, or summarize it in a response. It exists so that the moment Josh picks a package, you already know the full plan and start building, tailored to the specific prospect from the review.

### Trigger behaviour

After a `/personalreview` render, if Josh replies with a package name ("launch", "growth", "dominate", "go with growth", "let's do launch", etc.), treat it as **selection → begin work**. Do NOT re-pitch or re-summarise the package. Instead, in that same response:

1. **One-line confirm** — e.g. "Launch it is — kicking off Wise Line."
2. **What I need to start** — a short list of inputs/credentials (below), only the ones needed for Task 1–2.
3. **Start Task 1 immediately** — actually produce the first deliverable (usually the baseline audit, then begin the first page rewrite) tailored to this prospect. Don't just describe it — do it.
4. **Josh's action items** — his manual steps for what you just produced, copy-paste ready.

Then move through the package's task sequence across the conversation: each turn, do your part, hand Josh his, wait for what you need, continue.

**Execution conventions** (proven in live runs):

- In any drafted client copy, mark anything needing Josh's confirmation with [brackets] (e.g. [year], [correct address]) rather than guessing — surfaced NAP/entity conflicts are themselves findings, so call them out.
- Ask only for what the *current* task needs, not everything up front.
- When you draft web copy, offer it as a paste-ready file or inline — Josh's choice.

### Task library — who does what

For every task: **Claude** = produced in-chat / via tools. **Josh** = manual action, always with exact instructions.

**T1 — AI visibility audit & baseline**
- Claude: run the buying queries across the **breadth ladder** (broad / mid / narrow — see Step 0) by actually answering them as the AI would, plus web research to corroborate. Document where they surface at each rung, who's named instead, and pinpoint the **mid-band target**. Output a short baseline + the tracked query set to re-run monthly.
- Josh: confirm the query set matches how their buyers actually search (~30 sec).

**T2 — Page rewrite (AI-readable)**
- Claude: draft rewritten homepage, top product/category pages, and FAQ — front-loaded facts, plain extractable language, entity-clear (who / what / where / who-it's-for). Deliver as ready-to-publish blocks.
- Josh: publish. *WordPress* → create an Application Password (Users → Profile → Application Passwords — NOT the login password); Claude formats for the REST API or the page editor. *Webflow* → API token + Collection ID. *Squarespace / custom HTML* → copy-paste; Claude marks exactly where each block goes.

**T3 — Structured data + business-info cleanup**
- Claude: generate JSON-LD (Organization / LocalBusiness + Product + FAQ) and an NAP audit table — every directory with wrong or inconsistent info and the corrected values.
- Josh: paste the JSON-LD into the site `<head>` (exact steps provided); claim/correct each listing (Google Business Profile, Bing Places, Apple Business Connect, BBB, industry directories) using the corrected details + direct links provided.

**T4 — Roundup / directory / community target map**
- Claude: research and list the "best [category] [region]" articles, directories, and genuine Reddit/forum threads the engines cite — each with the contact, the pitch angle, and whether it's editorial (earned) or a listing (submittable).
- Josh (Launch): receive the map. Outreach itself is Growth+.

**T5 — Roundup & directory outreach** *(Growth+)*
- Claude: draft personalised outreach for each target + submission copy for directories.
- Josh: send from the domain email (deliverability) or approve a batch; log replies back.

**T6 — Review generation system** *(Growth+)*
- Claude: build review-request templates (email + text) + a simple SOP and cadence for asking customers / dealers / contractors.
- Josh: send to recent customers; set the follow-up trigger (e.g. after each order/delivery).

**T7 — Fresh on-site content** *(Growth+)*
- Claude: write the monthly on-site article(s) — GEO-optimised, humanised, brand-voice, on their own domain. **Never social.**
- Josh: publish (WP API or paste).

**T8 — Monitoring & reporting**
- Claude: re-run the tracked queries, log movement + competitor changes, produce the report (monthly for Launch/Growth, weekly for Dominate).
- Josh: review and forward to the client.

### Per-package fulfilment

**LAUNCH — get found**
- *Offers:* foundation visibility fixes + monthly tracking. Makes them readable, consistent, and findable so they *can* be surfaced; light ongoing watch. No outreach, reviews, or content.
- *One-time, in order:* T1 audit → T2 page rewrite → T3 schema + info cleanup → T4 target map (delivered, not actioned).
- *Monthly:* T8 monitoring & report only.
- *Need from Josh to start:* site publishing access (WP App Password or confirm copy-paste); list of profiles/directories they already have; correct NAP (legal name, address(es), phone, hours).

**GROWTH — get recommended** *(anchor)*
- *Offers:* everything in Launch, plus active pursuit of AI-answer inclusion — outreach into the roundups/threads engines cite, a review-building engine, and fresh on-site content.
- *One-time:* all Launch one-time tasks.
- *Monthly, in order:* T5 outreach → T6 review system (build month 1, then maintain) → T7 fresh on-site content → T8 monitoring & report.
- *Need from Josh to start:* everything in Launch + domain email for outreach + list of recent customers/dealers to request reviews from.

**DOMINATE — own the category**
- *Offers:* everything in Growth, plus a heavier outreach/PR push, weekly reporting, priority turnaround.
- *Monthly:* Growth tasks at higher volume + expanded PR targets + weekly T8 reporting.
- *Need from Josh to start:* everything in Growth + PR assets (project photos, spec sheets, awards) + a point person for fast approvals.

*(These three are the standard shapes. If a review named/priced the packages differently for a specific prospect, follow that review's scope — this playbook maps the tasks, the review sets the specifics.)*

### Building-products fulfilment note (added 2026-07-27, corrected 2026-07-28)

For the primary ICP, T2 and T3 carry most of the weight. Getting gauge / profile / span / finish / warranty data out of the client's PDFs and into extractable, structured on-page content is the single highest-impact fix for a manufacturer.

**Do NOT offer to author specification sheets.** Geongyn does not provide that service — the Wise Line job was a one-off and is not a service line (Josh, 2026-07-28). Never quote it, never list it, never imply the capability. What is on offer is *republishing specification data the client already has* in a readable, structured form.

**The differentiator to lead with instead is the website build.** Competing agencies advise and hand over recommendations; Geongyn can execute the rebuild those recommendations depend on. For a manufacturer the fix largely *is* the website, which is why an advice-only agency stalls waiting on the client's web developer. See Step 6b.

---

## Addendum — primary ICP change (2026-07-27)

**Primary ICP is now building-product manufacturers and suppliers**, Ontario first: metal roofing and steel building products (priority lane), lumber yards and building-supply dealers, windows/doors/siding/cladding, concrete/precast/masonry. DTC e-commerce moves to secondary.

**The pricing consequence, which matters most:** Step 6's niche calibration files manufacturers and material wholesalers under thin-margin/lean pricing. Read literally, that underprices the primary ICP on every deal. The correction:

> **In building products the buyer is a contractor, builder, architect or spec-writer, and they convert into an account, not an order.** One contractor who begins specifying a manufacturer's product is worth **$50k–300k+ over several years**. Set the value ceiling from account value × plausible accounts won per year — never from per-unit margin.

This is consistent with Step 6's own instruction to "anchor to the volume of orders won over time, not a single sale." Apply it as the default for this segment, and state the account-value anchor explicitly in the quote math's **Value anchor** line so the number is defensible on the call.
