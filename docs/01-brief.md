# Brief

## Ringkasan

Bikin design system netral dan themeable, plus situs dokumentasi yang rapi dan enak dipakai.
MVP fokus ke desain: foundations dan 15 komponen inti, terdokumentasi lengkap, dengan Figma library yang sinkron.
Kode React menyusul setelah MVP.

## Kenapa

- Banyak designer paham komponen, tapi belum pernah lihat DS yang dibangun dan didokumentasikan dengan benar dari nol.
- Kebanyakan referensi DS publik itu milik perusahaan besar. Terlalu besar dan terlalu spesifik buat dicontoh.
- DS yang netral dan gampang di-rebrand punya pasar: tim kecil, freelancer, agency.

## Tujuan

1. **Referensi.** Situs yang bisa dipakai designer buat belajar cara bikin dan mendokumentasikan DS.
2. **Fondasi produk.** Token, Figma library, dan dokumentasi yang kualitasnya layak dijual nanti.
3. **Portofolio.** Bukti kemampuan design system dan component architecture.

## Audiens

| Audiens | Butuh apa | Prioritas |
|---|---|---|
| Designer yang belajar DS | Contoh struktur, alasan di balik keputusan, do and don't | Utama |
| Designer atau tim kecil yang mau pakai | Figma library siap pakai, cara rebrand | Utama |
| Calon pembeli (nanti) | Kualitas, kelengkapan, lisensi jelas | Nanti |
| Developer (nanti) | Paket React, props, contoh kode | Nanti |

## Scope MVP

**Masuk**
- Situs dokumentasi bahasa Inggris, struktur siap bilingual
- 7 halaman foundations: Color, Typography, Spacing, Radius, Elevation, Layout, Iconography
- 1 halaman Tokens dan 1 halaman Theming
- 15 halaman komponen dengan template yang sama
- Preview komponen interaktif di web (visual reference, belum package production)
- Figma library: variables dan 15 komponen
- Light dan dark mode
- Deploy ke Vercel

**Tidak masuk MVP**
- Paket React yang bisa di-install
- Konten bahasa Indonesia
- Patterns (form, empty state, dll)
- Halaman harga, lisensi, checkout
- Versioning multi-versi docs

## Arah visual

Netral, bersih, themeable. Kayak base yang siap dipakai brand apa pun.
Karakter muncul dari detail: tipografi rapi, spacing konsisten, state yang lengkap, motion halus.
Bukan dari warna yang mencolok.

## Constraint

- Deadline MVP: 1 bulan (target rilis Jumat, 6 November 2026)
- Tim: Ilham (design lead, reviewer, pengambil keputusan) dan Claude (build, draft konten, sync Figma)
- Ilham bukan developer. Semua yang teknis harus bisa di-review lewat browser dan Figma.
- Belum ada source DS. Style dibangun bareng selama project jalan.

## Definisi sukses MVP

- Semua halaman MVP terisi sesuai template, nggak ada placeholder
- Token sama persis di web dan Figma
- Kontras teks lolos WCAG 2.2 AA di light dan dark
- Ilham bisa pakai Figma library-nya buat bikin 1 layar contoh tanpa detach komponen
- Situs live dan bisa di-share
