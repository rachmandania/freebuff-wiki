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
| Free allowance 5 hours/day, 4 on VPN or proxy | README (superseded) | **Wrong as stated** — the Discord FAQ of 22 November 2026 gives 30 hours in the US, 21 or 12 in listed countries, 5 elsewhere, 4 on a VPN or proxy. The wiki now points at the regional table instead of repeating one number |
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
| "Free access is 5 hours a day, 4 with a VPN" | True of the 9 November announcement only. The 22 November Discord FAQ replaced it with hours per region; the article pages now name the regions and link to the table instead of repeating one number |

## Wiki page revisions at time of writing

| Page | Revision |
| --- | --- |
| `Freebuff Wiki` (Home, EN) | 225 |
| `Freebuff Wiki (Bahasa Indonesia)` | 226 |
| `Freebuff` | 243 |
| `Freebuff (Bahasa Indonesia)` | 244 |
| `Buffy` | 241 |
| `Buffy (Bahasa Indonesia)` | 242 |
| `What's new` | 245 |
| `What's new (Bahasa Indonesia)` | 246 |
| `Details` (new page) | 233 |
| `Detail (Bahasa Indonesia)` (new page) | 234 |

## Changes after the 24 November restructure

| Change | Where |
| --- | --- |
| Tabs dropped, one page per language with a nav menu, contents list and jump links | all ten pages |
| Section headings rewritten as reader questions; contents lists cut to 4–5 entries | all ten pages |
| Home compacted from ~14 KB to ~9 KB; model catalog and glossary moved out | `Freebuff Wiki`, `Freebuff Wiki (Bahasa Indonesia)` |
| Model catalog, plan bonuses and glossary moved to two new pages | `Details`, `Detail (Bahasa Indonesia)` |
| Free allowance no longer stated as "5 hours a day, 4 on a VPN": the pages point at the regional table on Home instead | `Freebuff`, `Freebuff (Bahasa Indonesia)` |
| Release notes CLI 0.2.37 (09:26 UTC) and 0.2.38 (19:06 UTC) added to the dated list, with Discord permalinks; the 0.2.37 note is merged into its commit entry so there is one entry and one link | `What's new`, `What's new (Bahasa Indonesia)` |
| The menu row in both languages carries the Details/Detail link (six rows were missing it and were fixed) | `Buffy`, `Freebuff`, `What's new` (both languages) |

## Checks run on the live pages

* 0 red links on all ten pages, checked through the parser output rather than by eye.
* Jump links whose heading ends in a question mark work: the stored id is `What_is_Freebuff.3F`, the link `[[#What is Freebuff?]]` matches it, and clicking it scrolled the page to that heading.
* Cross-page jump verified: `[[Freebuff Wiki#How much does it cost?|Home page]]` on `Freebuff` opens the Home page with that heading 46 px from the top.
* Tables render (14 rows in the model table on `Details`, 3 tables on both Detail pages, no stray `|-` rows).
* Menu on every page links to both `Details` and `Detail (Bahasa Indonesia)`.
* Every page states exactly one labelled referral link where it has one, and no raw wiki syntax leaks into rendered text.

## Known gaps

* Mobile layout of the wide platform table was not visually checked.
* Fandom renders its own automatic "Contents" box above the article, separate from the hand-written contents list.
* Model names, prices and daily hours will drift; the notes describe mechanisms on purpose.
* `docs/en.md` and `docs/id.md` are the older long-form notes. They were written before the restructure and still describe the tab-free 2026-11 layout in more words than the wiki pages now use.
