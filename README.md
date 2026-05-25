# FastQuote Decal - Cloud Shared History

Website kalkulator decal dengan riwayat order yang bisa terhubung antar perangkat memakai Supabase.

## Isi file

- `index.html` = website utama, langsung bisa upload ke GitHub Pages
- `supabase-schema.sql` = struktur database Supabase

## Cara pakai

### 1. Buat project Supabase

Buka Supabase lalu buat project baru.

### 2. Buat tabel database

Masuk ke:

SQL Editor > New query

Copy isi file `supabase-schema.sql`, lalu klik Run.

### 3. Ambil API key

Masuk ke:

Project Settings > API

Ambil:
- Project URL
- anon public key

### 4. Tempel ke index.html

Buka `index.html`, cari:

```js
const SUPABASE_URL = "ISI_PROJECT_URL_SUPABASE_ANDA";
const SUPABASE_ANON_KEY = "ISI_ANON_PUBLIC_KEY_SUPABASE_ANDA";
```

Ganti sesuai data dari Supabase.

### 5. Upload ke GitHub

Upload file:
- index.html
- supabase-schema.sql
- README.md

Aktifkan GitHub Pages:

Settings > Pages > Deploy from branch > main > root

## Cara kerja

- Admin daftar/login pakai email.
- Saat admin menyimpan nota, data masuk ke Supabase.
- Semua admin yang login bisa melihat riwayat yang sama.
- HP, tablet, dan laptop akan menampilkan data yang sama karena sumber datanya database online.
- Kalau Supabase belum disetting, website tetap berjalan dengan mode lokal/browser.

## Supabase Auth

Agar daftar akun lebih mudah, di Supabase bisa matikan email confirmation:

Authentication > Providers > Email > Confirm email = Off

Kalau tetap On, admin harus cek email dulu sebelum bisa login.
