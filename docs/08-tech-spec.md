# Tech Spec

Ditulis supaya Ilham paham alurnya tanpa harus ngoding.

## Stack

| Bagian | Pilihan | Kenapa |
|---|---|---|
| Framework situs | **Astro** | Halaman statis yang cepat, cocok buat dokumentasi, bebas dikustom |
| Konten | **MDX** | Markdown biasa yang bisa diselipin komponen. Gampang diedit |
| Preview komponen | **React** (sebagai island di Astro) | Komponen preview nanti tinggal dimatangkan jadi paket React |
| Styling | **CSS variables dari token** | Themeable dari akar. Ganti variable, semua ikut |
| Token build | **Style Dictionary** | Ubah `tokens/*.json` jadi CSS variables dan JSON buat Figma |
| Search | **Pagefind** | Search statis, gratis, nggak butuh server |
| Code highlight | Shiki (bawaan Astro) | |
| Hosting | **Vercel** | Udah familiar, preview link otomatis per perubahan |
| Repo | **GitHub** | Riwayat perubahan, preview deploy |
| Figma sync | Figma connector (MCP) | Claude bikin dan update variables dan komponen di file Figma |

## Struktur repo

```
rasa-ds/
├── CLAUDE.md
├── README.md
├── ROADMAP.md
├── DECISIONS.md
├── docs/                      # Dokumen perencanaan (file-file ini)
├── tokens/
│   ├── primitives.json
│   ├── semantic.light.json
│   ├── semantic.dark.json
│   └── components/            # button.json, text-field.json, ...
├── src/
│   ├── components/
│   │   ├── docs/              # Komponen situs: Header, Sidebar, TokenTable, DoDont, Preview, ...
│   │   └── ui/                # Komponen DS: Button.tsx, TextField.tsx, ...
│   ├── layouts/
│   ├── pages/
│   └── styles/
│       └── tokens.css         # Hasil build, jangan diedit manual
├── content/
│   ├── en/
│   │   ├── get-started/
│   │   ├── foundations/
│   │   └── components/        # button.mdx, text-field.mdx, ...
│   └── id/                    # Kosong dulu, struktur sama dengan en/
├── public/
│   └── images/
└── build/
    └── figma/                 # JSON token untuk sync Figma
```

## Alur kerja harian

```
Ilham kasih arahan / feedback
        │
        ▼
Claude update tokens / konten / komponen
        │
        ▼
Push ke GitHub ──► Vercel bikin preview link
        │
        ▼
Ilham review di browser (dan Figma kalau perlu)
        │
        ├── Revisi ──► balik ke atas
        └── Approve ──► merge ke main ──► live
                          │
                          ▼
                Claude sync token/komponen ke Figma
```

## Komponen situs (internal)

Komponen ini dipakai di MDX supaya semua halaman konsisten:

| Komponen | Fungsi |
|---|---|
| `<ComponentHeader>` | Header komponen dari frontmatter |
| `<Preview>` | Area live preview + kontrol + toggle tema |
| `<TokenTable>` | Tabel token, nilainya dibaca langsung dari JSON |
| `<ColorPalette>` | Swatch palette + kontras + copy |
| `<TypeScale>` | Contoh type scale |
| `<DoDont>` | Blok Do, Don't, Caution |
| `<Anatomy>` | Gambar bernomor + legenda |
| `<KeyboardTable>` | Tabel keyboard di tab Accessibility |
| `<Related>` | Kartu komponen terkait |
| `<StatusBadge>` | Draft, Beta, Stable, Deprecated |

## Hal yang perlu Ilham siapkan

- Akun GitHub (untuk repo)
- Akun Vercel (udah ada)
- File Figma kosong untuk library (Claude yang isi)
- Akses: lihat `DECISIONS.md` bagian Open
