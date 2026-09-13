# geongyn-skills

Geongyn's GEO + prospecting skills for [Claude Code](https://claude.com/claude-code), packaged as an installable plugin marketplace.

## Install

```
/plugin marketplace add josheywashey321/geongyn-skills
/plugin install geongyn-skills@geongyn-skills
```

Restart Claude Code afterward so the skills load.

## Use without installing (phone, borrowed machine, claude.ai)

No plugin, no marketplace, no restart. Paste a link and tell Claude to follow it:

> Read this skill and use it on [business + URL]:
> `https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/personalreview/SKILL.md`

Each skill is self-contained — the SKILL.md tells Claude which other file to fetch, and every file is a raw URL on this repo.

| Skill | Paste this URL |
|---|---|
| `chaseframe` | `https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/chaseframe/SKILL.md` |
| `clientreview` | `https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/clientreview/SKILL.md` |
| `coldemail` | `https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/coldemail/SKILL.md` |
| `personalreview` | `https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/personalreview/SKILL.md` |

## What's inside

| Skill | What it does |
|---|---|
| `chaseframe` | Chase Hughes' behavioral influence frameworks (FATE, the six social needs, decision filters) applied to copywriting, page layout, campaigns, and live sales calls. |
| `clientreview` | Client-facing AI Visibility Scorecard — scores a prospect /100 across six dimensions and shows the path to being recommended by AI assistants. |
| `coldemail` | Researches a business from just its URL and drafts warm, human cold outreach pitching GEO / AI-visibility and website services. |
| `personalreview` | Internal prospect review + quoting: fit check, prioritized jobs, good-better-best packages, and margin math. |

> **Heads-up:** `personalreview` contains internal quoting and margin logic. Installing this plugin makes that logic readable to anyone who installs it.

## How they research a prospect

All three run one shared **[research protocol](https://raw.githubusercontent.com/josheywashey321/geongyn-skills/master/skills/personalreview/references/research-protocol.md)** — a defined retrieval pass rather than a vague "look them up":

1. `agent-reach doctor --json` — see which channels are actually live
2. **Jina Reader on the prospect's site** — measures what an AI assistant can genuinely extract from it, which is the site-readability finding rather than a guess about it
3. Exa search — who the cited sources name instead
4. Reddit / LinkedIn — community signal and company size

This runs through the [agent-reach](https://github.com/Panniantong/Agent-Reach) skill when it's installed. **It is not required.** Every step names a plain `WebSearch` / `WebFetch` fallback, so the skills work unchanged on a machine that has never heard of agent-reach.

Every finding is tagged `[retrieved]`, `[live prompt]`, or `[inferred]`. Only the first two may become a number, a score, or a named competitor on anything a client sees — an unverified figure on a scorecard is the one mistake that costs the account.

## chaseframe

The persuasion framework the other three draw on. Built on **FATE — Focus → Authority → Tribe → Emotion** — treated as a ladder where every rung is load-bearing: no Focus and the reader never enters; no Emotion and they agree with every word and do nothing.

Its most-used feature is diagnostic rather than generative. When a page or campaign underperforms, you find the broken rung before rewriting anything:

| Symptom | Broken rung |
|---|---|
| Nobody engages | Focus |
| Traffic, no depth | Authority |
| Engaged, never shortlisted | Tribe |
| Shortlisted, then stalls forever | Emotion |

Frameworks are sourced and tagged `[primary]` / `[secondary]` / `[contested]`, with disagreements between sources stated rather than smoothed over. The frameworks decide sequence, framing and emphasis — never whether a claim is true; the verified-claims rule applies to everything built with it.
