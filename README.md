# RCHMT CLIPPER AI — Starter V1

Starter website untuk clipping video pribadi. Antarmuka dibuat mobile-first dan mesin FFmpeg berjalan di browser (WebAssembly).

## Fitur yang aktif
- Pilih video dari perangkat
- Preview video dan durasi
- Atur timestamp mulai dan durasi
- Potong video dan ekspor MP4
- Crop tengah ke format vertikal 9:16
- Pilihan kualitas encoding
- PWA dasar (dapat ditambahkan ke layar utama setelah di-host melalui HTTPS)

## Keterbatasan penting
- Ini belum setara OpusClip: AI highlight, subtitle otomatis, face tracking, dan batch clipping belum diimplementasikan.
- FFmpeg.wasm lebih lambat dan lebih berat daripada FFmpeg native. Mulai uji dengan video MP4 kecil (disarankan <100 MB) dan klip 15–30 detik.
- Pemrosesan tetap di perangkat. File video tidak diunggah ke server oleh kode starter ini.
- Koneksi internet diperlukan untuk memuat library FFmpeg dari CDN saat pertama kali digunakan.
- Tidak ada jaminan performa pada semua HP Android; hasil bergantung pada chipset, browser, codec, ukuran video, dan memori bebas.

## Cara mencoba dari HP Android (tanpa komputer)
1. Simpan dan ekstrak ZIP ini.
2. Buat repository GitHub baru dari browser Chrome, misalnya `rchmt-clipper-ai`.
3. Upload `index.html`, `manifest.json`, `sw.js`, dan folder `assets`.
4. Aktifkan GitHub Pages melalui Settings → Pages → Deploy from a branch → `main` → `/root`.
5. Buka alamat website HTTPS yang diberikan GitHub Pages menggunakan Chrome Android.
6. Pilih video kecil, mulai 0 detik, durasi 15 detik, lalu tekan PROSES POTONG VIDEO.
7. Jika berhasil, unduh MP4. Tambahkan website ke layar utama melalui menu Chrome → Add to Home screen.

## Roadmap
- V1.1: perbaikan UX, validasi codec, pilihan ukuran output.
- V2: subtitle otomatis menggunakan model ASR kecil di browser; perlu pengujian performa dan dukungan WebGPU/WASM.
- V2: editor subtitle, gaya caption, safe-area, dan crop manual.
- V3: analisis transkrip untuk menyarankan highlight, skor klip, dan batch export.

## Catatan lisensi
Periksa lisensi FFmpeg dan build core yang dipakai sebelum distribusi publik atau penggunaan komersial. Starter ini memuat FFmpeg.wasm dan util dari jsDelivr CDN.
