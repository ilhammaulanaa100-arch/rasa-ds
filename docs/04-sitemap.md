# Sitemap (Information Architecture)

Label: **MVP** wajib di rilis pertama, **P1** kalau sempat, **Later** setelah MVP.
Semua route diawali `/en`. Versi Indonesia nanti di `/id` dengan struktur yang sama.

## Navigasi global

```
Header:   Logo · Get started · Foundations · Components · Resources · [Search ⌘K] · [Theme] · [EN/ID]
Footer:   Changelog · Roadmap · Feedback · Figma · GitHub (nanti) · Lisensi (nanti)
```

## Struktur halaman

```
/en
├── /                                   Home                                MVP
│
├── /get-started
│   ├── /introduction                   Apa itu Rasa DS, prinsip            MVP
│   ├── /principles                     4 prinsip desain + alasannya        MVP
│   ├── /for-designers                  Cara pakai Figma library            MVP
│   ├── /for-developers                 Placeholder "coming soon"           MVP (singkat)
│   ├── /theming                        Cara rebrand lewat token            MVP
│   ├── /theme-playground               Ganti brand, preview langsung       P1
│   ├── /lifecycle                      Arti status Draft/Beta/Stable       MVP
│   └── /changelog                      Riwayat rilis                       P1
│
├── /foundations
│   ├── /                               Overview + grid foundations         MVP
│   ├── /tokens                         Arsitektur token, penamaan          MVP
│   ├── /color                          Palette, semantic, kontras          MVP
│   ├── /typography                     Type scale, font, pairing           MVP
│   ├── /spacing                        Scale dan aturan pemakaian          MVP
│   ├── /radius                         Scale dan aturan                    MVP
│   ├── /elevation                      Shadow, layer, z-index              MVP
│   ├── /layout                         Grid, breakpoint, container         MVP
│   ├── /iconography                    Set ikon, ukuran, aturan            MVP
│   ├── /motion                         Durasi, easing                      Later
│   └── /accessibility                  Standar a11y yang kita pegang       P1
│
├── /components
│   ├── /                               Grid semua komponen + filter status MVP
│   └── /[component]                    15 komponen, tab di bawah           MVP
│       ├── ?tab=usage
│       ├── ?tab=specs
│       ├── ?tab=accessibility
│       ├── ?tab=code                   Later
│       └── ?tab=changelog
│
├── /patterns                                                               Later
│   ├── /forms
│   ├── /empty-states
│   └── /feedback-and-errors
│
├── /content                                                                Later
│   ├── /voice-and-tone
│   ├── /writing-for-ui
│   └── /word-list
│
└── /resources
    ├── /figma-library                  Link dan cara install               MVP
    ├── /icons                          Browser ikon + copy nama            P1
    ├── /glossary                       Istilah DS                          MVP
    └── /faq                                                                P1
```

## Halaman Home

1. Hero: nama, 1 kalimat value, 2 tombol (Get started, Browse components)
2. 4 kartu jalur: Foundations, Components, Theming, Figma library
3. Preview komponen hidup (beberapa komponen dalam satu komposisi kecil)
4. "Built to be rebranded": demo ganti warna brand (versi mini dari playground)
5. Yang baru: 3 entri terakhir changelog

## Halaman Components overview

- Grid kartu: thumbnail preview, nama, 1 kalimat deskripsi, status badge
- Filter: kategori (Actions, Inputs, Feedback, Display) dan status
- Dikelompokkan per kategori, bukan cuma alfabetis

## Halaman Foundation (template)

1. Header: judul, 1 kalimat deskripsi, link Figma
2. Overview: apa dan kenapa
3. Principles: 2 sampai 4 poin
4. Scale atau palette: visual + tabel token dengan tombol copy
5. Usage: aturan pakai, do and don't
6. Accessibility notes
7. Related foundations dan komponen

## Kenapa strukturnya begini

- **Get started dipisah dari Foundations.** Orang baru butuh pintu masuk, bukan langsung tabel warna.
- **Theming di Get started.** Ini fitur jualan utama, harus gampang ditemukan.
- **Tab pakai query (`?tab=`).** Satu URL per komponen, gampang di-share, tab tetap bisa di-link.
- **Patterns dan Content disiapkan tapi belum diisi.** Struktur nggak perlu dibongkar saat ditambah.
