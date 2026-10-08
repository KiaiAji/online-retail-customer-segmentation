# Analisis Perilaku Pelanggan dan Segmentasi Customer Menggunakan RFM dan K-Means

## Deskripsi

Proyek ini merupakan studi kasus analisis data transaksi pada perusahaan e-commerce menggunakan dataset **Online Retail**.

Tujuan utama proyek ini adalah menganalisis perilaku pelanggan berdasarkan data transaksi, kemudian melakukan segmentasi pelanggan menggunakan metode **RFM (Recency, Frequency, Monetary)** dan **K-Means Clustering**.

Proyek ini dibuat sebagai implementasi materi *"Make Sense of Data with Analysis and AI"*, khususnya mengenai proses data analytics mulai dari **data understanding, data preparation, analysis, modeling, evaluation, hingga pengambilan keputusan berdasarkan insight**.

---

## Tujuan

Tujuan dari proyek ini adalah:

1. Memahami karakteristik data transaksi pelanggan.
2. Melakukan pembersihan dan persiapan data.
3. Menganalisis pola transaksi dan pelanggan.
4. Menghitung nilai **Recency, Frequency, dan Monetary (RFM)** setiap pelanggan.
5. Melakukan segmentasi pelanggan menggunakan **K-Means Clustering**.
6. Mengevaluasi hasil clustering menggunakan **Elbow Method** dan **Silhouette Score**.
7. Menghasilkan insight yang dapat digunakan sebagai dasar strategi pemasaran.

---

## Dataset

Dataset yang digunakan adalah **Online Retail / E-Commerce Transaction Dataset** yang berisi data transaksi penjualan.

Beberapa atribut utama dalam dataset:

| Kolom | Keterangan |
|---|---|
| InvoiceNo | Nomor transaksi/invoice |
| StockCode | Kode produk |
| Description | Deskripsi produk |
| Quantity | Jumlah produk yang dibeli |
| InvoiceDate | Tanggal dan waktu transaksi |
| UnitPrice | Harga satuan produk |
| CustomerID | ID pelanggan |
| Country | Negara pelanggan |

Dataset memiliki data transaksi dalam jumlah besar sehingga diperlukan proses data cleaning sebelum dilakukan analisis.

> Catatan: Dataset asli tidak disertakan dalam repository untuk menghindari penyimpanan data mentah yang tidak diperlukan. Notebook menggunakan file `data.csv` sebagai input dataset.

---

## Metodologi

Proses analisis dilakukan melalui beberapa tahapan:

### 1. Data Understanding

Pada tahap ini dilakukan pemeriksaan terhadap:

- jumlah baris dan kolom,
- tipe data,
- informasi setiap variabel,
- statistik deskriptif,
- missing value,
- dan duplicate data.

### 2. Data Cleaning

Tahap preprocessing dilakukan untuk meningkatkan kualitas data.

Beberapa proses yang dilakukan:

- Menghapus data duplikat.
- Mengubah `InvoiceDate` menjadi format datetime.
- Menghapus transaksi yang dibatalkan.
- Menghapus transaksi dengan `Quantity <= 0`.
- Menghapus transaksi dengan `UnitPrice <= 0`.
- Menghapus data yang tidak memiliki `CustomerID`.

Kemudian dibuat variabel baru:

```text
Revenue = Quantity × UnitPrice
