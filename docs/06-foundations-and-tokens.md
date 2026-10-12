# Foundations dan Token

Semua angka di sini **usulan awal**. Ilham review di halaman Style Guide, lalu kita freeze di akhir minggu 1.

## Prinsip

1. **Token satu-satunya sumber nilai.** Komponen nggak boleh pakai hex, px, atau angka langsung.
2. **Komponen pakai token semantic, bukan primitive.** Biar rebrand cukup ganti mapping.
3. **Nama menjelaskan fungsi, bukan tampilan.** `color.text.subtle`, bukan `color.gray-600`.
4. **Dark mode bukan tema terpisah.** Dia mode dari token semantic yang sama.

## Tiga lapis token

```
Primitive              Semantic                     Component
(nilai mentah)         (makna)                      (khusus komponen)

color.blue.600   ──►   color.action.primary.bg ──►  button.primary.bg
color.gray.900   ──►   color.text.default      ──►  textfield.fg
space.4          ──►   space.inset.md          ──►  button.md.padding-x
```

| Lapis | Isi | Siapa yang pakai | Berubah saat rebrand? |
|---|---|---|---|
| Primitive | Palette lengkap, scale angka | Cuma token semantic | Brand ramp ya, sisanya jarang |
| Semantic | Makna: text, bg, border, action, status | Komponen dan layout | Mapping-nya bisa |
| Component | Override khusus komponen | Komponen itu sendiri | Jarang |

Aturan: component token **selalu** menunjuk ke semantic. Semantic **selalu** menunjuk ke primitive.

## Penamaan

```
{category}.{concept}.{variant}.{state}

color.text.default
color.text.subtle
color.action.primary.bg
color.action.primary.bg-hover
color.status.danger.fg
space.inset.md
radius.control
```

- Huruf kecil semua, pisah pakai titik. Kata majemuk pakai tanda hubung.
- State di ujung: `-hover`, `-active`, `-disabled`.
- Di CSS jadi `--rasa-color-text-default`. Di Figma jadi `color/text/default`.

## Format file

Pakai format **W3C Design Tokens (DTCG)** supaya bisa dibaca banyak tools.

```json
{
  "color": {
    "blue": {
      "600": { "$type": "color", "$value": "#2563EB" }
    },
    "action": {
      "primary": {
        "bg": { "$type": "color", "$value": "{color.blue.600}" }
      }
    }
  }
}
```

Dark mode disimpan di file terpisah yang override lapis semantic: `tokens/semantic.light.json` dan `tokens/semantic.dark.json`.

## Figma variables

| Collection | Modes | Isi |
|---|---|---|
| Primitives | 1 (Default) | Semua palette dan scale |
| Semantic | Light, Dark | Alias ke Primitives |
| Component | 1 | Alias ke Semantic (cuma kalau perlu) |
| Typography | 1 | Font family, size, line height, weight sebagai variables, plus text styles |

Primitives di-hide dari publishing, supaya designer langsung pakai Semantic.

## Usulan awal foundations

### Color

- **Neutral:** 1 ramp abu-abu, 11 step (50 sampai 950). Sedikit cool supaya netral tapi nggak mati.
- **Brand:** 1 ramp, 11 step. Default biru netral, gampang diganti.
- **Status:** danger (merah), warning (kuning/amber), success (hijau), info (biru).
- **Semantic groups:** `bg`, `surface`, `text`, `icon`, `border`, `action`, `status`, `focus`.
- Syarat: setiap pasangan `text` di atas `bg` atau `surface` lolos AA (4.5:1 untuk teks normal, 3:1 untuk teks besar dan komponen UI).

### Typography

- 1 font sans-serif dengan lisensi bebas komersial (pilihan final di DECISIONS).
- Type scale usulan (px): 12, 14, 16, 18, 20, 24, 30, 36, 48.
- Semantic text styles: `display`, `heading.lg/md/sm`, `body.lg/md/sm`, `label.md/sm`, `caption`, `code`.
- Line height: 1.5 untuk body, 1.2 sampai 1.3 untuk heading.

### Spacing

- Base 4px.
- Scale: 0, 2, 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80.
- Semantic: `space.inset.*` (padding dalam), `space.stack.*` (jarak vertikal), `space.inline.*` (jarak horizontal).

### Radius

- Scale: 0, 2, 4, 6, 8, 12, 16, full.
- Semantic: `radius.control` (button, input), `radius.container` (card, modal), `radius.pill`.
- Ini salah satu tombol rebrand paling kerasa. Ganti `radius.control` dan seluruh DS berubah karakter.

### Elevation

- 5 level: 0 (flat), 1 (raised), 2 (overlay: dropdown, tooltip), 3 (modal), 4 (toast).
- Tiap level = shadow + z-index yang berpasangan.
- Dark mode: shadow dikurangi, beda level ditunjukkan lewat warna surface yang lebih terang.

### Layout

- Breakpoints: `sm` 640, `md` 768, `lg` 1024, `xl` 1280, `2xl` 1536.
- Grid: 4 kolom (mobile), 8 (tablet), 12 (desktop).
- Container max width dan gutter per breakpoint.

### Iconography

- Base set: library open source dengan lisensi yang mengizinkan pemakaian komersial (usulan: Lucide, cek lisensi final).
- Ukuran: 16, 20, 24. Stroke konsisten.
- Ikon selalu ikut warna teks lewat `currentColor`.

## Alur kerja token

```
1. Claude edit tokens/*.json
2. Build otomatis jadi CSS variables (situs) dan JSON untuk Figma
3. Ilham review di halaman Style Guide (web)
4. Approve → Claude sync ke Figma variables lewat Figma connector
5. Perubahan dari Figma? Ilham kasih tau, Claude update tokens/*.json dulu, baru sync ulang
```

Satu arah. Figma nggak pernah jadi sumber, supaya nggak ada dua versi kebenaran.
