
## ✨ Fitur Utama

- **🔐 Autentikasi PIN**: Keamanan berlapis dengan sistem PIN untuk melindungi catatan pribadi
- **📝 Manajemen Catatan**: Tambah, edit, dan hapus catatan dengan mudah
- **💾 Penyimpanan Lokal**: Data tersimpan aman di perangkat menggunakan SQLite
- **📱 Antarmuka User-Friendly**: Desain yang bersih dan mudah digunakan
- **🔄 Real-time Updates**: Perubahan catatan langsung tersinkronisasi
- **📅 Timestamp**: Setiap catatan memiliki waktu pembuatan dan pembaruan

### Dependencies

```yaml
dependencies:
  flutter: ^3.9.0
  sqflite: ^2.4.2 # Database lokal
  shared_preferences: ^2.5.3 # Penyimpanan preferensi
  path: ^1.9.1 # Manajemen path file
  cupertino_icons: ^1.0.8 # Icon iOS
```

## 📱 Screenshot dan Fitur

### 1. Halaman Login PIN

- Input PIN untuk akses pertama kali (membuat PIN baru)
- Verifikasi PIN untuk akses selanjutnya
- Tombol show/hide PIN untuk keamanan

### 2. Halaman Utama Catatan

- Daftar semua catatan dengan tanggal pembuatan
- Floating Action Button untuk menambah catatan baru
- Tombol logout di AppBar
- Preview konten catatan

### 3. Fitur CRUD Catatan

- **Create**: Dialog untuk menambah catatan baru dengan judul dan isi
- **Read**: Tampilan daftar catatan dengan preview
- **Update**: Edit catatan dengan dialog yang sama seperti tambah
- **Delete**: Konfirmasi hapus catatan dengan dialog

## 🚀 Instalasi dan Menjalankan Aplikasi

### Prasyarat

- Flutter SDK (versi 3.9.0 atau lebih baru)
- Android Studio / VS Code
- Android SDK untuk development Android
- Xcode untuk development iOS (khusus macOS)

### Langkah Instalasi

1. **Clone repository**

   ```bash
   git clone <repository-url>
   cd flutter_catatan_app
   ```

2. **Install dependencies**

   ```bash
   flutter pub get
   ```

3. **Jalankan aplikasi**
   ```bash
   flutter run
   ```

### Build untuk Release

**Android:**

```bash
flutter build apk --release
```

**iOS:**

```bash
flutter build ios --release
```

**Web:**

```bash
flutter build web
```

## 📁 Struktur Project

```
lib/
├── main.dart                 # Entry point aplikasi
├── data/
│   ├── database_local.dart   # Kelas untuk manajemen database SQLite
│   ├── note.dart            # Model data catatan
│   └── pin_service.dart     # Service untuk manajemen PIN
└── pages/
    ├── home_page.dart       # Halaman utama daftar catatan
    └── pin_page.dart        # Halaman login dengan PIN
```

## 🔧 Konfigurasi

### Database Schema

Database SQLite dengan tabel `notes`:

```sql
CREATE TABLE notes(
  id TEXT PRIMARY KEY,
  title TEXT,
  content TEXT,
  createdAt TEXT,
  updatedAt TEXT
)
```

### Permissions (Android)

Aplikasi menggunakan permission berikut di `android/app/src/main/AndroidManifest.xml`:

```xml
<uses-permission android:name="android.permission.INTERNET"/>
```

