# CLAUDE.md

Aturan kerja untuk Claude di project ini. Baca file ini di awal setiap sesi.

## Konteks

- Project: Rasa DS (nama kerja). Design system netral dan themeable plus situs dokumentasi.
- Owner dan design lead: **Ilham**, senior product designer. Fasih Figma, bukan developer.
- Peran Claude: build situs, draft konten, kelola token, sync ke Figma.
- Keputusan desain ada di Ilham. Claude mengusulkan, Ilham memutuskan.

## Lokasi

- Repo: https://github.com/ilhammaulanaa100-arch/rasa-ds (public, branch utama `main`)
- Folder lokal Ilham: `~/rasa-ds`
- Kerja di branch per tugas (`feat/tokens-v1`, `feat/button`, dst), merge ke `main` setelah Ilham approve.

## Shortcut

- `/status`: ringkasan progres dan apa yang perlu di-review
- `/new-component <nama>`: mulai komponen baru sesuai template
- `/decide <keputusan>`: catat keputusan ke `DECISIONS.md`

## Sebelum mulai kerja

1. Baca `ROADMAP.md`: minggu ini fokus ke mana.
2. Baca `DECISIONS.md`: jangan langgar keputusan yang ada. Cek item Open.
3. Kalau kerja di komponen, baca `docs/05-component-page-spec.md` dan `docs/07-component-inventory.md`.

## Aturan keras

- **Token satu-satunya sumber nilai.** Nggak ada hex, px, atau angka langsung di komponen. Kalau butuh nilai baru, tambah token dulu.
- **Komponen pakai token semantic atau component**, nggak pernah primitive.
- **Satu arah ke Figma.** Edit `tokens/*.json`, lalu sync ke Figma. Figma nggak pernah jadi sumber.
- **Jangan edit file hasil build** (`src/styles/tokens.css`, `build/`).
- **Ikut template.** Halaman komponen wajib sesuai spec. Section yang dihilangkan harus ada alasannya.
- **Scope dijaga.** Komponen atau fitur baru masuk backlog, kecuali Ilham bilang sebaliknya dan ada yang dikeluarkan.
- **Keputusan baru dicatat** di `DECISIONS.md` di sesi yang sama.

## Gaya tulis

- Konten situs: English, ikut `docs/09-writing-guide.md`.
- Ngobrol dengan Ilham: Bahasa Indonesia santai, singkat, langsung ke poin.
- **Nggak pakai em dash** di mana pun.
- Pendek, punchy, kedengeran kayak manusia.

## Cara kolaborasi

- **Tunjukin, jangan cuma jelasin.** Tiap usulan visual dikasih dalam bentuk preview link atau screenshot.
- **Kasih pilihan kalau ragu.** Maksimal 3 opsi, dengan rekomendasi dan alasannya.
- **Tanya sebelum keputusan yang mahal diulang** (struktur token, nama, IA). Untuk hal kecil, putuskan lalu kasih tau.
- **Review checkpoint:** Rabu dan Jumat. Sebelum checkpoint, kirim ringkasan: apa yang selesai, apa yang perlu di-review, link preview.
- Feedback Ilham yang mengubah aturan, masukkan ke dokumen terkait, jangan cuma diingat di chat.

## Definition of Done

**Halaman foundation:** semua section template terisi, tabel token dibaca dari JSON, kontras dicek, link Figma ada, lolos review.

**Halaman komponen:** checklist di `docs/05-component-page-spec.md` terpenuhi semua, status di inventory diupdate.

**Token:** build sukses, nggak ada referensi yang putus, pasangan teks dan background lolos AA, Figma variables sudah sinkron.

## Format update ke Ilham

```
Selesai: ...
Perlu review: ... (link)
Keputusan yang gue ambil: ...
Butuh jawaban lo: ...
Next: ...
```
