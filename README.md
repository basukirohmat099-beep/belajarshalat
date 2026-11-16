# Panduan Shalat Lengkap

Website statis HTML/CSS/JavaScript, siap untuk Vercel.

## Menjalankan lokal
Jalankan `python -m http.server 8080` dari folder project, lalu buka `http://localhost:8080`. Service Worker hanya aktif melalui localhost atau HTTPS.

## Deploy ke Vercel
1. Unggah folder ini ke repository GitHub.
2. Di Vercel pilih Add New → Project, impor repository.
3. Framework Preset: Other. Build Command dan Output Directory dapat dikosongkan (root project).
4. Deploy. Tidak memerlukan backend.

## Aset foto
Foto referensi yang Anda unggah disimpan sebagai `assets/images/sujud-referensi.jpg` dan dipakai untuk contoh sujud. Foto terpisah untuk 11 gerakan lain belum disediakan. Tambahkan foto yang benar dan berlisensi ke `assets/images/`, lalu isi properti `gambar` pada `data/gerakan.js`.

## Aset audio
Belum ada file MP3 yang disediakan. Simpan rekaman yang telah diperiksa pelafalannya di `assets/audio/`, misalnya `takbir.mp3`, `rukuk.mp3`, `iktidal.mp3`, `sujud.mp3`, `tasyahud.mp3`, dan `salam.mp3`. Hubungkan nama file pada data bacaan sebelum mengaktifkan tombol pemutar.

## Catatan konten
Konten ini kerangka edukasi awal, bukan pengganti guru, mushaf, atau kitab fikih. Verifikasi teks Arab, harakat, transliterasi, terjemahan, dalil, serta variasi mazhab oleh pengajar yang kompeten sebelum dipublikasikan.

## Fitur yang berjalan
- Navigasi SPA, kategori, pencarian sederhana.
- Galeri/detail 12 urutan gerakan; satu foto referensi sujud yang tersedia.
- Bacaan berurutan (iftitah, Fatihah, iktidal, tasyahud awal/akhir, shalawat, doa sebelum salam, qunut, salam), niat, doa, dan lima surat pendek lengkap.
- Bookmark, checklist progres, kuis.
- Tema preset, warna, ukuran huruf, font, radius kartu, dark mode; tersimpan di LocalStorage.
- Manifest, Service Worker, cache aset inti untuk offline setelah kunjungan pertama.

## Batasan
Audio MP3 untuk frasa gerakan shalat, playlist lengkap, unduhan offline, teks seluruh surat Al-Qur’an, kalender Hijriah, serta fitur arah kiblat belum disediakan. Audio murottal lima surah tersedia melalui streaming internet. Tambahkan aset dan data terverifikasi sebelum menyatakan fitur tersebut tersedia.

## Perubahan revisi
- Tombol "Tandai selesai" kini bisa dibatalkan (toggle).
- Bacaan shalat dilengkapi; surat pendek berisi teks penuh.
- Cache Service Worker dinaikkan ke v2 agar data baru termuat.
- Menu dirampingkan: Galeri Gerakan, Belajar Pemula, Audio Bacaan, dan Shalat Sunnah dihapus (duplikat/kosong). Murottal kini diputar dari halaman Surat Pendek. Cache v3.
- Halaman Bacaan: label Wajib/Sunnah dan filter "Wajib saja" untuk pemula. Cache v4.
- Al-Fatihah di halaman Bacaan kini bisa diputar (murottal streaming). Bacaan lain menunggu rekaman MP3. Cache v5.
- Bacaan tanpa rekaman memakai suara mesin browser (ar-SA) sebagai bantuan sementara; ganti dengan MP3 qari/guru bila ada. Cache v6.
