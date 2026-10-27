# SuryaMart Data Analysis — Harisenin Bootcamp Project Assignment

![Excel](https://img.shields.io/badge/Tools-Microsoft_Excel_%7C_Google_Sheets-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Bootcamp](https://img.shields.io/badge/Program-Harisenin_Data_Analytics_Bootcamp-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Selesai-success?style=for-the-badge)

> **Hands-on Case Study Project** — Menganalisis 1.000+ data transaksi pelanggan untuk mengoptimalkan kampanye promosi, manajemen inventaris produk, dan strategi pemasaran regional pada e-commerce **SuryaMart**.

---

## 📌 Latar Belakang Proyek
Repositori ini berisi proyek analisis data *end-to-end* yang dikerjakan sebagai bagian dari **Harisenin Data Analytics Bootcamp**. Studi kasus berfokus pada **SuryaMart**, sebuah platform *e-commerce* yang ingin mengevaluasi efektivitas kampanye pemasaran mereka berdasarkan data perilaku konsumen serta mengoptimalkan strategi penjualan produk.

Melalui pengolahan lebih dari 1.000 baris data transaksi, analisis ini membedah pola belanja konsumen dari sisi demografi usia, preferensi gender, distribusi wilayah (kota), efektivitas penggunaan diskon, hingga dampak media sosial.

---

## 🛠️ Tahap Data Cleaning & Transformasi
Sebelum dianalisis menggunakan Pivot Table, data mentah telah melalui proses pembersihan dan transformasi:

1. **Penghapusan Duplikat**: Memeriksa keunikan `Customer_ID` dan menghapus baris data duplikat.
2. **Penanganan Missing Values**: Mengisi data kosong (*null/blank*) pada kolom `Purchase_Category` menjadi kategori `"Books"` sesuai instruksi bisnis.
3. **Standardisasi Teks (Proper Case & Typo)**: Membersihkan karakter anomali/angka berlebih dan menyeragamkan penulisan huruf kapital di awal kata (contoh: mengubah `HoTELS0` menjadi `Hotels` dan `LUXury GoODs0` menjadi `Luxury Goods`).
4. **Validasi Format Numerik**: Memastikan atribut `Age`, `Purchase_Amount (Rp)`, dan `Frequency_of_Purchase` berformat angka yang valid.
5. **Transformasi Data (Clustering dengan Nested IF)**:
   - **Cluster Usia (`Cluster_Usia`)**: Mengelompokkan umur pelanggan ke dalam 11 rentang usia (`18-20` hingga `48-50`) menggunakan rumus `IF` bertingkat:
     ```excel
     =IF(B2<=20,"18-20",IF(B2<=23,"21-23",IF(B2<=26,"24-26",IF(B2<=29,"27-29",IF(B2<=32,"30-32",IF(B2<=35,"33-35",IF(B2<=38,"36-38",IF(B2<=41,"39-41",IF(B2<=44,"42-44",IF(B2<=47,"45-47","48-50"))))))))))
     ```
   - **Cluster Pengeluaran (`Cluster_Pengeluaran`)**: Mengelompokkan nominal belanja ke dalam interval Rp 1.000.000 (mulai dari `<1.000.000` hingga `>10.000.000`).

### 📸 Cuplikan Hasil Data Cleaning & Clustering
> *Dokumentasi pengerjaan pembersihan data dan pembuatan kolom baru (`Cluster_Usia` & `Cluster_Pengeluaran`):*

![Hasil Data Cleaning](assets/data_cleaning.png)

---

## 🧮 Eksplorasi Data dengan Pivot Table
Seluruh pertanyaan bisnis dijawab dengan membangun **6 Pivot Table** terpisah untuk mengagregasi total penjualan (`SUM`), frekuensi transaksi (`COUNT`), dan rata-rata nilai pembelian (`AVERAGE`).

### 📸 Cuplikan Pengerjaan Pivot Table
| Pivot Table 1 & 2 (Gender & Kategori Produk) | Pivot Table 3 & 4 (Lokasi Kota & Diskon) |
| :---: | :---: |
| ![Pivot 1-2](assets/pivot_1_2.png) | ![Pivot 3-4](assets/pivot_3_4.png) |

| Pivot Table 5 (Cluster Usia) | Pivot Table 6 (Pengaruh Media Sosial) |
| :---: | :---: |
| ![Pivot 5](assets/pivot_5.png) | ![Pivot 6](assets/pivot_6.png) |

---

## 📈 Visualisasi Data & Analisis Grafik
Berikut adalah visualisasi data yang dirancang di lembar kerja `c. Visualisasi Data` beserta analisis singkatnya:

### 1. Total Penjualan per Kategori Produk
![Chart Kategori Produk](assets/chart_kategori.png)
* **Analisis**: Kategori **Sports & Outdoors** unggul di posisi pertama (Rp 236,65 Juta), diikuti oleh *Jewelry & Accessories* (Rp 232,34 Juta). Sebaliknya, *Arts & Crafts* berada di urutan paling bawah (Rp 116,71 Juta).

### 2. Preferensi Kategori Produk Berdasarkan Gender
![Chart Preferensi Gender](assets/chart_gender.png)
* **Analisis**: Terlihat kontras yang jelas di mana pelanggan wanita mendominasi pembelian produk bayi dan perawatan diri, sedangkan pelanggan pria mendominasi produk buku, olahraga, dan elektronik.

### 3. Kontribusi Total Pembelian Berdasarkan Kota
![Chart Kontribusi Kota](assets/chart_kota.png)
* **Analisis**: Kota **Makassar** menjadi kontributor pendapatan terbesar bagi SuryaMart (Rp 806,80 Juta), mengungguli Bandung (Rp 769,13 Juta) dan Jakarta (Rp 746,20 Juta).

### 4. Pengaruh Penggunaan Diskon Terhadap Nilai Transaksi
![Chart Dampak Diskon](assets/chart_diskon.png)
* **Analisis**: Pelanggan yang menggunakan diskon mencatatkan frekuensi transaksi lebih banyak (525 transaksi) dengan nilai rata-rata pembelanjaan yang tetap stabil di kisaran Rp 4,26 Juta.

### 5. Rata-rata Nilai Pembelian Berdasarkan Cluster Usia
![Chart Cluster Usia](assets/chart_usia.png)
* **Analisis**: Kelompok usia produktif **27–29 tahun** mencatatkan rata-rata nilai transaksi tertinggi sebesar Rp 4.465.280 per transaksi.

---

## 📊 Rangkuman Temuan Utama & Rekomendasi Strategi

Berikut adalah matriks rangkuman *Executive Summary* yang disusun pada lembar kerja `d. Insight Summary & Strategy`:

| No | Pertanyaan Bisnis | Temuan Data (Findings) | Insight Bisnis | Rekomendasi Strategi |
| :-: | :--- | :--- | :--- | :--- |
| **1** | **Preferensi Kategori Berdasarkan Gender** | Pelanggan **Wanita** mendominasi *Baby Products* (Rp 102,2 Juta) & *Beauty*. Pelanggan **Pria** mendominasi *Books* (Rp 102,6 Juta) & *Sports & Outdoors*. | Terdapat pola kebutuhan produk yang sangat spesifik dan terpisah antara konsumen pria dan wanita. | Terapkan personalisasi *banner homepage* dan rekomendasi produk otomatis sesuai profil gender akun pengguna. |
| **2** | **Kategori Penjualan Tertinggi & Terendah** | **Sports & Outdoors** mencetak penjualan tertinggi (**Rp 236.658.185**), sedangkan **Arts & Crafts** terendah (**Rp 116.713.760**). | Produk olahraga dan aktivitas luar ruang menjadi penggerak utama pendapatan platform, sementara produk kerajinan kurang diminati. | Perbanyak variasi stok dan adakan *flash sale* pada *Sports & Outdoors*. Kurangi stok atau buat *bundling* promosi untuk *Arts & Crafts*. |
| **3** | **Kontribusi Pembelian Berdasarkan Kota** | Kota **Makassar** menyumbang nilai transaksi terbesar (**Rp 806.802.280**), disusul oleh **Bandung** (Rp 769,1 Juta) dan **Jakarta** (Rp 746,2 Juta). | Pasar luar Jawa seperti Makassar memiliki antusiasme dan daya beli belanja online yang sangat masif. | Fokuskan alokasi anggaran iklan digital (*ads*) dan berikan subsidi ongkir khusus untuk wilayah Makassar, Bandung, dan Jakarta. |
| **4** | **Pengaruh Diskon Terhadap Rata-rata Transaksi** | Transaksi dengan diskon (`TRUE`: 525 transaksi) memiliki volume lebih tinggi dengan rata-rata nilai belanja (~Rp 4,26 Juta) yang setara dengan tanpa diskon (`FALSE`: 479 transaksi, rata-rata ~Rp 4,28 Juta). | Pemberian diskon efektif memicu kuota/frekuensi transaksi tanpa menurunkan rata-rata nominal belanja konsumen. | Pertahankan promo voucher diskon dengan menetapkan syarat *minimum pembelian* (misal min. belanja Rp 4,5 Juta) untuk menaikkan *basket size*. |
| **5** | **Rata-rata Pembelian Berdasarkan Cluster Usia** | Kelompok usia **27–29 tahun** mencatatkan rata-rata nilai transaksi tertinggi (**Rp 4.465.280**), diikuti usia **30–32 tahun** (**Rp 4.400.155**). | Segmen usia dewasa muda (27–32 tahun) yang mapan secara finansial merupakan kontributor pendapatan paling potensial. | Rancang kampanye pemasaran eksklusif dan *bundling* produk sesuai gaya hidup kelompok usia 27–32 tahun. |
| **6** | **Dampak Pengaruh Media Sosial** | Konsumen dengan pengaruh medsos **High** mencatatkan rata-rata transaksi tertinggi (**Rp 4,39 Juta**), sementara rata-rata frekuensi belanja merata di semua tingkat (~6,9–7,2 kali). | Paparan media sosial yang tinggi mendorong konsumen untuk membeli barang dengan nilai nominal yang lebih mahal. | Optimalkan konten video promosi dan kolaborasi *influencer* pada produk-produk bernilai tinggi (*high-margin*). |

---

## 👤 Penulis
**Ananda Widi Alrafi - 1306011**  
