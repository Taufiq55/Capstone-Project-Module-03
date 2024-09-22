# Hotel Reservation Cancellation Prediction

![Bellagio-Hotel-Casino-Las-Vegas](https://github.com/user-attachments/assets/ae31b187-377c-4c9e-b2cf-305ecc2fd496)

## Overview

Proyek ini bertujuan untuk mengembangkan model prediktif yang secara akurat meramalkan pembatalan reservasi hotel. Dengan mengidentifikasi potensi pembatalan lebih awal, hotel dapat meminimalkan kehilangan pendapatan dan mengoptimalkan alokasi kamar. Fokus utama adalah mengurangi false negatives, di mana pelanggan yang diprediksi tidak membatalkan ternyata melakukan pembatalan.

## Business Question

**Bagaimana kita dapat memprediksi dengan akurat apakah seorang pelanggan akan membatalkan reservasi hotel, sehingga mengurangi kehilangan pendapatan akibat kesalahan prediksi?**

## Goal

- Mengembangkan model prediksi yang meminimalkan kerugian finansial dari pembatalan reservasi yang tidak terduga.
- Mengurangi jumlah false negatives dalam prediksi pembatalan.
- Membandingkan efektivitas model machine learning dengan model berbasis aturan dalam memprediksi pembatalan.

## Data

Dataset terdiri dari **83.573 data** dengan fitur sebagai berikut:

| **Nama Kolom**               | **Deskripsi**                                                |
|-------------------------------|----------------------------------------------------------------|
| `country`                     | Negara asal.                                           |
| `market_segment`              | Penetapan segmen pasar.                              |
| `previous_cancellations`      | Jumlah pemesanan sebelumnya yang dibatalkan oleh pelanggan.        |
| `booking_changes`             | Jumlah perubahan yang dilakukan pada pemesanan.                      |
| `deposit_type`                | Indikasi apakah pelanggan telah membayar deposit untuk menjamin pemesanan. |
| `days_in_waiting_list`        | Jumlah hari pemesanan berada dalam daftar tunggu.          |
| `customer_type`               | Tipe pemesanan.                                            |
| `reserved_room_type`          | Kode tipe kamar yang dipesan.                                            |
| `required_car_parking_space`  | Jumlah tempat parkir mobil yang dibutuhkan oleh pelanggan.      |
| `total_of_special_request`    | Jumlah permintaan khusus yang diajukan oleh pelanggan.            |
| `is_canceled`                 | Nilai yang menunjukkan apakah pemesanan dibatalkan (1) atau tidak (0).  |

## Methodology

### Analityc Approach

1. **Persiapan Data**: Membersihkan dan memproses dataset.
2. **Pemilihan Model**: Menguji berbagai model klasifikasi:
   - RandomForestClassifier
   - XGBClassifier
   - DecisionTreeClassifier
   - LogisticRegression
   - KNeighborsClassifier
   - GradientBoostingClassifier

### Metric Evaluation

Metrik evaluasi utama adalah **F2-score**, yang lebih fokus pada recall untuk mengurangi false negatives.

## Result

### Kinerja Model

- **Model Machine Learning**:
  - Skor F2: **70,4%**
  - True Positives (TP): 421 prediksi pembatalan; 337 kamar berhasil dijual kembali.
  - Pendapatan Diselamatkan: **Rp 235.900.000**
  - False Negatives (FN): 60 pembatalan tidak terdeteksi; kerugian Rp 42.000.000.
  - Dampak Bersih Pendapatan: **Rp 193.900.000 diselamatkan per malam.**

- **Model Rule Based**:
  - Skor F2: **46,7%**
  - True Positives (TP): 250 prediksi pembatalan; 200 kamar berhasil dijual kembali.
  - Pendapatan Diselamatkan: **Rp 140.000.000**
  - False Negatives (FN): 231 pembatalan tidak terdeteksi; kerugian Rp 161.700.000.
  - Dampak Bersih Pendapatan: **Rp 21.700.000 hilang per malam.**

## Recommendation

1. **Adopsi Model Machine Learning** sebagai pendekatan utama untuk memprediksi pembatalan.
2. **Tingkatkan Model** dengan mengumpulkan fitur tambahan seperti waktu pemesanan, jumlah kamar, metode pembayaran, kebijakan pembatalan, rating pelanggan, dan acara musiman.
3. **Pantau dan Evaluasi** model secara berkala untuk memastikan efektivitasnya yang berkelanjutan.

## Conclusion

Mengimplementasikan model machine learning untuk memprediksi pembatalan reservasi hotel secara signifikan mengurangi kerugian pendapatan dan meningkatkan efisiensi operasional. Peningkatan terus-menerus dan pengumpulan fitur tambahan akan lebih meningkatkan akurasi prediksi dan kemampuan pengambilan keputusan.
