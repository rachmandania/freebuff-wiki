# Freebuff & Buffy — notes and sources

**English below · Bahasa Indonesia di bawah**

Research notes behind the fan-made wiki **[freebuff.fandom.com/wiki/Freebuff_Wiki](https://freebuff.fandom.com/wiki/Freebuff_Wiki)**, written in simple language for people who have never coded, in English and Indonesian. Every fact here was checked against the official pages listed under [Sources](#sources) on **24 November 2026**.

---

## What is in here

| Path | What it is |
| --- | --- |
| [`docs/en.md`](docs/en.md) | Full English notes: what Freebuff is, who Buffy is, platforms, capabilities, how to start, cost, limits, FAQ, glossary |
| [`docs/id.md`](docs/id.md) | Catatan lengkap Bahasa Indonesia (isi yang sama) |
| [`wiki/`](wiki) | The raw wikitext of every published wiki page — the source of truth for what is live |
| [`NOTES.md`](NOTES.md) | Verification log: which claims were checked where, and which earlier claims turned out wrong |

## Quick facts

| Topic | Answer |
| --- | --- |
| What it is | A free AI coding agent, funded by text ads |
| The agent | Buffy — the AI you talk to; the main loop is called **base3** |
| Made by | The Codebuff team, on the open Codebuff framework |
| Where | Desktop (macOS/Windows/Linux), CLI, Web, Cloud, Chat, iOS, Android, Website Builder, Cowork |
| Modes | Plan (read only) and Build (can change files) |
| Cost | Free; optional paid plans add model hours |
| Licence | Apache-2.0 ([CodebuffAI/freebuff](https://github.com/CodebuffAI/freebuff)) |
| Site | [freebuff.com](https://freebuff.com) · docs: [docs.freebuff.page](https://docs.freebuff.page) |

Three details worth knowing before you repeat anything about Freebuff:

* **Models change constantly.** The catalog is rented per use, so names come and go. The page explains the mechanism — hours per model — instead of freezing a list that will be stale.
* **Balances are in hours**, since 2026-10-15, at **1 hour = 5 Freebucks**. Free access is 5 hours a day, or 4 on a VPN or proxy.
* **Plan and Build are cleanly separated on Desktop**, but the CLI ties the root agent to the selected model and an internal lite mode. Do not assume Desktop behaviour applies to the CLI.

## Sources

* [freebuff.com](https://freebuff.com) — products, platform list, models, store
* [README on GitHub](https://github.com/CodebuffAI/freebuff) — model catalog, hours and Freebucks, access tiers, data notice, licence
* [docs.freebuff.page/working-with-the-agent](https://docs.freebuff.page/working-with-the-agent) — the loop, Plan and Build, tool groups, helper limits
* [docs.freebuff.page/cli](https://docs.freebuff.page/cli/) — install command, Node requirement, config paths
* [Launch post](https://freebuff.com/blog/freebuff-launch) — subagents, slash commands, positioning
* [codebuff.com/docs](https://codebuff.com/docs) — the framework, and its orchestrator "Buffy"

## Referral link

This wiki is run by one person. If you want to try Freebuff and support the wiki at the same time, use the referral link below. It costs nothing extra, the app is the same one, and part of it goes to keeping the wiki online.

**https://freebuff.com/?ref=ref-ee33d868-d2dc-4b5e-a4d8-8156352d2f60&via=settings_earn_link**

It is labelled as a referral link on every wiki page too, so no reader is misled into thinking it is the plain official link.

## Licence and scope

Wiki text is published on Fandom under **CC BY-SA** unless noted otherwise. This is an unofficial fan project: not affiliated with, endorsed by, or sponsored by Freebuff or Codebuff. Prices, model names and daily limits change often — check the official site before relying on a number.

---

# Bahasa Indonesia

Catatan riset di balik wiki buatan penggemar **[freebuff.fandom.com/wiki/Freebuff_Wiki](https://freebuff.fandom.com/wiki/Freebuff_Wiki)**, ditulis dengan bahasa sederhana untuk orang yang belum pernah ngoding, dalam bahasa Inggris dan Indonesia. Semua fakta di sini dicek ke halaman resmi di bagian [Sumber](#sumber) pada **24 November 2026**.

## Isi repo ini

| Path | Isinya |
| --- | --- |
| [`docs/id.md`](docs/id.md) | Catatan lengkap Bahasa Indonesia |
| [`docs/en.md`](docs/en.md) | Catatan lengkap bahasa Inggris (isi sama) |
| [`wiki/`](wiki) | Wikitext mentah setiap halaman wiki yang sudah terbit |
| [`NOTES.md`](NOTES.md) | Log verifikasi: klaim mana dicek di mana, dan klaim lama mana yang ternyata salah |

## Fakta singkat

| Topik | Jawaban |
| --- | --- |
| Apa ini | AI coding agent gratis, dibiayai iklan teks |
| Agent-nya | Buffy — AI yang kamu ajak bicara; siklus utamanya bernama **base3** |
| Dibuat oleh | Tim Codebuff, di atas framework Codebuff yang terbuka |
| Bisa dipakai di | Desktop (macOS/Windows/Linux), CLI, Web, Cloud, Chat, iOS, Android, Website Builder, Cowork |
| Mode | Plan (hanya baca) dan Build (bisa mengubah file) |
| Biaya | Gratis; paket berbayar menambah jam model |
| Lisensi | Apache-2.0 ([CodebuffAI/freebuff](https://github.com/CodebuffAI/freebuff)) |
| Situs | [freebuff.com](https://freebuff.com) · dokumentasi: [docs.freebuff.page](https://docs.freebuff.page) |

Tiga hal yang perlu diketahui sebelum mengulang informasi soal Freebuff:

* **Model terus berubah.** Katalognya disewa per pemakaian, jadi nama masuk dan keluar. Halamannya menjelaskan mekanismenya — jam per model — bukan menulis daftar yang bulan depan sudah salah.
* **Saldo dihitung dalam jam**, sejak 2026-10-15, dengan **1 jam = 5 Freebucks**. Akses gratis 5 jam sehari, atau 4 kalau pakai VPN atau proxy.
* **Plan dan Build terpisah rapi di Desktop**, tapi CLI mengikat agent akar ke model terpilih dan mode lite internal. Jangan menganggap perilaku Desktop berlaku sama di CLI.

## Sumber

* [freebuff.com](https://freebuff.com) — produk, daftar platform, model, toko
* [README di GitHub](https://github.com/CodebuffAI/freebuff) — katalog model, jam dan Freebucks, tingkat akses, pemberitahuan data, lisensi
* [docs.freebuff.page/working-with-the-agent](https://docs.freebuff.page/working-with-the-agent) — siklus kerja, Plan dan Build, grup tool, batas pembantu
* [docs.freebuff.page/cli](https://docs.freebuff.page/cli/) — perintah install, syarat Node, lokasi config
* [Postingan peluncuran](https://freebuff.com/blog/freebuff-launch) — subagent, slash command, posisi produk
* [codebuff.com/docs](https://codebuff.com/docs) — framework dan orkestratornya, "Buffy"

## Link referral

Wiki ini dikelola satu orang. Kalau kamu ingin mencoba Freebuff sekaligus mendukung wiki ini, pakai link referral di bawah. Tidak ada biaya tambahan, aplikasinya sama, dan sebagiannya untuk menjaga wiki ini tetap online.

**https://freebuff.com/?ref=ref-ee33d868-d2dc-4b5e-a4d8-8156352d2f60&via=settings_earn_link**

Labelnya juga ditulis terbuka di setiap halaman wiki, supaya pembaca tidak salah mengira itu link resmi biasa.

## Lisensi dan lingkup

Teks wiki diterbitkan di Fandom di bawah **CC BY-SA** kecuali dinyatakan lain. Ini proyek penggemar tidak resmi: tidak berafiliasi, tidak didukung, dan tidak disponsori Freebuff atau Codebuff. Harga, nama model dan batas harian sering berubah — cek situs resmi sebelum memakai sebuah angka.
