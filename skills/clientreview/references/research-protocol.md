# Prospect Research Protocol

Shared by `/personalreview`, `/clientreview` and `/coldemail`. An identical copy lives in each skill's `references/` folder so every skill stands alone.

**Reading this from GitHub?** This is the whole protocol — you don't need anything else installed to follow it. Every step names a fallback that works with plain `WebSearch` / `WebFetch`.

Raw source: `https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/clientreview/references/research-protocol.md`

## Why this exists

These skills stake their credibility on findings being *real* — a scorecard that invents a review count or a competitor name is the one thing that gets an agency caught. This turns "live research on the prospect" from a vague instruction into a defined pass, run through the **agent-reach** skill (`https://github.com/Panniantong/Agent-Reach`) where it's available and named fallbacks where it isn't.

## Rule 0 — declare, then tag everything

1. **Say what you're using** before you start — one line, e.g. "Researching via agent-reach: Jina Reader for the site, Exa for the category, Reddit unavailable."
2. **Tag every finding** with one of three provenance classes:

| Tag | Means |
|---|---|
| `[retrieved: channel/backend, YYYY-MM-DD]` | Pulled off the internet this run |
| `[live prompt]` | You answered the buyer's query as the assistant. Legitimate primary evidence — you *are* one of the assistants their buyers ask |
| `[inferred]` | Neither. A reasonable read, but unverified |

**The hard rule:** an `[inferred]` finding may shape narrative and internal judgement, but it can never become a score digit, a named competitor, a review count, or any number on a client-facing page. When retrieval fails, the honest output is "unverified this run" — never a plausible-looking number.

## R0 — Check what's actually live

```bash
agent-reach doctor --json
```

- **Command not found** → agent-reach isn't installed on this machine. Use the fallback ladder at every step below and keep tagging. Nothing here requires it.
- Record each channel's `active_backend` and pick commands to match.
- **`warn` is not broken.** It usually means an auth check the doctor won't run live. Try the channel once; on error, drop to the fallback. Never spend more than one retry on a dead channel.

## R1 — Read their site the way an AI reads it (never skip)

Two fetches per key page — what an assistant can *extract*, and what's in the *markup*:

```bash
# what an AI actually gets out of the page
curl -s "https://r.jina.ai/https://example.com"

# what the markup declares
curl -s -L "https://example.com" | grep -ioE 'application/ld\+json|<title>[^<]*|og:[a-z]+|name="description"'
```

Pages worth the pass: home, main product/category, about, contact, dealers / where-to-buy, one spec or technical page.

What it measures — this is the step that converts guesses into findings:

- Jina returns thin or empty text while the page looks fine in a browser → the content is JS-rendered, image-baked, or PDF-trapped. **That is the site-readability score, measured rather than assumed.**
- No `application/ld+json` → no structured data. Straightforward, checkable.
- Business name / address / phone differing across pages → entity inconsistency, with the specific pages as evidence.
- Spec links resolving to PDFs → the single highest-value finding for the building-products ICP.

*Fallback:* `WebFetch` the same URLs. Its cleaned text is a **weaker** readability proxy than raw Jina — it can make an unreadable site look fine. Say so rather than scoring it as if measured.

## R2 — Who the sources name instead

Ladder: `mcporter` → Exa MCP → `WebSearch`.

```bash
mcporter call 'exa.web_search_exa(query: "best metal roofing supplier ontario", numResults: 5)'
```

Run, adapted to the prospect:

- the **mid-band** buyer prompt (the one that's both winnable and has volume)
- `best [category] [region]`
- `[business name]` alone — what the internet says they *are* (entity check)
- `[business name] reviews`
- `[category] association / directory [region]`

Yields cited-source presence, the roundup + directory target map, and competitor names you can print **because you retrieved them**.

## R3 — Community signal

```bash
opencli reddit search "query" -f yaml     # desktop, needs the browser extension
rdt search "query" --limit 10             # standalone fallback
```

Reddit is a genuine ChatGPT retrieval source, not a nice-to-have. If both routes are down, try a scoped web search (`site:reddit.com …`) and tag it as the weaker source it is. If nothing works, record **"community signal unverified this run"** — don't guess.

## R4 — Size, spend, and people

- **LinkedIn** — headcount band, who owns marketing. See agent-reach `references/career.md`. Feeds the fit check and the value ceiling in quote math.
- **Meta Ad Library** — active ads mean a real budget and a qualified prospect. Web fetch / search.
- **Decision-maker name** (coldemail especially) — from the about/team pages already pulled in R1. **Never fabricate an email address**; a bounce costs deliverability. Generic `info@` with a named human to address is the honest output.

## R5 — Reviews and entity consistency

Not an agent-reach channel. Use targeted search and fetch for the Google rating + count and whichever platforms matter for their type. If a rating won't surface at all, **that is itself the finding** (thin or under-optimized GBP) — record it as such, not as a blank.

## R6 — Video / podcast

Only when relevant — rare for building products. `yt-dlp` is zero-config and live by default.

## Retrieval does not replace the live-prompt pass

R1–R6 are retrieval. The **AI-answer-presence test** — you answering the buyer's query as the assistant across the broad / mid / narrow breadth ladder — is still run exactly as each skill describes, and tagged `[live prompt]`. Retrieval corroborates it and supplies competitor names you've confirmed are real. It doesn't substitute for it.

## Reporting what you ran

- **`/personalreview`** → a 🔒 internal line naming channels, backends, and gaps: *"Site via Jina; category via Exa; Reddit unavailable — community signal unverified."*
- **`/clientreview`** → plain language inside *What we scanned*, **no tool names ever**: *"We read your site the way an AI assistant reads it, searched the sources those assistants cite, and ran five buyer questions live."*
- **`/coldemail`** → not mentioned to the lead; it feeds the Research snapshot and the AI-visibility table.

## Workspace

Temporary output goes in `/tmp/` or the session scratchpad. Never write research files into the client's project or into the skill directory.
