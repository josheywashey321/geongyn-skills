---
name: clientreview
description: Produce a client-facing AI Visibility Scorecard for a prospect — a real scan scoring /100 across six dimensions, showing which AI answers name them (and who gets named instead), what's holding them back, and the outcome path to being recommended. Diagnostic on the surface, sales tool underneath. Use when Josh says "/clientreview [business]", "run a scorecard on", "scan this prospect", "AI visibility scorecard", or drops a prospect URL asking what AI says about them. No pricing ever appears on the output. The internal pricing counterpart is /personalreview.
---

# /clientreview — AI Visibility Scorecard (diagnostic on the surface, sales sheet underneath)

**What this is:** a scan that ranks how likely a prospect is to show up when a buyer asks an AI assistant for their category — then walks through everything that's holding them back and how it gets fixed. It reads as a diagnostic report. It functions as a sales tool. The prospect should feel *informed*, not *pitched* — the offer emerges from the diagnosis, it doesn't open the door.

This replaces the old proposal format. The engine underneath is still `/personalreview` (reuse its research + packages); this is how the findings get presented to the buyer.

## Portable use — no install required

This skill lives at **https://github.com/josheywashey321/geongyn-skills**. If you're reading this file from GitHub instead of an installed skill, fetch one more file before you start:

`https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/clientreview/references/research-protocol.md`

Those two files *are* the skill. Nothing else needs installing — the protocol names a plain `WebSearch` / `WebFetch` fallback for every retrieval step.

## Invocation

`/clientreview [business name] [website] — [category], [city]`

If a field is missing, research it. Don't ask Josh to fill in what you can find.

## The one rule that makes it work

**Every number and finding is real, pulled from an actual scan. Urgency is the genuine cost of staying invisible — never invented scarcity.**

Why this is non-negotiable (and not just ethics): a specific, true diagnosis is what gives it authority and what survives the prospect pushing back. A fabricated score or fake "2 spots left" is what gets an agency caught and killed on trust. Real findings, framed well, out-persuade hype every time. This also keeps it inside Geongyn's verified-claims standard.

### How the scan is actually run

**Run [references/research-protocol.md](references/research-protocol.md)** ([raw](https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/clientreview/references/research-protocol.md)) before scoring anything. It's the shared retrieval pass, run through the **agent-reach** skill where available: `agent-reach doctor --json` for what's live, **Jina Reader on their site to measure what an AI can actually extract**, Exa for who the cited sources name, Reddit for community signal. No agent-reach on this machine? The protocol's `WebSearch` / `WebFetch` fallback covers every step.

This is what makes the rule above enforceable rather than aspirational. Each finding carries a tag:

- `[retrieved]` — pulled off the internet this run
- `[live prompt]` — you answered the buyer's query as the assistant (legitimate primary evidence — you *are* one of the assistants their buyers ask)
- `[inferred]` — neither

**Only `[retrieved]` and `[live prompt]` findings may become a number on this page**, or a named competitor, or a review count. An `[inferred]` read can shape the wording; it can never be printed as fact. When a channel is down, the honest line is that the signal is unverified — never a plausible-looking figure. A fabricated number is the one failure this document cannot survive.

**Retired figures — never use.** The v1.0 team doc's unverified stats are banned from anything that could reach a client: "60%+ ask AI", "41% from listicles", "14.2% vs 2.8%", "+40%", "3x", and star-filter thresholds.

## No pricing — ever — on the scorecard

**No dollar figures. No tiers with numbers. No ranges. Not even a hint of cost.** Price on a diagnostic is the single tell that turns a report back into a sales sheet — the one thing this must never look like. Pricing lives only in `/personalreview` (internal) and gets built live on the call. The scorecard's job is to earn that call, not to quote.

## The score (so the ranking is defensible, not vibes)

Compute an **AI Visibility Score /100** from the scan. Six weighted dimensions:

