# PRD: Situs Dokumentasi Rasa DS

Status: Draft v0.1 · Owner: Ilham · Update terakhir: 9 Okt 2026

## 1. Masalah

Designer yang mau bikin atau pakai DS butuh contoh yang lengkap tapi nggak raksasa.
Referensi publik yang ada cenderung terlalu besar (Material, Carbon) atau cuma UI kit tanpa alasan di balik keputusannya.

## 2. Tujuan produk

- Orang bisa nemu komponen, paham kapan dipakai, dan lihat spesifikasinya dalam kurang dari 1 menit.
- Setiap keputusan desain punya alasan yang ditulis, bukan cuma gambar.
- Rebrand cukup dengan ganti token, bukan bongkar komponen.

## 3. Persona

**Dina, designer yang lagi belajar DS.** Tau Figma, belum pernah bikin DS. Mau tau "kenapa begini", bukan cuma "begini".

**Raka, lead designer di agency kecil.** Butuh base DS yang bisa di-rebrand per klien dalam sehari.

**Developer (nanti).** Butuh props, kode contoh, dan token dalam bentuk CSS variables.

## 4. User stories

| ID | Sebagai | Saya mau | Supaya | Prioritas |
|---|---|---|---|---|
| US-01 | Designer | Cari komponen lewat search | Nggak perlu scroll sidebar | P0 |
| US-02 | Designer | Lihat semua variant dan state dalam satu halaman | Paham cakupannya | P0 |
| US-03 | Designer | Tau kapan **nggak** pakai komponen ini, dan alternatifnya | Nggak salah pilih | P0 |
| US-04 | Designer | Lihat token apa yang dipakai tiap bagian komponen | Bisa replikasi dan rebrand | P0 |
| US-05 | Designer | Copy nama token atau nilai dengan sekali klik | Kerja lebih cepat | P0 |
| US-06 | Designer | Buka komponen yang sama di Figma | Langsung pakai | P0 |
| US-07 | Semua | Pindah light dan dark mode | Cek dua tema | P0 |
| US-08 | Semua | Tau status komponen (draft, beta, stable) | Tau mana yang aman dipakai | P0 |
| US-09 | Designer | Coba ganti warna brand dan lihat hasilnya langsung | Yakin DS ini themeable | P1 |
| US-10 | Semua | Kasih feedback dari halaman mana pun | Bantu perbaikan | P1 |
| US-11 | Pembaca ID | Baca dalam bahasa Indonesia | Lebih nyaman | P2 |
| US-12 | Developer | Copy kode React dan lihat props | Implementasi | P2 |

## 5. Fitur

### P0 (wajib ada di MVP)

| Fitur | Detail |
|---|---|
| Navigasi global | Header: Get started, Foundations, Components, Resources. Sidebar per section. Breadcrumb di mobile. |
| On this page | Daftar isi di kanan, aktif mengikuti scroll |
| Search | Cmd/Ctrl + K. Index semua halaman, heading, dan nama token |
| Light dan dark mode | Ikut sistem, bisa di-override, pilihan diingat |
| Template halaman komponen | Sesuai `05-component-page-spec.md` |
| Live preview | Komponen asli (bukan gambar) dengan kontrol variant, size, state |
| Tabel token | Nama token, nilai light, nilai dark, tombol copy |
| Do and don't | Blok visual dengan label jelas, wajib ada keterangan |
| Status badge | Draft, Beta, Stable, Deprecated. Muncul di header komponen dan di grid overview |
| Link Figma | Per komponen dan per halaman foundation |
| Prev dan next | Di bawah tiap halaman |
| Responsif | Nyaman dari 360px sampai layar lebar |
| i18n-ready | Route `/en/...` dari awal. `/id/...` tinggal diisi |

### P1 (masuk MVP kalau waktu cukup)

| Fitur | Detail |
|---|---|
| Theme playground | Ganti warna brand, radius, dan font. Preview komponen berubah langsung. Export token |
| Copy snippet | HTML dan CSS sederhana untuk tiap contoh |
| Feedback | Tombol "Was this helpful?" plus link form |
| Changelog situs | Satu halaman, update tiap rilis |
| Last updated | Tanggal di tiap halaman |

### P2 (setelah MVP)

- Konten bahasa Indonesia penuh dengan language switcher
- Paket React, props table, dan tab Code
- Patterns: Forms, Empty states, Feedback and errors
- Content guidelines: Voice and tone, Word list
- Versioning dokumentasi
- Halaman produk: Pricing, License, Showcase

## 6. Kebutuhan non-fungsional

- **Performa:** Lighthouse Performance dan Accessibility minimal 90 di halaman utama dan halaman komponen.
- **Aksesibilitas situs:** bisa dinavigasi keyboard penuh, focus ring kelihatan, skip link, heading berurutan.
- **Kontras:** semua pasangan teks dan background di token semantic lolos WCAG 2.2 AA.
- **Konsistensi:** nggak ada nilai hardcode di komponen. Semua lewat token.
- **Maintainability:** tambah komponen baru cukup bikin 1 file MDX plus 1 file preview.

## 7. Metrik

MVP (internal):
- 7 foundations + Tokens + Theming + 15 komponen terisi 100% sesuai template
- 0 token beda antara web dan Figma
- Ilham bisa bikin 1 layar contoh di Figma pakai library tanpa detach

Setelah rilis (indikatif):
- Jumlah pengunjung dan halaman paling sering dibuka
- Feedback "helpful" per halaman

## 8. Di luar scope

Checkout, akun pengguna, CMS, blog, multi-versi docs, paket npm.

## 9. Risiko

| Risiko | Dampak | Mitigasi |
|---|---|---|
| Style berubah terus karena belum ada source | Molor | Freeze foundations di akhir minggu 1. Perubahan setelahnya masuk backlog |
| Scope komponen nambah di tengah jalan | Molor | Komponen baru masuk batch setelah MVP, kecuali ada yang dikeluarkan |
| Web dan Figma nggak sinkron | DS nggak bisa dipercaya | Satu arah: token dulu, lalu generate ke dua-duanya |
| Konten dokumentasi tipis | Cuma jadi UI kit | Template wajib dan checklist per halaman |
| Review numpuk di akhir | Kualitas turun | Review tiap 2 sampai 3 hari, bukan di akhir minggu |

## 10. Pertanyaan terbuka

Lihat bagian Open di `DECISIONS.md`.
