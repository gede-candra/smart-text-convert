# Smart Text Convert

Smart Text Convert adalah web utility ringan untuk membantu konversi teks menjadi format yang siap pakai di terminal dan workflow teks sehari-hari.

Tool ini dibuat sebagai **single-page app** berbasis HTML/CSS/JavaScript tanpa dependency tambahan.

Untuk dokumentasi English (default repo), lihat [README.md](README.md).

## Fitur Utama

### 1. Find: Kecualikan Daftar
Menghasilkan command `find` untuk mencari file yang **tidak** termasuk nama pada daftar input.

Output yang tersedia:
- `-print` (preview file)
- `-delete` (hapus file)
- `| wc -l` (hitung jumlah file)

Tambahan:
- Opsi command berbasis `keep.txt` untuk daftar panjang.

### 2. Find: Pilih Saja
Kebalikan dari fitur sebelumnya: menghasilkan command `find` untuk memilih **hanya** file yang ada di daftar input.

Output yang tersedia:
- `-print`
- `-delete`
- `| wc -l`

Tambahan:
- Opsi command berbasis `pick.txt` untuk daftar panjang.

### 3. Formatter List
Mengubah input multiline menjadi format list sesuai kebutuhan.

Pilihan format:
- separator `spasi`
- separator `,`
- pembungkus `""`
- pembungkus `''`

Contoh hasil:
- `a, b, c, d`
- `"a", "b", "c", "d"`

### 4. Pembersih Duplikat Baris
Menghapus duplikat baris sambil mempertahankan urutan kemunculan pertama.

Tambahan:
- menampilkan jumlah baris awal
- menampilkan jumlah baris setelah proses

## UX yang Sudah Dioptimalkan

- Sidebar menu untuk pindah fitur dengan cepat.
- Setiap hasil punya area scroll internal agar output panjang tetap nyaman dibaca.
- Tombol copy tersedia di setiap output utama.

## Cara Menjalankan

### Opsi 1: Buka langsung di browser
Cukup buka file `index.html`.

### Opsi 2: Jalankan dengan Live Server (disarankan)
1. Buka project ini di VS Code.
2. Install extension `Live Server` (oleh Ritwick Dey) jika belum ada.
3. Klik kanan file `index.html`.
4. Pilih `Open with Live Server`.

Lalu buka URL local yang dibuat oleh Live Server (biasanya `http://127.0.0.1:5500`).

## Catatan Keamanan (Penting)

Saat menggunakan command yang mengandung `-delete`:
1. Selalu jalankan versi `-print` terlebih dulu.
2. Cek jumlah dengan `| wc -l` sebelum hapus.
3. Untuk daftar sangat panjang, gunakan mode file (`keep.txt` / `pick.txt`) agar aman dari limit panjang command.
