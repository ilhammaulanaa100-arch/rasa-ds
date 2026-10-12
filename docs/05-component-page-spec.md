# Spec Halaman Komponen

Setiap komponen wajib ikut template ini. Section bertanda (opsional) boleh dihilangkan kalau memang nggak relevan, tapi tulis alasannya di catatan PR.

## Struktur

```
┌─────────────────────────────────────────────────────────┐
│ Header                                                  │
│  Nama · Status · Versi · Updated                        │
│  1 kalimat deskripsi                                    │
│  [Figma] [Code: coming soon]                            │
├─────────────────────────────────────────────────────────┤
│ Tabs: Usage | Specs | Accessibility | Changelog         │
├──────────────────────────────────────────┬──────────────┤
│ Konten tab                               │ On this page │
└──────────────────────────────────────────┴──────────────┘
  Feedback · Prev / Next
```

## Header

| Elemen | Isi | Contoh |
|---|---|---|
| Nama | Sentence case | Text field |
| Status | Draft, Beta, Stable, Deprecated | Beta |
| Versi | Semver komponen | 0.1.0 |
| Updated | Tanggal update terakhir | 20 Okt 2026 |
| Deskripsi | 1 kalimat, mulai dengan kata kerja, maks 20 kata | Lets people enter and edit a single line of text. |
| Link | Figma (wajib), Code (nanti) | |

## Tab 1: Usage

Urutan wajib:

1. **Live preview**
   Komponen asli dengan kontrol: variant, size, state, dan toggle konten (icon, label, dll).
   Ada tombol copy snippet (P1) dan toggle background light/dark.

2. **When to use**
   2 sampai 4 poin.

3. **When not to use**
   2 sampai 4 poin, masing-masing dengan alternatif. Contoh: "To navigate to another page. Use **Link** instead."

4. **Anatomy**
   Gambar komponen dengan nomor, plus daftar bagian. Tandai mana yang opsional.

5. **Variants**
   Tiap variant: preview, kapan dipakai, 1 kalimat alasan.

6. **Sizes**
   Tabel ukuran dan konteks pakai. (opsional)

7. **States**
   Grid semua state: default, hover, active, focus, disabled, plus state khusus (loading, error, read-only, dll).

8. **Behavior**
   Interaksi, overflow teks, responsif, loading, truncation.

9. **Best practices**
   Blok Do, Don't, Caution. Tiap blok wajib ada visual dan 1 kalimat keterangan.

10. **Content**
    Aturan teks untuk komponen ini: panjang, kapitalisasi, nada, contoh benar dan salah.

11. **Related**
    2 sampai 4 komponen terkait dengan 1 kalimat perbedaannya.

12. **Why we designed it this way** (pembeda Rasa DS)
    2 sampai 4 keputusan desain penting dan alasannya. Contoh: "Minimum width is 2.25x the height so short labels still read as buttons."

## Tab 2: Specs

1. **Dimensions**
   Redline: tinggi, padding, gap, ukuran ikon, per size.

2. **Token map**
   Tabel wajib:

   | Part | Property | Token | Light | Dark |
   |---|---|---|---|---|
   | Container | background | `button.primary.bg` | `#…` | `#…` |
   | Container | background (hover) | `button.primary.bg-hover` | | |
   | Label | color | `button.primary.fg` | | |

   Setiap nama token bisa di-copy. Nilai otomatis dari `tokens.json`, bukan ditulis manual.

3. **Responsive** (opsional)
   Perubahan di breakpoint tertentu.

## Tab 3: Accessibility

1. **Keyboard**: tabel tombol dan aksinya
2. **Screen reader**: role, nama yang dibacakan, atribut ARIA yang dibutuhkan
3. **Focus**: tampilan focus ring dan urutan fokus
4. **Color and contrast**: pasangan warna yang dicek dan rasionya
5. **Touch target**: ukuran area sentuh minimum
6. **Internationalization**: teks lebih panjang (ID biasanya lebih panjang dari EN), wrap, truncation

## Tab 4: Code (setelah MVP)

Install, import, contoh, props table, catatan implementasi. Selama MVP, tab ini disembunyikan.

## Tab 5: Changelog

| Versi | Tanggal | Perubahan |
|---|---|---|

## Format file

Satu komponen = satu file MDX di `content/en/components/<slug>.mdx`.

Frontmatter:

```yaml
---
title: Text field
slug: text-field
description: Lets people enter and edit a single line of text.
category: inputs        # actions | inputs | feedback | display
status: beta            # draft | beta | stable | deprecated
version: 0.1.0
updated: 2026-10-20
figma: https://www.figma.com/design/...
related: [text-area, select]
tags: [form, input]
---
```

## Checklist selesai (Definition of Done)

- [ ] Semua section wajib terisi, nggak ada lorem ipsum
- [ ] Live preview menampilkan semua variant dan state
- [ ] Minimal 2 pasang Do dan Don't
- [ ] Token map lengkap, cocok dengan Figma
- [ ] Kontras dicek di light dan dark
- [ ] Keyboard dan screen reader terisi
- [ ] Komponen ada di Figma library dengan nama dan variant yang sama
- [ ] Lolos review Ilham

## Status lifecycle

| Status | Artinya | Syarat naik |
|---|---|---|
| Draft | Lagi dikerjakan, bisa berubah total | Template terisi, preview jalan |
| Beta | Bisa dipakai, detail masih mungkin berubah | Lolos review, ada di Figma |
| Stable | Siap pakai, perubahan besar butuh versi major | Dipakai di minimal 1 layar contoh, nggak ada isu terbuka |
| Deprecated | Jangan dipakai lagi | Ada pengganti dan catatan migrasi |

Target MVP: semua 15 komponen minimal **Beta**.
