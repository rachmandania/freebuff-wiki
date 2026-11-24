# Freebuff & Buffy — full notes (English)

For people who have never coded. Words in *italics* are the plain-language idea; the rest is what the official sources actually say.

---

## Contents

1. [What is Freebuff](#1-what-is-freebuff)
2. [Who is Buffy](#2-who-is-buffy)
3. [Where you can use it](#3-where-you-can-use-it)
4. [What it can do](#4-what-it-can-do)
5. [How to start](#5-how-to-start)
6. [Is it really free?](#6-is-it-really-free)
7. [Limits](#7-limits)
8. [FAQ](#8-faq)
9. [Glossary](#9-glossary)
10. [Sources](#10-sources)

---

## 1. What is Freebuff

| Topic | Answer |
| --- | --- |
| What it is | A free AI coding agent, funded by text ads |
| The agent | Buffy |
| Made by | The Codebuff team, on the Codebuff framework |
| Where | Desktop, CLI, Web, Cloud, Chat, iOS, Android, Website Builder, Cowork |
| Modes | Plan (read only) and Build (can change files) |
| Cost | Free; optional paid plans add model hours |

Freebuff is not a search engine and not a chat box that only writes text back. It is a loop: it reads your project, decides on one action, uses a tool, reads the result, and decides again — until the job is done or it needs something from you.

Four layers are easy to mix up:

* **Model** — generates the reply and chooses the next action.
* **Agent** — gives the model a role, instructions, your project's context and a set of tools.
* **Tool** — does one concrete thing: read a file, search text, run a command, open a page.
* **Runtime** — decides where that happens: your machine or a cloud workspace.

Freebuff is made by the Codebuff team on top of [Codebuff](https://codebuff.com), an open multi-agent framework. It is often described as the free alternative to Claude Code, Codex CLI, Cursor, Windsurf and Devin.

The project is public: [github.com/CodebuffAI/freebuff](https://github.com/CodebuffAI/freebuff), licence Apache-2.0. It reads `AGENTS.md` and `CLAUDE.md`, so rules you already wrote for another agent still apply.

## 2. Who is Buffy

**Buffy** is the name of the AI agent you talk to in Freebuff — "ask Buffy" means the AI in the chat window. The name also appears in Freebuff's branding and on merchandise, including a ["Buffy on Fire" T-shirt](https://freebuff.com/store/buffy-on-fire-t-shirt).

Inside Freebuff, the main working loop is called **base3**: one agent investigates, edits and checks with its own tools. In Codebuff's documentation, "Buffy" is the name of the orchestrator agent — Freebuff is built on that framework, which is why the name carries over.

A turn looks like this:

1. **You ask** for something, in your own words.
2. **Investigate** — the agent lists, searches and reads before changing anything.
3. **Decide** — it picks one action: a tool call, a question, or an answer.
4. **Read the result** — output goes back into context, errors included.
5. **Repeat or report** — it continues until done, blocked, or in need of you.

The instructions say to check its own result and report checks it could not run. That is a rule it follows, not an independent audit: when a reply says "fixed", the evidence is the diff and the commands that actually ran.

**Helper agents** are additions to the main loop, not the default shape of a turn. At launch Freebuff shipped 9 specialized subagents; named ones include:

* **code-reviewer** — reads a change back and looks for problems.
* **browser-use** — drives a real browser.
* **file-picker** — finds which files matter for the request.
* **thinker-with-files-gemini** — deep thinking over your files.
* a **research** helper — reads documentation and current pages.

Limits: up to **6 helpers** per spawn request, up to **20 code subagents** at once with Projects access; full code subagents are not offered in Plan mode and not on sponsored runs.

## 3. Where you can use it

| Version | What it is |
| --- | --- |
| Desktop | macOS, Windows and Linux. Runs agents on a folder on your own computer; parallel agents each get their own workspace |
| CLI | `npm install -g freebuff`, then `freebuff` inside the project. Node 16+ per docs, 18+ per the CLI page |
| Web | Runs in the browser at freebuff.com/app; aimed at building and shipping full-stack apps |
| Cloud | Runs agents on any GitHub repository, with a sandbox, preview, terminal and deploy flow |
| Chat | Free AI chat for questions and ideas; no project needed |
| Mobile | iOS and Android apps; follow and continue chats from your phone, including chats running on Desktop |
| Website Builder | Prompt-to-app builder with managed hosting, so you get a live URL |
| Cowork | A separate Freebuff surface for work outside pure coding |

## 4. What it can do

**Finding and reading**

* Map an unfamiliar project and explain how it fits together
* Read large files by line range instead of guessing
* Search code for a symbol, string or file name

**Editing and running**

* Edit files, create new ones, run tests, builds and installers in a real terminal
* Work with git: see the diff, commit, review
* Run your own hooks after a file changes

**Checking**

* Show a live preview of a running website next to the chat
* Drive a real browser: click, type, read console and network errors, take screenshots

**Shipping**

* Publish a site with database, file storage and sign-in
* Work directly on a connected GitHub repository

**Content and visuals**

* Documents, slides, spreadsheets and diagrams
* Images and simple page designs

**Information**

* Search the web and read documentation pages
* Ask a separate research helper for multi-source answers

**Connected apps**

* GitHub, Linear, Notion, Stripe, Vercel, Supabase, Sentry, PostHog, Resend, Google Drive/Docs/Sheets, Discord, Telegram
* MCP servers you add and approve

**Parallel work**

* Up to 6 helpers in one spawn request, up to 20 code subagents with Projects access

## 5. How to start

1. Open [freebuff.com](https://freebuff.com) and download Desktop, or open the web app.
2. Or use the terminal: `npm install -g freebuff`, then `freebuff`.
3. Open a project folder, or start an empty one.
4. Type a request in plain language, for example: *"Explain what this project does."*
5. Read the answer, then give the next small step.

Brief it like a ticket — three questions: **what** to do, **where** it may touch, and **how** you will know it worked (the command, test or URL).

Useful habits:

* Start in **Plan** mode on an unfamiliar project: nothing can be changed while you look around.
* One small step at a time beats "build the whole app".
* Keep the project in git so a bad change can be undone.

Documented flow from a vague idea to a reviewable change: `/interview` → `/plan` → implement → `/review`. Typing `@` points at a file, `/` opens the command list.

## 6. Is it really free?

Yes — text ads pay for the models instead of a subscription, and there is no card or API key.

* Balances are counted in **hours** since 2026-10-15. **1 hour = 5 Freebucks.**
* A model costs hours at the rate in the picker: an hour on a one-hour model uses one hour of balance, a three-hour model uses three, free experimental models use none.
* The free allowance depends on where you are: 30 hours a day in the United States, 21 or 12 in the countries listed there, 5 elsewhere, and 4 on a VPN or proxy. The full table is on the [Home page](https://freebuff.fandom.com/wiki/Freebuff_Wiki#How_much_does_it_cost?), and the daily pool is spent before your wallet.
* Referrals and bounties earn extra hours, which sit in a wallet and are spent after the daily allowance.

Current catalog (changes often — check the picker):

| Model | Access | Notes |
| --- | --- | --- |
| DeepSeek V4.1 Flash | Free + paid | Fast coding and tool use, 1M context |
| DeepSeek V4.1 Flash Slow | Free + paid | Same model, slower stream; default at limited access without a plan, and in Chat |
| DeepSeek V4.1 Flash Fast | Free + paid | Faster variant in limited-access regions |
| Solar Mini 4 | Free + paid | Upstage, compact, 500K context, text only |
| Solar Pro 4 | Free + paid | Upstage, larger, 500K context, text only |
| Muse Spark 1.3 | Paid | Meta agentic coding model, 1M context |
| Muse Ember | Paid | Meta fast coding model, 375K context |
| Claude Haiku 5.5 | Paid | Fast Anthropic model, 100K context |
| GPT-6.1 Terra | Paid | OpenAI, two sessions a day, 1M context, images |
| Beam 1.0 · Glyph Cluster · Nemotron 3.5 Lightning | Free experimental | Limited-access tiers |

Gemini 3.1 Flash Lite handles specialist jobs such as file finding instead of appearing in the main picker. Some models have already been retired: GLM 5.3 Flash, MiMo 2.6 Pro, GPT-6.1 Sol, Gemini 4 Argon, Gemini 3.8 Flash.

Desktop can also run locally installed Claude Code and Codex agents on your own provider account; those are separate from Freebuff's catalog.

**Data:** a model may only be used for training when its notice says so. Separately, Freebuff may use your usage data to train the models that choose and measure ads; project files and connected repositories are not given to advertising providers.

## 7. Limits

* Vague requests give vague results — say what "done" looks like.
* It will not type your passwords or log in for you.
* No OS sandbox on Desktop: commands run with your own user rights and can reach beyond the opened folder. Administrator rights are never granted implicitly.
* Unknown projects can carry executable settings; the CLI asks before trusting project-level agent or MCP configuration, and that trust is tied to a directory.
* It cannot promise perfect code; a green build is evidence about the build, not about everything else.
* Answers depend on which model the session is using.
* Free hours are limited per day; heavy use runs into the allowance.
* Plan and Build are cleanly separated on Desktop; the CLI differs, so check your installed version.
* Cloud chats keep separate copies of files — merging is yours, through git.
* Context is finite: long chats get compressed into a summary, so restate hard requirements.

## 8. FAQ

**Do I need to know programming?**
No, but it helps. You need to say clearly what you want and check the result.

**Is it really free?**
Ads pay for the models. No card and no API key; paid plans add hours.

**Can it break my project?**
It can make mistakes. Use Plan mode first for big changes and keep the project in git.

**Where does my code go?**
On Desktop it stays in the folder you opened. On Cloud it runs in a cloud workspace for that project.

**Can I choose the model?**
Yes — the picker shows each model and how many hours an hour on it costs.

**What is "Freebucks"?**
The credit unit. Balances are shown in hours; 1 hour = 5 Freebucks.

**Does it train on my code?**
Only when a model or feature says data may be used for training. Check that notice per model.

**What is base3?**
The name of Freebuff's main agent loop: one agent investigates, edits and verifies with its own tools.

## 9. Glossary

**Agent** — the AI that does the work, not just answers questions. Here its name is Buffy.
**Prompt** — the message you type to ask for something.
**Repo (repository)** — a project folder tracked by git, so changes can be reviewed or undone.
**Terminal** — the text window where commands are typed. Freebuff can use it for you.
**Build** — turning source code into something that runs, and checking that it does.
**Sandbox / workspace** — a separate place where the project runs. Cloud has one; Desktop does not isolate your OS.
**Mode** — how much power the agent has: Plan (read only) or Build (can change files).
**Subagent** — a helper given one narrow job; its result returns to the main agent.
**AGENTS.md** — a file where a project states its own rules and verification commands.
**Referral link** — a link that credits whoever shared it when a new user signs up.

## 10. Sources

* [freebuff.com](https://freebuff.com) — products, platform list, models and store
* [README on GitHub](https://github.com/CodebuffAI/freebuff) — catalog, hours and Freebucks, access tiers, data notice, licence
* [docs.freebuff.page/working-with-the-agent](https://docs.freebuff.page/working-with-the-agent) — loop, Plan and Build, tool groups, helper limits
* [docs.freebuff.page/cli](https://docs.freebuff.page/cli/) — install command, Node requirement, config paths
* [Launch post](https://freebuff.com/blog/freebuff-launch) — subagents, slash commands, positioning
* [codebuff.com/docs](https://codebuff.com/docs) — the framework and its orchestrator, "Buffy"

Checked on 24 November 2026. Prices, model names and daily limits change often, so these notes describe how they work instead of freezing numbers that will be wrong next month.

---

Unofficial fan project. Not affiliated with or endorsed by Freebuff or Codebuff. Referral link used by the wiki: https://freebuff.com/?ref=ref-ee33d868-d2dc-4b5e-a4d8-8156352d2f60&via=settings_earn_link
