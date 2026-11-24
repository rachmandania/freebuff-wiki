# Verification log

Checked on **24 November 2026**. Everything below was re-read on the official pages, not recalled from memory.

## What was checked, and where

| Claim | Source that decides it | Verdict |
| --- | --- | --- |
| Freebuff is funded by text ads, no card or API key | freebuff.com, README | Confirmed |
| Products: Desktop, CLI, Web, Cloud, Chat, + mobile apps | README "Choose your Freebuff" + site | Confirmed; Cloud is specifically *agents on any GitHub repository* |
| Website Builder, Cowork exist | freebuff.com nav (`/website-builder`, `/cowork`) | Confirmed |
| Install command `npm install -g freebuff`, then `freebuff` | README quick start, docs CLI | Confirmed |
| Node requirement | docs CLI says Node >= 16; freebuff.com/cli says 18+ | **Conflict** — wiki names both instead of picking one |
| Plan = read only, Build = can change files | docs "Plan and Build" | Confirmed for Desktop |
| CLI behaves differently (root agent tied to model + internal lite mode) | docs "Plan and Build" | Confirmed — added as a caveat |
| Slash commands `/interview`, `/plan`, `/review`; `@` for files, `/` for commands | launch post, site UI text | Confirmed |
| Main agent loop is named **base3** | docs "The main agent" | Confirmed |
| "Buffy" is the orchestrator name | codebuff.com/docs | Confirmed |
| 9 specialized subagents ship in the box | launch post | Confirmed as a launch claim |
| Named helpers: code-reviewer, browser-use, file-picker, thinker-with-files-gemini | launch post | Confirmed |
| Up to 6 helpers per spawn call, 20 concurrent with Projects; not in Plan, not on sponsored runs | docs "Helper agents" | Confirmed |
| Balances in hours since 2026-10-15; 1 hour = 5 Freebucks | README | Confirmed |
| Free allowance 5 hours/day, 4 on VPN or proxy | README | Confirmed |
| Model catalog | README model table | Confirmed at time of check |
| Gemini 3.1 Flash Lite used for file finding, not in the picker | README | Confirmed |
| Retired models: GLM 5.3 Flash, MiMo 2.6 Pro, GPT-6.1 Sol, Gemini 4 Argon, Gemini 3.8 Flash | README | Confirmed |
| "Buffy on Fire" T-shirt in the official store | freebuff.com store | Confirmed |
| Licence Apache-2.0 | GitHub repo | Confirmed |
| No OS sandbox on Desktop | docs "What to keep in mind" | Confirmed |
| Data used for training only where a model says so; usage data may train ad models | README privacy section | Confirmed |

## Claims that were wrong in earlier drafts, and what replaced them

| Wrong claim | Reality |
| --- | --- |
| "Models: DeepSeek, GLM, MiMo, MiniMax, GPT-class, Gemini-class" | GLM, MiMo and MiniMax are gone from the catalog. Current: DeepSeek V4.1 Flash / Flash Slow / Flash Fast, Solar Mini 4, Solar Pro 4, Muse Spark 1.3, Muse Ember, Claude Haiku 5.5, GPT-6.1 Terra, plus free experimental Beam 1.0 / Glyph Cluster / Nemotron 3.5 Lightning |
| "Daily allowance of Freebucks" | Balances are shown in hours now; Freebucks is the credit unit at 5 per hour |
| "First release 2025" | Not supportable. Repository exists since 2024-07-09; the public launch post is dated 2026. Removed |
| "Helper agents: code searcher, file picker, web researcher, browser driver, reviewer" | Names were guesses. Only code-reviewer, browser-use, file-picker, thinker-with-files-gemini and a research helper are documented |
| "Press Tab to switch between modes" | Not documented anywhere. Removed |
| "Buffy is the mascot" | Only provable part: the name is used in branding and on merchandise. Softened |
| "Cloud = a cloud computer" | Cloud is *agents on any GitHub repository*; the workspace is the mechanism, not the pitch |
| "Each language page had tabs" | Tabs hid the content and looked like plain text on the dark mobile skin. Replaced by a single page with a nav menu, a contents list and jump links |

## Wiki page revisions at time of writing

| Page | Revision |
| --- | --- |
| `Freebuff_Wiki` (Home, EN) | 187 |
| `Freebuff Wiki (Bahasa Indonesia)` | 188 |
| `Freebuff` | 183 |
| `Freebuff (Bahasa Indonesia)` | 184 |
| `Buffy` | 185 |
| `Buffy (Bahasa Indonesia)` | 186 |

## Checks run on the live pages

* 0 red links, 0 broken `#` anchors across 114 jump links.
* Tables render (3 on Home, 5 on Freebuff, 2 on Buffy).
* Exactly one labelled referral link per page.
* No raw wiki syntax leaking into the rendered text.
* Clicking a contents entry scrolls to that section (`#Capabilities` verified).

## Known gaps

* Mobile layout of the wide platform table was not visually checked.
* Fandom renders its own automatic "Contents" box above the article, separate from the hand-written contents list.
* Model names, prices and daily hours will drift; the notes describe mechanisms on purpose.