| Dimension | Weight | Measures |
|---|---|---|
| AI answer presence | 30 | Are they actually named by ChatGPT / Perplexity / Gemini for real buying queries? |
| Cited-source presence | 20 | Are they in the roundups, directories, and communities AI pulls from? |
| Review signal | 20 | Volume × rating on the platforms that matter for their type |
| Site readability | 15 | Can AI parse and quote them? Structured data present? |
| Entity consistency | 10 | Does their business info match everywhere — one clear entity? |
| Freshness | 5 | Recent content / activity |

**Bands:** 0–24 *Invisible* · 25–49 *Emerging* · 50–74 *Competitive* · 75–100 *Dominant*. Lower score = more urgency AND more upside — say both. Score each dimension honestly from what the scan actually found; the per-dimension scores double as the problem list.

### Measure "AI answer presence" by actually asking the AI — across a breadth ladder

Don't just check who ranks in search, and don't test one phrase. **Run the buyer's prompts live through the AI (you, Claude)** across three rungs of breadth, and record where they surface at each:

- **Broad** — generic intent ("best metal roofing"). Usually wrong-intent and unwinnable.
- **Mid** — signals their lane with real volume ("metal roofing supplier near [town]"). **The target.**
- **Narrow** — exact category ("standing seam manufacturer Ontario"). May win, but thin volume.

You *are* one of the assistants their buyers ask, so this is a real reference. If they're not named, **name the competitors that were** — that's the "Where you stand" evidence. The usual pattern — *buried when broad, wins when narrow* — sets up the honest story: the winnable prize is the **mid-band**. Run 3+ prompts per relevant rung so it's a pattern, not a fluke.

*Local note:* "near me" prompts are the most location-grounded; a cold read is a weaker proxy, so validate those live before shipping. If the business has both a storefront and a shippable product, they have two fronts (local vs product) — scan whichever the prompt actually targets.

## The persuasion layer (the "hack" — applied to real findings only)

**The canonical framework is the `chaseframe` skill** ([raw](https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/chaseframe/SKILL.md)) — Chase Hughes' behavioral influence system (FATE: Focus → Authority → Tribe → Emotion), with the sourced frameworks, the six social needs and their paired fears, the four decision filters, and the full technique library. Read it when building a scorecard; it goes deeper than this summary on every point below. If it isn't installed, the condensed list here stands on its own.

The scorecard runs the FATE ladder in document form, and the mechanics land in roughly this order:

- **Attention direction (Focus)** — lead with the single number. It frames everything after it and controls what they fixate on.
- **Authority** — a real methodology, precise findings, the exact queries. Expertise they can't self-diagnose positions you as the one who sees what they can't. Hughes' *agentic shift*: in the presence of credited authority, the reader transfers responsibility for the decision — which quietly removes objections you never addressed.
- **Contrast + social proof (Tribe)** — the leaderboard: competitors named, they're not. Make the gap visceral with real names. Tribe means *businesses like them* — a same-town rival lands harder than a national brand.
- **Loss aversion / status-quo cost (Emotion)** — every buyer who asks and doesn't hear their name is a quote a competitor gets instead. Honest, concrete, ongoing. **This is the rung a diagnostic most often skips**, and skipping it is why a prospect can agree with every finding and still not book.
- **Specificity = credibility** — real queries, real competitor names, the actual broken details (e.g. placeholder text still on their site). Specifics are believed; generalities aren't.
- **Open loops** — each finding names the problem and implies a fix exists, pulling them forward to the next section (Zeigarnik effect).
- **Future pacing** — briefly let them picture the after-state: their name in the answers.
- **Anchoring** — the low score anchors the pain; the fix path is the relief.
- **One small yes** — close on a low-friction next step (a short call), not a big commitment.

