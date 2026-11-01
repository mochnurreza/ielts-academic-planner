# IELTS Academic 6.5 Planner — PWA

## Isi paket
- `index.html`: planner, jadwal, tautan materi, checklist, evaluasi, pengaturan reminder.
- `manifest.webmanifest`: metadata instalasi PWA.
- `sw.js`: cache offline dan penanganan klik notifikasi.
- `icons/`: ikon aplikasi 192px dan 512px.

## Deploy gratis
PWA harus diakses melalui HTTPS (atau localhost). Upload seluruh isi folder ini ke salah satu static hosting:
- GitHub Pages
- Cloudflare Pages
- Netlify

Jangan hanya mengunggah `index.html`; sertakan manifest, service worker, dan folder icons.

## Android
1. Deploy folder ini dan buka URL HTTPS di Chrome.
2. Pilih menu ⋮ → Install app / Add to Home screen.
3. Buka aplikasi dari ikon homescreen.
4. Di bagian Pengingat belajar, pilih jam → Aktifkan notifikasi → izinkan.
5. Tekan Tes notifikasi untuk memastikan izin berfungsi.

## iPhone / iPad
1. Deploy dan buka URL HTTPS di Safari.
2. Tekan Share → Add to Home Screen → Add.
3. Buka dari ikon homescreen.
4. Atur jam reminder dan izinkan notifikasi.
5. Web Push notifications pada iOS/iPadOS memerlukan versi 16.4 atau lebih baru dan aplikasi web ditambahkan ke Home Screen.

## Batasan reminder penting
Versi ini memakai pemeriksaan waktu di halaman aplikasi saat aplikasi/browser aktif atau dibuka kembali. Browser tidak menjamin JavaScript berjalan tepat waktu ketika aplikasi ditutup atau sistem menghemat baterai. Service worker di sini menangani cache/offline dan klik notifikasi, bukan alarm terjadwal persisten.

Untuk reminder yang benar-benar terkirim pada jam tertentu walaupun aplikasi ditutup, perlu ditambahkan backend push notification (misalnya layanan push + server/cron) dan konfigurasi VAPID. Versi ini tidak mengirim data belajar ke server.

## Penyimpanan
Checklist dan evaluasi tersimpan di localStorage perangkat/browser masing-masing. Data tidak otomatis tersinkron antarperangkat.
