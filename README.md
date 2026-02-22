# suryadiarsyil-ops

Aplikasi Android berbasis HTML yang dibangun menggunakan **Apache Cordova** dan di-build otomatis menjadi file APK melalui **GitHub Actions**.

---

## 📁 Struktur Proyek

```
exampleapp/
├── .github/
│   └── workflows/
│       └── build.yml       # GitHub Actions CI/CD workflow
├── www/
│   ├── index.html          # Halaman utama aplikasi
│   ├── css/
│   │   └── style.css       # Stylesheet
│   └── js/
│       └── app.js          # Logika aplikasi Cordova
├── config.xml              # Konfigurasi Cordova
├── package.json            # Dependensi npm
├── .gitignore
└── README.md
```

---

## ⚙️ Cara Kerja CI/CD

Setiap kali ada **push ke branch `main`**, GitHub Actions akan otomatis:

1. Checkout repository
2. Setup Java 17 (Temurin) dan Node.js 18
3. Install Cordova secara global
4. Install dependensi npm
5. Menambahkan platform Android
6. Build APK debug
7. Mengupload `app-debug.apk` sebagai **artifact** yang bisa diunduh

---

## 📦 Mengunduh APK

1. Buka tab **Actions** di repository GitHub kamu
2. Pilih workflow run terbaru
3. Scroll ke bagian **Artifacts**
4. Klik **app-debug-apk** untuk mengunduh

---

## 🛠️ Menjalankan Secara Lokal

Pastikan sudah menginstall:
- [Node.js](https://nodejs.org/) versi 18+
- [Java JDK](https://adoptium.net/) versi 17
- [Android SDK](https://developer.android.com/studio) (via Android Studio)

```bash
# Clone repository
git clone https://github.com/suryadiarsyil-ops/exampleapp.git
cd exampleapp

# Install dependensi
npm install

# Install Cordova (jika belum)
npm install -g cordova

# Tambah platform Android
cordova platform add android

# Build APK debug
cordova build android

# (Opsional) Jalankan di emulator/device
cordova run android
```

APK hasil build akan tersedia di:
```
platforms/android/app/build/outputs/apk/debug/app-debug.apk
```

---

## 📋 Konfigurasi Aplikasi

| Key | Value |
|-----|-------|
| App ID | `com.suryadi.exampleapp` |
| Versi | `1.0.0` |
| Min SDK | 22 (Android 5.1) |
| Target SDK | 33 (Android 13) |
| Author | suryadi |

---

## 🔧 Kustomisasi

- **Nama & ID aplikasi** → edit `config.xml`
- **Tampilan** → edit `www/css/style.css`
- **Logika** → edit `www/js/app.js`
- **Halaman utama** → edit `www/index.html`

---

## 📄 Lisensi

MIT © 2025 [suryadiarsyil](https://github.com/suryadiarsyil-ops/exampleapp.git)
# suryadiarsyil-ops
