# Benchmark

Tujuannya bukan niru satu DS, tapi ambil yang terbaik dari masing-masing dan susun jadi standar kita.

## DS yang dilihat

| DS | Pemilik | Kenapa relevan |
|---|---|---|
| BLUE (blue3) | Blibli | Referensi awal. Lokal, rapi, struktur jelas |
| Carbon | IBM | Halaman komponen paling lengkap, tab Accessibility terpisah |
| Atlassian Design System | Atlassian | Usage guideline tajam, content guideline per komponen |
| Primer | GitHub | Lifecycle komponen yang jelas |
| Spectrum | Adobe | Anatomy, options, behaviors, dan i18n yang sistematis |
| Material 3 | Google | Tab Specs dengan token per bagian komponen |
| Polaris | Shopify | Lifecycle, content guideline kuat |
| Untitled UI | Komersial | Contoh DS yang dijual: Figma variables, dark mode, lisensi bertingkat |
| shadcn/ui | Open source | Model distribusi kode yang disukai developer modern |

## Pola halaman komponen

| | BLUE | Carbon | Atlassian | Spectrum | Material 3 |
|---|---|---|---|---|---|
| Tab | Implementation, Usage, Changelog | Usage, Style, Code, Accessibility | Examples, Code, Usage, Changelog | Satu halaman panjang | Overview, Specs, Guidelines, Accessibility |
| Live demo | Ya | Ya | Ya | Ya | Ya |
| When **not** to use | Tidak eksplisit | Ya | Ya, lewat aturan | Ya | Ya |
| Anatomy | Ya | Ya | Ya ("Parts") | Ya | Ya |
| Behavior dan state | Ya | Ya | Sebagian | Ya | Ya |
| Content guideline per komponen | Ya | Ya | Ya, sangat detail | Ya | Sebagian |
| Token per bagian | Tidak di halaman publik | Di tab Style | Tidak | Lewat design data | Ya, di Specs |
| Accessibility | Atribut dan keyboard | Tab sendiri | Section | Section | Tab sendiri |
| Related components | Prev/next | Ya | Ya | Ya | Ya |
| Status dan versi | Versi, coverage, SSR | Status | Release phase | Status | Tidak menonjol |

## Yang kita ambil

| Dari | Ambil | Alasan |
|---|---|---|
| BLUE | Header komponen dengan badge, grid komponen dengan deskripsi 1 kalimat, label New, content guideline sebagai bagian DS | Ringkas dan scannable |
| Carbon | **When not to use**, tab Accessibility terpisah, section Related | Bantu orang nggak salah pilih |
| Atlassian | Aturan usage ditulis sebagai kalimat perintah ("Use one primary call to action") | Lebih gampang diingat dari paragraf panjang |
| Material 3 | **Tab Specs**: tabel token per bagian komponen, ukuran, spacing | Ini yang paling dibutuhkan buat rebrand |
| Spectrum | Urutan Anatomy, Options, Behaviors. Catatan i18n | Sistematis. Relevan buat EN dan ID |
| Primer, Polaris | **Lifecycle**: Draft, Beta, Stable, Deprecated dengan kriteria jelas | Jujur soal kematangan, penting kalau mau dijual |
| Untitled UI | Figma variables dengan mode light dan dark, satu library rapi | Standar minimum DS komersial |
| shadcn/ui | Kode yang gampang di-copy (nanti, fase React) | Pola distribusi yang disukai developer |

## Yang sengaja **nggak** kita ambil

- **Satu halaman sangat panjang tanpa tab** (Spectrum). Susah dinavigasi buat pembaca baru.
- **Konten yang dikunci VPN** (BLUE). Situs kita sepenuhnya publik.
- **Variant sebanyak mungkin** (UI kit komersial). Kita pilih sedikit variant yang punya alasan jelas.

## Pembeda Rasa DS

1. **"Why" di setiap keputusan.** Tiap halaman foundation dan komponen punya catatan alasan singkat. Ini yang bikin dia jadi referensi belajar, bukan cuma katalog.
2. **Theming jadi fitur utama.** Ada halaman Theming dan playground buat ganti brand.
3. **Siap bilingual.** Dibangun dengan catatan i18n, termasuk teks ID yang biasanya lebih panjang dari EN.
4. **Ukuran pas.** Cukup lengkap buat produk nyata, cukup kecil buat dipahami.

## Sumber

- BLUE: https://blue.blibli.com/blue3/ (dicek langsung, termasuk halaman Button dan Foundations)
- Carbon Button: https://carbondesignsystem.com/components/button/usage/ (dicek)
- Atlassian Button: https://atlassian.design/components/button/usage (dicek)
- Primer component lifecycle: https://primer.style/guides/component-lifecycle (dicek)
- Polaris component lifecycle: https://polaris.shopify.com/getting-started/components-lifecycle
- Spectrum: https://spectrum.adobe.com/page/home
- Material 3: https://m3.material.io
- Untitled UI: https://untitledui.com (dicek)
- shadcn/ui: https://ui.shadcn.com

Catatan: Spectrum, Material 3, Polaris, dan shadcn/ui diringkas dari pengetahuan umum soal struktur situsnya, belum dibuka ulang di sesi ini. Cek lagi kalau ada detail yang mau dijadikan acuan pasti.
