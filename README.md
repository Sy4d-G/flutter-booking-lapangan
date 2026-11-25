# Apex Sport - Aplikasi Booking Lapangan Olahraga

Aplikasi mobile berbasis **Flutter murni (Standalone Client)** untuk reservasi dan penyewaan lapangan olahraga secara cepat, transparan, dan interaktif.

---

## 📱 Fitur Utama

### 1. Eksplorasi & Katalog Lapangan
- **Filter Multi-Cabang Olahraga**: Futsal, Badminton, Basket, Voli, dan Mini Soccer.
- **Informasi Lengkap**: Tipe lantai (Vinyl Taraflex, Parquet Kayu, Rumput Sintetis FIFA), fasilitas (lampu lux, loker, shower), jam operasional (07:00 - 23:00), dan aturan bermain.
- **Pencarian Cerdas**: Pencarian instan berdasarkan nama lapangan, lokasi, atau jenis lantai.

### 2. Alur Reservasi & Pemilihan Slot (*Slot Picker*)
- **Matriks Jadwal Jam**: Tampilan slot interaktif per jam dengan indikator warna status (*Tersedia* / *Sudah Dipesan*).
- **Multi-Slot Selection**: Pemilihan beberapa jam bermain sekaligus dengan penghitungan total harga otomatis.
- **Hold Lock Timer**: Penguncian sementara slot selama 10 menit saat pengguna memproses pesanan.

### 3. Pembayaran & Konfirmasi
- **Metode Pembayaran**: Transfer Bank (BCA, Mandiri) dan QRIS Statis/Dinamis.
- **Unggah Bukti Transfer**: Integrasi kamera langsung dan galeri perangkat (`image_picker`).
- **Split Payment**: Penggunaan saldo dompet refund untuk memotong total tagihan sewa.

### 4. E-Ticket Digital (*Boarding Pass*)
- Tiket digital interaktif bergaya *boarding pass* dengan *notch cut*.
- Dilengkapi detail reservasi, status verifikasi admin, dan kode QR untuk pemindaian (*check-in*) di pintu masuk lapangan.

### 5. Dompet Refund Akumulatif (Kebijakan Pembatalan H-1)
- Pembatalan sewa maksimal H-1 secara otomatis memproses penalti 20% dan mengembalikan 80% dana ke **Dompet Saldo**.
- Saldo dompet dapat langsung dibelanjakan kembali untuk pemesanan lapangan berikutnya.

### 6. Profil & Layanan Pengguna
- **Guest Mode & Akun Terdaftar**: Menjelajah katalog tanpa harus login; proteksi autentikasi aktif saat menuju checkout.
- **Kelola Rekening Refund**: Simpan data rekening bank atau e-wallet untuk keperluan pencairan dana.
- **Dukungan WhatsApp**: Tombol bantuan langsung membuka chat WhatsApp admin dengan pesan otomatis.

---

## 📂 Struktur Proyek

```text
lib/
├── main.dart                  # Titik masuk utama aplikasi (Entry point)
├── models/                    # Definisi model data
│   ├── booking.dart           # Model reservasi, status tiket, dan riwayat
│   ├── field.dart             # Model venue lapangan, court, dan fasilitas
│   └── refund_account.dart    # Model rekening bank pengembalian dana
├── screens/                   # Layar antarmuka pengguna (UI Screens)
│   ├── welcome_screen.dart    # Layar onboarding & pengantar
│   ├── auth_screen.dart       # Layar login & registrasi tab
│   ├── home_screen.dart       # Beranda utama, katalog, & floating bottom bar
│   ├── venue_detail_screen.dart # Detail spesifikasi lapangan & fasilitas
│   ├── slot_picker_screen.dart  # Pemilihan tanggal & slot jam bermain
│   ├── checkout_screen.dart   # Review pesanan, split payment, & metode bayar
│   ├── ticket_pass_screen.dart  # E-ticket digital & QR code pass
│   ├── history_screen.dart    # Riwayat reservasi (Aktif / Selesai / Dibatalkan)
│   ├── profile_screen.dart    # Profil pengguna, dompet refund, & rekening bank
│   └── notifications_screen.dart # Layar notifikasi transaksi & reservasi
├── services/                  # State management reaktif (ValueNotifier)
│   ├── auth_service.dart      # Manajemen sesi login & mode guest
│   ├── booking_service.dart   # Manajemen data booking & mutasi tiket
│   ├── favorite_service.dart  # Manajemen lapangan favorit
│   └── wallet_service.dart    # Manajemen saldo refund & transaksi dompet
├── theme/                     # Desain sistem & palet warna
│   └── app_colors.dart        # Standar warna (Emerald Green, Mint, Dark Text)
├── utils/                     # Fungsi pembantu (Helper)
│   └── date_formatter.dart    # Format tanggal dan jam bahasa Indonesia
└── widgets/                   # Komponen UI modular
    ├── category_chip.dart     # Chip kategori olahraga
    ├── custom_search_bar.dart # Input pencarian dengan ikon
    ├── field_card.dart        # Kartu informasi lapangan
    └── primary_button.dart    # Tombol aksi utama
```

---

## 🚀 Cara Menjalankan Aplikasi

1. **Pastikan Flutter SDK terpasang** (versi 3.12.0 atau lebih baru):
   ```bash
   flutter --version
   ```

2. **Unduh seluruh dependensi**:
   ```bash
   flutter pub get
   ```

3. **Jalankan pada perangkat / emulator**:
   ```bash
   # Melihat daftar device yang tersedia
   flutter devices

   # Menjalankan aplikasi
   flutter run
   ```

4. **Build APK Debug / Release**:
   ```bash
   # Build APK Debug
   flutter build apk --debug

   # Build APK Release
   flutter build apk --release
   ```
