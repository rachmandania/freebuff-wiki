# Freebuff & Buffy — catatan lengkap (Bahasa Indonesia)

Untuk orang yang belum pernah ngoding. Istilah teknis dijelaskan dengan bahasa sehari-hari.

---

## Daftar isi

1. [Apa itu Freebuff](#1-apa-itu-freebuff)
2. [Siapa Buffy](#2-siapa-buffy)
3. [Bisa dipakai di mana](#3-bisa-dipakai-di-mana)
4. [Apa kemampuannya](#4-apa-kemampuannya)
5. [Cara mulai](#5-cara-mulai)
6. [Benar-benar gratis?](#6-benar-benar-gratis)
7. [Batasan](#7-batasan)
8. [Pertanyaan umum](#8-pertanyaan-umum)
9. [Glosarium](#9-glosarium)
10. [Sumber](#10-sumber)

---

## 1. Apa itu Freebuff

| Topik | Jawaban |
| --- | --- |
| Apa ini | AI coding agent gratis, dibiayai iklan teks |
| Agent-nya | Buffy |
| Dibuat oleh | Tim Codebuff, di atas framework Codebuff |
| Bisa dipakai di | Desktop, CLI, Web, Cloud, Chat, iOS, Android, Website Builder, Cowork |
| Mode | Plan (hanya baca) dan Build (bisa mengubah file) |
| Biaya | Gratis; paket berbayar menambah jam model |

Freebuff bukan mesin pencari dan bukan kotak chat yang hanya menulis teks. Ia bekerja dalam siklus: membaca project-mu, memilih satu tindakan, memakai tool, membaca hasilnya, lalu memutuskan lagi — sampai selesai atau sampai butuh sesuatu darimu.

Empat lapisan yang mudah tertukar:

* **Model** — menghasilkan jawaban dan memilih tindakan berikutnya.
* **Agent** — memberi model sebuah peran, instruksi, konteks project-mu dan satu set tool.
* **Tool** — melakukan satu hal konkret: membaca file, mencari teks, menjalankan perintah, membuka halaman.
* **Runtime** — menentukan di mana hal itu terjadi: komputermu atau workspace awan.

Freebuff dibuat oleh tim Codebuff di atas [Codebuff](https://codebuff.com), framework multi-agent terbuka. Ia sering disebut alternatif gratis untuk Claude Code, Codex CLI, Cursor, Windsurf dan Devin.

Project-nya publik: [github.com/CodebuffAI/freebuff](https://github.com/CodebuffAI/freebuff), lisensi Apache-2.0. Ia membaca `AGENTS.md` dan `CLAUDE.md`, jadi aturan yang sudah kamu tulis untuk agent lain tetap berlaku.

## 2. Siapa Buffy

**Buffy** adalah nama AI agent yang kamu ajak bicara di Freebuff — "tanya Buffy" maksudnya AI di jendela chat. Nama ini juga muncul di branding dan merchandise Freebuff, termasuk kaos ["Buffy on Fire"](https://freebuff.com/store/buffy-on-fire-t-shirt).

Di dalam Freebuff, siklus kerja utamanya bernama **base3**: satu agent yang menyelidiki, mengubah dan memeriksa dengan tool-nya sendiri. Di dokumentasi Codebuff, "Buffy" adalah nama agent orkestrator — Freebuff dibangun di atas framework itu, jadi namanya ikut terbawa.

Satu giliran berjalan begini:

1. **Kamu minta** sesuatu, dengan kata-katamu sendiri.
2. **Selidiki** — agent mendaftar, mencari dan membaca sebelum mengubah apa pun.
3. **Putuskan** — ia memilih satu tindakan: panggilan tool, pertanyaan, atau jawaban.
4. **Baca hasil** — keluaran masuk kembali ke konteks, termasuk error.
5. **Ulangi atau lapor** — berlanjut sampai selesai, terhalang, atau butuh kamu.

Instruksinya menyuruh agent memeriksa hasilnya sendiri dan melaporkan pemeriksaan yang tidak bisa dijalankan. Itu aturan yang ia ikuti, bukan audit independen: kalau jawabannya bilang "sudah diperbaiki", buktinya adalah diff dan perintah yang benar-benar dijalankan.

**Agent pembantu** adalah tambahan pada siklus utama, bukan bentuk default satu giliran. Saat peluncuran Freebuff membawa 9 subagent khusus; yang disebut namanya antara lain:

* **code-reviewer** — membaca ulang perubahan dan mencari masalah.
* **browser-use** — mengendalikan browser sungguhan.
* **file-picker** — mencari file mana yang penting untuk permintaan.
* **thinker-with-files-gemini** — berpikir mendalam atas file-mu.
* pembantu **riset** — membaca dokumentasi dan halaman terbaru.

Batasnya: sampai **6 pembantu** per permintaan spawn, sampai **20 subagent kode** sekaligus dengan akses Projects; subagent kode penuh tidak ditawarkan di mode Plan dan tidak di sesi bersponsor.

## 3. Bisa dipakai di mana

| Versi | Apa itu |
| --- | --- |
| Desktop | macOS, Windows dan Linux. Menjalankan agent di folder di komputermu; agent paralel masing-masing dapat workspace sendiri |
| CLI | `npm install -g freebuff`, lalu `freebuff` di dalam project. Node 16+ menurut dokumentasi, 18+ menurut halaman CLI |
| Web | Berjalan di browser di freebuff.com/app; fokus membangun dan merilis aplikasi full-stack |
| Cloud | Menjalankan agent pada repository GitHub mana pun, dengan sandbox, preview, terminal dan alur deploy |
| Chat | Chat AI gratis untuk pertanyaan dan ide; tanpa perlu project |
| Mobile | Aplikasi iOS dan Android; ikuti dan lanjutkan chat dari ponsel, termasuk chat yang jalan di Desktop |
| Website Builder | Pembuat aplikasi dari prompt dengan hosting terkelola, jadi langsung dapat URL hidup |
| Cowork | Permukaan Freebuff terpisah untuk pekerjaan di luar coding murni |

## 4. Apa kemampuannya

**Mencari dan membaca**

* Memetakan project yang belum dikenal dan menjelaskan cara bagian-bagiannya menyatu
* Membaca file besar per rentang baris, bukan menebak
* Mencari simbol, teks atau nama file di dalam kode

**Mengubah dan menjalankan**

* Mengubah file, membuat file baru, menjalankan test, build dan installer di terminal sungguhan
* Bekerja dengan git: lihat diff, commit, review
* Menjalankan hook pemeriksaanmu sendiri setelah file berubah

**Memeriksa**

* Menampilkan preview website yang sedang jalan di samping chat
* Mengendalikan browser sungguhan: klik, mengetik, membaca error console dan network, mengambil screenshot

**Merilis**

* Mempublikasikan situs dengan database, penyimpanan file dan login
* Bekerja langsung di repository GitHub yang terhubung

**Konten dan visual**

* Dokumen, slide, spreadsheet dan diagram
* Gambar dan rancangan halaman sederhana

**Informasi**

* Mencari di internet dan membaca halaman dokumentasi
* Meminta bantuan asisten riset terpisah untuk pertanyaan multi-sumber

**Aplikasi terhubung**

* GitHub, Linear, Notion, Stripe, Vercel, Supabase, Sentry, PostHog, Resend, Google Drive/Docs/Sheets, Discord, Telegram
* Server MCP yang kamu tambahkan dan setujui

**Kerja paralel**

* Sampai 6 pembantu dalam satu permintaan spawn, sampai 20 subagent kode dengan akses Projects

## 5. Cara mulai

1. Buka [freebuff.com](https://freebuff.com) dan unduh Desktop, atau buka versi web.
2. Atau lewat terminal: `npm install -g freebuff`, lalu `freebuff`.
3. Buka folder project, atau mulai dari folder kosong.
4. Tulis permintaan dengan bahasa biasa, misalnya: *"Jelaskan project ini fungsinya apa."*
5. Baca jawabannya, lalu beri langkah kecil berikutnya.

Beri instruksi seperti tiket — tiga pertanyaan: **apa** yang harus dilakukan, **di mana** ia boleh menyentuh, dan **bagaimana** kamu tahu berhasil (perintah, test atau URL).

Kebiasaan yang membantu:

* Mulai dengan mode **Plan** kalau project-nya belum kamu kenal: tidak ada yang bisa diubah saat kamu melihat-lihat.
* Satu langkah kecil sekali jalan lebih baik daripada "buat seluruh aplikasi".
* Simpan project di git supaya perubahan yang salah bisa dibatalkan.

Alur yang didokumentasikan dari ide kabur sampai perubahan yang bisa direview: `/interview` → `/plan` → implementasi → `/review`. Mengetik `@` menunjuk file, `/` membuka daftar perintah.

## 6. Benar-benar gratis?

Ya — iklan teks yang membayar modelnya, bukan langganan, dan tidak perlu kartu atau API key.

* Saldo dihitung dalam **jam** sejak 2026-10-15. **1 jam = 5 Freebucks.**
* Sebuah model memakan jam sesuai tarif di picker: sejam di model satu-jam memakai satu jam saldo, model tiga-jam memakai tiga, model eksperimen gratis tidak memakai saldo.
* Region yang didukung mendapat akses penuh. Region lain dan pengguna VPN/proxy mendapat **akses terbatas**: 5 jam sehari, atau 4 kalau pakai VPN atau proxy.
* Referral dan bounty menambah jam, masuk ke dompet, dan dipakai setelah jatah harian.

Katalog saat ini (sering berubah — cek picker):

| Model | Akses | Catatan |
| --- | --- | --- |
| DeepSeek V4.1 Flash | Gratis + berbayar | Coding dan tool use cepat, konteks 1M |
| DeepSeek V4.1 Flash Slow | Gratis + berbayar | Model sama, aliran lebih lambat; default di akses terbatas tanpa paket, dan di Chat |
| DeepSeek V4.1 Flash Fast | Gratis + berbayar | Varian lebih cepat di region akses terbatas |
| Solar Mini 4 | Gratis + berbayar | Upstage, ringkas, konteks 500K, hanya teks |
| Solar Pro 4 | Gratis + berbayar | Upstage, lebih besar, konteks 500K, hanya teks |
| Muse Spark 1.3 | Berbayar | Model agentic coding Meta, konteks 1M |
| Muse Ember | Berbayar | Model coding cepat Meta, konteks 375K |
| Claude Haiku 5.5 | Berbayar | Model cepat Anthropic, konteks 100K |
| GPT-6.1 Terra | Berbayar | OpenAI, dua sesi sehari, konteks 1M, gambar |
| Beam 1.0 · Glyph Cluster · Nemotron 3.5 Lightning | Eksperimen gratis | Tingkat akses terbatas |

Gemini 3.1 Flash Lite mengerjakan tugas khusus seperti mencari file, bukan tampil di picker utama. Sudah ada model yang pensiun: GLM 5.3 Flash, MiMo 2.6 Pro, GPT-6.1 Sol, Gemini 4 Argon, Gemini 3.8 Flash.

Desktop juga bisa menjalankan agent Claude Code dan Codex yang terpasang lokal dengan akun provider-mu sendiri; itu terpisah dari katalog Freebuff.

**Soal data:** sebuah model hanya boleh dipakai untuk pelatihan kalau pemberitahuannya bilang begitu. Terpisah dari itu, Freebuff bisa memakai data pemakaianmu untuk melatih model yang memilih dan mengukur iklan; file project dan repository yang terhubung tidak diberikan ke penyedia iklan.

## 7. Batasan

* Permintaan kabur menghasilkan hasil kabur — jelaskan "selesai" itu seperti apa.
* Ia tidak akan mengetik password-mu atau login untukmu.
* Di Desktop tidak ada sandbox OS: perintah berjalan dengan hak user-mu dan bisa keluar dari folder yang dibuka. Hak administrator tidak pernah diberikan diam-diam.
* Project yang belum dikenal bisa membawa setting yang bisa dieksekusi; CLI bertanya sebelum memercayai konfigurasi agent atau MCP tingkat project, dan kepercayaan itu terikat ke sebuah direktori.
* Ia tidak bisa menjamin kode tanpa cela; build hijau adalah bukti tentang build itu, bukan tentang segalanya.
* Jawaban tergantung model yang dipakai sesi itu.
* Jam gratis dibatasi per hari; pemakaian berat akan kena jatah.
* Plan dan Build terpisah rapi di Desktop; CLI berbeda, jadi cek versi yang kamu install.
* Chat Cloud menyimpan salinan file sendiri — menggabungkannya tugasmu, lewat git.
* Konteks terbatas: chat panjang diringkas menjadi ringkasan, jadi ulangi syarat penting.

## 8. Pertanyaan umum

**Apakah saya harus bisa programming?**
Tidak, tapi sangat membantu. Kamu perlu menjelaskan keinginanmu dengan jelas dan memeriksa hasilnya.

**Apakah benar-benar gratis?**
Iklan yang membayar modelnya. Tanpa kartu dan tanpa API key; paket berbayar menambah jam.

**Apakah bisa merusak project saya?**
Ia bisa salah. Pakai mode Plan dulu untuk perubahan besar dan simpan project di git.

**Kode saya pergi ke mana?**
Di Desktop tetap di folder yang kamu buka. Di Cloud berjalan di workspace awan untuk project itu.

**Bisa pilih model sendiri?**
Bisa — picker menunjukkan tiap model dan berapa jam biaya sejam di model itu.

**Apa itu "Freebucks"?**
Satuan kredit. Saldo ditampilkan dalam jam; 1 jam = 5 Freebucks.

**Apakah kode saya dipakai untuk pelatihan?**
Hanya kalau model atau fiturnya menyatakan data boleh dipakai untuk pelatihan. Cek pemberitahuan per model.

**Apa itu base3?**
Nama siklus agent utama Freebuff: satu agent menyelidiki, mengubah dan memverifikasi dengan tool-nya sendiri.

## 9. Glosarium

**Agent** — AI yang mengerjakan tugas, bukan cuma menjawab. Di sini namanya Buffy.
**Prompt** — pesan yang kamu tulis untuk meminta sesuatu.
**Repo (repository)** — folder project yang dilacak git, jadi perubahan bisa diperiksa atau dibatalkan.
**Terminal** — jendela teks tempat perintah diketik. Freebuff bisa memakainya untukmu.
**Build** — mengubah kode sumber jadi sesuatu yang bisa jalan, lalu memeriksanya.
**Sandbox / workspace** — tempat terpisah untuk menjalankan project. Cloud punya; Desktop tidak mengisolasi OS-mu.
**Mode** — seberapa besar kekuatan agent: Plan (hanya baca) atau Build (bisa mengubah file).
**Subagent** — agent pembantu dengan satu tugas sempit, hasilnya kembali ke agent utama.
**AGENTS.md** — file tempat project menyatakan aturan dan perintah verifikasinya sendiri.
**Link referral** — link yang memberi kredit ke orang yang membagikannya saat pengguna baru mendaftar.

## 10. Sumber

* [freebuff.com](https://freebuff.com) — produk, daftar platform, model dan toko
* [README di GitHub](https://github.com/CodebuffAI/freebuff) — katalog, jam dan Freebucks, tingkat akses, pemberitahuan data, lisensi
* [docs.freebuff.page/working-with-the-agent](https://docs.freebuff.page/working-with-the-agent) — siklus, Plan dan Build, grup tool, batas pembantu
* [docs.freebuff.page/cli](https://docs.freebuff.page/cli/) — perintah install, syarat Node, lokasi config
* [Postingan peluncuran](https://freebuff.com/blog/freebuff-launch) — subagent, slash command, posisi produk
* [codebuff.com/docs](https://codebuff.com/docs) — framework dan orkestratornya, "Buffy"

Dicek pada 24 November 2026. Harga, nama model dan batas harian sering berubah, jadi catatan ini menjelaskan cara kerjanya, bukan menulis angka yang bulan depan sudah salah.

---

Proyek penggemar tidak resmi. Tidak berafiliasi dan tidak didukung Freebuff atau Codebuff. Link referral yang dipakai wiki: https://freebuff.com/?ref=ref-ee33d868-d2dc-4b5e-a4d8-8156352d2f60&via=settings_earn_link
