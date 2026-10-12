---
description: Mulai komponen baru sesuai template
argument-hint: <nama komponen, contoh "text field">
---

Komponen: $ARGUMENTS

1. Cek `docs/07-component-inventory.md`. Kalau komponen ini nggak ada di daftar MVP, berhenti dan tanya Ilham dulu (aturan scope di file itu).
2. Baca `docs/05-component-page-spec.md` dan `docs/06-foundations-and-tokens.md`.
3. Kalau udah ada komponen lain yang statusnya `beta` atau `stable`, pakai itu sebagai contoh struktur.
4. Bikin:
   - `tokens/components/<slug>.json` (semua nilai menunjuk ke token semantic)
   - `src/components/ui/<Name>.tsx`
   - `content/en/components/<slug>.mdx` dengan frontmatter lengkap dan semua section wajib
5. Isi konten ikut `docs/09-writing-guide.md`. Jangan pakai lorem ipsum. Kalau ada keputusan desain yang belum jelas, tulis usulan lo di section "Why we designed it this way" dan tandai untuk review.
6. Jalankan build dan pastikan lolos.
7. Update status di inventory jadi `draft`.
8. Tutup dengan ringkasan: apa yang dibikin, keputusan yang lo ambil, dan apa yang perlu Ilham review.
