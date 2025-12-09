# 🌋 Sistem Klasifikasi Tweet Gunung Meletus (Volcano Eruption Tweet Classifier)

## 📌 Gambaran Umum

Sistem ini adalah solusi otomatis untuk mengumpulkan, memproses, dan mengklasifikasikan tweet terkait gunung meletus dan aktivitas vulkanologi. Sistem menggunakan teknik **web scraping**, **pembersihan data**, dan **machine learning** (Logistic Regression) untuk mendeteksi apakah suatu tweet membahas tentang gunung meletus atau tidak.

---

## 🎯 Fitur Utama

1. **Pengumpulan Data Otomatis**  
   - Mengambil tweet berdasarkan keyword vulkanologi (4 kelompok keyword)
   - Rentang waktu: 2018–2025
   - Bahasa: Indonesia
   - Menggunakan token Twitter untuk akses API

2. **Pemrosesan Teks**  
   - Menghapus URL, mention (@), hashtag (#), RT, dan whitespace berlebih
   - Persiapan teks untuk analisis NLP

3. **Klasifikasi Machine Learning**  
   - Model: Logistic Regression dengan TF-IDF Vectorizer
   - Fitur: 3000 kata paling signifikan
   - Output: Kategori (Gunung Meletus / Bukan) + probabilitas

4. **Antarmuka Prediksi**  
   - Prediksi single tweet (manual input)
   - Prediksi batch dari file CSV
   - Ekspor hasil prediksi ke CSV

---

## 🚀 Cara Menggunakan

### **Langkah 1: Instalasi Dependensi**
Jalankan semua sel di notebook `FPMKMB.ipynb` secara berurutan. Sistem akan otomatis menginstal:
- Node.js v20+
- Playwright (untuk scraping)
- Library Python: pandas, scikit-learn, joblib, dll.

### **Langkah 2: Pengambilan Data Tweet**
```python
# Otomatis dijalankan dalam notebook
# Mengambil ~10.000 tweet (2500 per kelompok keyword)
# Keyword meliputi: gunung meletus, erupsi, awan panas, mitigasi, dll.
```

### **Langkah 3: Pemrosesan dan Pelatihan Model**
1. **Pembersihan Data**: Menghapus karakter tidak penting dari tweet.
2. **Pelabelan**: Semua tweet diberi label `1` (asumsi semua terkait gunung meletus).
3. **Training Model**: Logistic Regression dengan validasi 80/20.

### **Langkah 4: Prediksi**
Pilih opsi prediksi melalui menu interaktif:

#### **A. Prediksi Manual**
```
Masukkan teks tweet: "Gunung Merapi mengeluarkan awan panas setinggi 3 km"
Kategori: GUNUNG MELETUS
Probabilitas gunung meletus: 92.34%
```

#### **B. Prediksi dari File CSV**
- File harus memiliki kolom `text`
- Hasil akan diekspor ke `hasil_prediksi.csv`

---

## 🔧 Konfigurasi Keyword

Sistem menggunakan 4 kelompok keyword:

| Kelompok | Topik | Contoh Keyword |
|----------|-------|----------------|
| 1 | Aktivitas Vulkanik | gunung meletus, erupsi, seismik, tremor |
| 2 | Material Erupsi | awan panas, lava, lahar, abu vulkanik |
| 3 | Mitigasi & Status | status waspada, evakuasi, zona rawan |
| 4 | Fitur Geografis | kawah, kaldera, kubah lava, basecamp |

---

## 📊 Performa Model

- **Algoritma**: Logistic Regression
- **Vectorizer**: TF-IDF (3000 fitur)
- **Stop Words**: English (bisa disesuaikan untuk Bahasa Indonesia)
- **Akurasi**: Tergantung dataset (~85-95% dengan data berkualitas)
- **Output**: Probability score + binary classification

---

## ⚠️ Catatan Penting

1. **Token Twitter**:  
   Token `44dbcc46f990445db65fab0d47adf939ef3d8695` digunakan untuk demo.  
   **Ganti dengan token Anda sendiri** untuk penggunaan produksi.

2. **Label Data**:  
   Sistem menggunakan label `1` untuk semua data (asumsi positif).  
   Untuk hasil lebih akurat, **tambahkan data negatif** dan sesuaikan labeling.

3. **Bahasa**:  
   Model dilatih dengan tweet Bahasa Indonesia.  
   Untuk bahasa lain, ubah parameter `lang` dan `stop_words`.

4. **Rate Limiting**:  
   Sistem memiliki delay 10 detik antar kelompok keyword untuk menghindari pembatasan API.

5. **Dataset**:  
   Pastikan file CSV memiliki kolom `text` dan `label` untuk training.

---

## 📈 Potensi Pengembangan

✅ **Sudah Tersedia**:
- Pipeline end-to-end
- Model klasifikasi dasar
- Antarmuka prediksi interaktif

🚀 **Rekomendasi Pengembangan**:
1. Tambahkan dataset negatif (tweet tidak relevan)
2. Gunakan model lebih canggih (BERT, LSTM)
3. Implementasi cross-validation
4. Dashboard visualisasi hasil
5. API endpoint untuk integrasi
6. Monitoring akurasi real-time

---

## 👥 Pengguna yang Cocok

- **Peneliti Vulkanologi**: Analisis percakapan publik tentang gunung berapi
- **BPBD/BNPB**: Monitoring media sosial untuk early warning
- **Mahasiswa**: Belajar NLP dan classification project
- **Developer**: Template untuk project scraping + ML pipeline

---

## 🛠️ Troubleshooting

| Masalah | Solusi |
|---------|---------|
| Token expired | Dapatkan token baru dari Twitter API |
| File CSV tidak terbaca | Pastikan format UTF-8 dan kolom sesuai |
| Model accuracy rendah | Tambah data training, sesuaikan parameter |
| Scraping lambat | Kurangi limit per grup, tambah delay |
| Playwright error | Jalankan: `playwright install chromium` |

---

## 📄 Lisensi

Proyek edukasi - dapat digunakan dan dimodifikasi dengan atribusi.

---

## ✨ Kontributor

Sistem dikembangkan untuk tujuan akademik dan penelitian vulkanologi.  
Untuk pertanyaan atau kolaborasi, silakan buka issue atau hubungi pengembang.

---

**🔥 Tetap Waspada, Selalu Siap Siaga Terhadap Bencana Alam!**