**Match the paired fear to the buyer.** For the building-products ICP the reader is usually running *intelligence* (fear: being seen as having specified wrong) on a *conformity* or *investment* filter — so the scorecard persuades through data, standards and account math, never through hype. See `chaseframe`'s need→language table.

Chase-Hughes-style throughline: direct attention, establish authority, frame around their fear (being passed over) and desire (being the one chosen) — but every lever pulls on a true finding.

## Structure (render in this order — reads as a report, not a pitch)

1. **The Score** — big, top of page. AI Visibility Score: __/100 — [Band]. One line: this is how likely a buyer's AI assistant is to name you today.
2. **Where you stand** — run several real buyer prompts (3–5) and report the client's placement across all of them as a hit-rate. Rules:
   - **Every competitor you name must be `[retrieved]`** — confirmed to exist via the protocol's R2 search, not recalled from training. Naming a company that doesn't operate in their market is how the whole scorecard loses its authority in one line.
   - **Format:** competitor names as clean bullets, **one per line** — never a run-on sentence or block quote. Tag pointed ones (e.g. a same-town rival).
   - **Named in none** → show one representative prompt's list with the client visibly absent, then a single bold line: not named in any of the prompts we ran.
   - **Named in one or more** → lead with their **best** result: the single prompt where they showed up (or ranked highest). Display that list with them in it, then state plainly it was the *only* prompt that surfaced them and list the ones that didn't. Label it explicitly a **best-case scenario**, and name the fragility — change the wording and they disappear. This is the gut-punch, and it's real because you actually ran the prompts.
3. **What we scanned** — the exact buyer questions run, that you ran them through the AI directly, and — in plain language — that you also read their site the way an assistant reads it and searched the sources those assistants cite. Brief = methodology and authority. (This is the "report" cover.) **Never name a tool** — no "Jina", "Exa", "agent-reach", no CLI anything. The client hears *what* was examined, never *with what*.
4. **What's holding you back** — the per-dimension rundown. Each line: the score, what's wrong in plain words, and what it's costing them. This is the body and the credibility.
5. **The cost of staying here** — honest loss-aversion. Not doom; just the real math of invisibility.
6. **How each gap closes** — reassure them every issue is fixable, and describe the path in *outcome* terms, not products: get readable → get into the sources AI trusts → get named and stay named. **No prices, no package menu, no tier names with numbers.** The specific plan is built live on the call — that's what the next step is for.
7. **Next step** — one small, specific, low-friction yes (a short call to walk through the scan and build the plan). The plan and the investment are a conversation, never a line on the page.

## Tone & format

Reads like a specialist's report a step above the reader's knowledge — calm, precise, a little sobering, never hypey or salesy on the surface. Plain language, no GEO jargon, no internal anything (no margin, verdict, or watch-outs — this is fully client-facing). Concise. Address them as "you." Can be exported to a branded document later; content and sequence come first.

## Building-products addendum (added 2026-07-27)

Geongyn's primary ICP is now **building-product manufacturers and suppliers** (metal roofing and steel building products, lumber yards and building-supply dealers, windows/doors/siding/cladding, concrete/precast/masonry) in Ontario. When scanning one of these:

- **The buyer is a contractor, builder, architect or spec-writer**, not a consumer. Write buyer prompts accordingly: product/spec questions ("26 vs 29 gauge for an ag roof", "who makes standing seam panels in Ontario", "engineered truss supplier near [town]"), dealer/account questions, and regional supply questions.
- **Review signal is weaker and site readability is stronger** than for local services. Manufacturers are usually invisible for structural reasons: spec data trapped in PDFs, catalogs behind "call for pricing", no `Product` structured data, no machine-readable technical attributes, unlisted dealer networks. Weight the *narrative* toward those findings even though the numeric weights stay fixed.
- **The cost-of-staying-here math is account-based, not order-based.** One contractor who begins specifying a competitor's product is worth $50k–300k+ over several years. That is the honest loss-aversion frame for this niche — never a per-unit-margin frame.
