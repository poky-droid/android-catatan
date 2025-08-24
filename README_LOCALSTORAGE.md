# Aplikasi Keuangan dengan LocalStorage

## 🚀 Fitur Utama

Aplikasi keuangan ini menggunakan **localStorage** untuk menyimpan data secara lokal tanpa memerlukan server atau database. Semua data disimpan di browser/device pengguna.

## ✨ Fitur yang Tersedia

### 📊 Manajemen Transaksi
- ✅ Tambah transaksi baru (pendapatan/pengeluaran)
- ✅ Edit transaksi yang sudah ada
- ✅ Hapus transaksi
- ✅ Lihat riwayat transaksi
- ✅ Filter berdasarkan jenis (pendapatan/pengeluaran)

### 💰 Dashboard Keuangan
- ✅ Tampilan saldo total
- ✅ Total pendapatan dan pengeluaran
- ✅ Grafik transaksi
- ✅ Ringkasan keuangan real-time

### 🔧 Pengaturan Pengguna
- ✅ Nama pengguna
- ✅ Mata uang (IDR)
- ✅ Tema aplikasi

### 📁 Manajemen Data
- ✅ Export data ke JSON
- ✅ Import data dari JSON
- ✅ Backup dan restore data
- ✅ Hapus semua data

## 🛠️ Cara Penggunaan

### 1. Menambah Transaksi
1. Klik tombol **"+ Tambah Transaksi"**
2. Pilih jenis transaksi (Pendapatan/Pengeluaran)
3. Masukkan jumlah dalam Rupiah
4. Tambahkan catatan (opsional)
5. Pilih tanggal
6. Klik **"Simpan Transaksi"**

### 2. Mengelola Transaksi
- **Lihat**: Transaksi ditampilkan otomatis di halaman utama
- **Edit**: Klik pada transaksi untuk mengedit
- **Hapus**: Klik ikon 🗑️ untuk menghapus

### 3. Export/Import Data
- **Export**: Data dapat diexport ke file JSON
- **Import**: File JSON dapat diimport untuk restore data
- **Backup**: Simpan file JSON sebagai backup

## 🏗️ Arsitektur Sistem

### Struktur File
```
src/
├── services/
│   └── localStorageService.ts    # Service untuk localStorage
├── hooks/
│   └── useLocalTransactions.ts   # Hook untuk state management
└── utils/
    └── storage.ts                # Tipe data dan interface

components/ui/
├── BalanceCard.tsx               # Kartu saldo dan ringkasan
├── TransactionForm.tsx           # Form tambah/edit transaksi
├── TransactionItem.tsx           # Item transaksi individual
└── Chart.tsx                     # Grafik transaksi
```

### Data Flow
1. **User Input** → TransactionForm
2. **Validation** → Form validation
3. **Storage** → localStorageService
4. **State Update** → useLocalTransactions hook
5. **UI Update** → React components

## 💾 Penyimpanan Data

### LocalStorage Keys
- `transactions`: Array transaksi
- `user_settings`: Pengaturan pengguna

### Struktur Data Transaction
```typescript
interface Transaction {
  id: string;                    // ID unik otomatis
  type: "income" | "expense";    // Jenis transaksi
  amount: number;                // Jumlah dalam Rupiah
  note?: string;                 // Catatan (opsional)
  date: string;                  // Tanggal (YYYY-MM-DD)
}
```

### Struktur Data User Settings
```typescript
interface UserSettings {
  name: string;                  // Nama pengguna
  currency: string;              // Mata uang
  theme: 'light' | 'dark';      // Tema aplikasi
}
```

## 🔒 Keamanan dan Privasi

### Keuntungan LocalStorage
- ✅ **Privasi**: Data tersimpan lokal di device pengguna
- ✅ **Offline**: Bisa digunakan tanpa internet
- ✅ **Cepat**: Tidak ada latency jaringan
- ✅ **Gratis**: Tidak ada biaya hosting/server

### Keterbatasan
- ⚠️ **Data Lokal**: Data hanya tersimpan di satu device
- ⚠️ **Kapasitas**: LocalStorage terbatas (~5-10MB)
- ⚠️ **Backup Manual**: Perlu export/import untuk backup
- ⚠️ **Tidak Sync**: Tidak ada sinkronisasi antar device

## 🚀 Pengembangan Selanjutnya

### Fitur yang Bisa Ditambahkan
1. **Kategori Transaksi**: Makanan, transport, hiburan, dll
2. **Budget Planning**: Target pengeluaran bulanan
3. **Reports**: Laporan bulanan/tahunan
4. **Charts**: Grafik yang lebih detail
5. **Notifications**: Reminder tagihan
6. **Multi-currency**: Dukungan mata uang lain
7. **Cloud Sync**: Sinkronisasi ke cloud (opsional)

### Teknologi yang Bisa Diintegrasikan
- **IndexedDB**: Untuk data yang lebih besar
- **PWA**: Progressive Web App
- **Offline Support**: Service Worker
- **Push Notifications**: Notifikasi real-time

## 🐛 Troubleshooting

### Data Tidak Tersimpan
- Pastikan localStorage tersedia di browser
- Cek kapasitas localStorage (biasanya 5-10MB)
- Coba refresh halaman

### Form Tidak Bisa Dibuka
- Pastikan semua dependencies terinstall
- Cek console untuk error JavaScript
- Restart aplikasi

### Data Hilang
- Cek apakah ada export data sebelumnya
- Pastikan tidak ada clear localStorage
- Gunakan fitur import untuk restore

## 📱 Kompatibilitas

### Browser Support
- ✅ Chrome (Android & Desktop)
- ✅ Safari (iOS & macOS)
- ✅ Firefox
- ✅ Edge

### Device Support
- ✅ Android (Chrome)
- ✅ iOS (Safari)
- ✅ Desktop (Semua browser modern)
- ✅ Tablet (Semua browser modern)

## 💡 Tips Penggunaan

1. **Backup Regular**: Export data setiap minggu/bulan
2. **Kategorisasi**: Gunakan catatan untuk mengelompokkan transaksi
3. **Update Rutin**: Update transaksi setiap hari
4. **Review Bulanan**: Cek laporan keuangan bulanan
5. **Budget Planning**: Tetapkan target pengeluaran

---

**Aplikasi ini 100% berjalan di browser tanpa server, memberikan privasi dan kontrol penuh atas data keuangan Anda!** 🎉
