# Component Inventory

Status: `todo` · `draft` · `beta` · `stable`. Update file ini tiap kali status berubah.

## MVP: 15 komponen

| # | Komponen | Kategori | Minggu | Variants | States khusus | Status |
|---|---|---|---|---|---|---|
| 1 | Button | Actions | 2 | Primary, Secondary, Tertiary, Danger · sm, md, lg · icon leading/trailing, icon-only | Loading | todo |
| 2 | Link | Actions | 2 | Inline, Standalone · external | Visited | todo |
| 3 | Icon | Display | 2 | 16, 20, 24 | | todo |
| 4 | Text field | Inputs | 3 | sm, md, lg · prefix/suffix icon · helper, counter | Error, Read-only | todo |
| 5 | Text area | Inputs | 3 | Auto-resize, fixed · counter | Error, Read-only | todo |
| 6 | Select | Inputs | 3 | Single select · sm, md, lg | Error, Open | todo |
| 7 | Checkbox | Inputs | 3 | Single, Group | Indeterminate, Error | todo |
| 8 | Radio | Inputs | 3 | Group, horizontal/vertical | Error | todo |
| 9 | Switch | Inputs | 3 | sm, md · label kiri/kanan | | todo |
| 10 | Badge | Display | 2 | Neutral, Info, Success, Warning, Danger · Subtle, Solid · Dot, Count | | todo |
| 11 | Chip | Inputs | 3 | Filter (selectable), Input (removable) · sm, md | Selected | todo |
| 12 | Avatar | Display | 4 | Image, Initials, Icon · xs sampai xl · circle, square | Status dot | todo |
| 13 | Tooltip | Feedback | 4 | Top, Right, Bottom, Left | | todo |
| 14 | Alert | Feedback | 4 | Info, Success, Warning, Danger · dismissible · with action | | todo |
| 15 | Spinner | Feedback | 2 | sm, md, lg · Default, Inverse | | todo |

**Kenapa 15 ini:** inilah blok yang muncul di hampir semua layar produk. Dengan 15 ini, satu form lengkap, satu settings page, dan satu list sederhana udah bisa dibangun. Itu cukup buat buktiin DS-nya jalan.

**Kenapa Button duluan di awal minggu 2:** dia jadi contoh lengkap (vertical slice). Template, token map, Figma sync, semua diuji di sini dulu. Setelah Button lolos review, baru Link, Icon, Badge, dan Spinner menyusul di minggu yang sama karena strukturnya sederhana.

## Backlog (setelah MVP, urut prioritas)

| Komponen | Kategori | Catatan |
|---|---|---|
| Tabs | Navigation | Butuh pola keyboard yang rumit |
| Modal | Feedback | Butuh focus trap |
| Toast | Feedback | Butuh sistem antrian |
| Card | Display | Lebih mirip pattern, perlu dipikir |
| Divider | Display | Kecil, bisa masuk kapan aja |
| Menu / Dropdown menu | Actions | Dasar buat Select lanjutan |
| Table | Display | Besar, sendiri satu batch |
| Pagination | Navigation | |
| Breadcrumb | Navigation | |
| Progress bar | Feedback | |
| Skeleton | Feedback | |
| Date picker | Inputs | Besar, belakangan |

## Aturan nambah komponen di tengah jalan

1. Tulis usulannya di sini dengan alasan.
2. Kalau mau masuk MVP, satu komponen MVP lain harus keluar. Deadline nggak geser.
3. Kalau nggak, masuk Backlog.
