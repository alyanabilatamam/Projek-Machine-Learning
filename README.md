# Klasifikasi Penyakit Daun Padi Menggunakan Ekstraksi Fitur MobileNetV3 dan Random Forest untuk Mendukung Pertanian Berkelanjutan 

Repositori ini disusun untuk memenuhi Tugas Proyek Ujian Akhir Semester Genap Tahun Akademik 2025/2026 matakuliah Pembelajaran Mesin, Program Studi S1 Sains Data, Universitas Negeri Surabaya.

## Anggota Kelompok 5
1. Alya Nabila Tamam (24031554099)
2. Fina Nihayatul Husna (24031554022)
3. Juli Yawati Manalu (24031554050)

## Topik
Pangan

## Rumusan Masalah
1.3 Dampak Perubahan Iklim dan Rendahnya Adopsi Pertanian Berkelanjutan

## Tujuan
Proyek ini bertujuan untuk membangun sistem klasifikasi otomatis penyakit daun padi menggunakan kombinasi MobileNetV3 sebagai feature extractor dan Random Forest sebagai classifier. Sistem ini diharapkan dapat membantu proses identifikasi penyakit tanaman secara cepat, akurat, dan efisien guna mendukung pertanian berkelanjutan dan ketahanan pangan.

## Deskripsi Singkat Proyek
Proyek ini berfokus pada penyelesaian rumusan masalah di bidang pertanian khususnya pada industri Pangan. Kami mengembangkan model Pembelajaran Mesin (Supervised Learning) untuk mengklasifikasikan jenis penyakit pada daun padi berdasarkan data citra. Identifikasi penyakit yang otomatis dan akurat diharapkan dapat membantu memberikan deteksi dini guna menjaga kualitas dan stabilitas hasil panen padi.

## Dataset
* **Sumber Data:** Kaggle 
* **Tautan:** [Rice Leaf Disease - An Images Dataset](https://www.kaggle.com/datasets/alamshihab075/rice-leaf-disease-an-images-dataset)
* **Deskripsi Singkat:** Dataset terdiri dari sekitar 29.000+ citra daun padi yang terbagi ke dalam 18 kelas penyakit dan kondisi tanaman sehat.

## Algoritma & Teknik Pembelajaran Mesin
Permasalahan yang diselesaikan adalah **Supervised Learning** pada data multimedia (citra). Pendekatan pemodelan yang dikembangkan dalam proyek ini meliputi:
* MobileNetV3 untuk mengekstraks fitur citra
* Random Forest untuk mengklasifikasikan fitur citra daun

## 📂 Struktur Repositori
Berikut adalah susunan direktori dan berkas di dalam repositori ini:

* **`Proposal/`**
  * `Proposal Projek Pembelajaran Mesin Kel 5.pdf` : Dokumen usulan rancangan proyek yang memuat latar belakang, rumusan masalah, dan metodologi.
  * ` Revisi Proposal Projek Pembelajaran Mesin Kel 5.pdf` : Revisi dari dokumen usulan rancangan proyek setelah dilakukan konsultasi bersama dosen.
* **`Progress 1/`**
  * `Laporan Progress Projek Pembelajaran Mesin Kel 5.pdf` : Laporan yang menjelaskan kemajuan pengerjaan proyek sejauh ini.
  * `Progress Projek Pembelajaran Mesin Kel 5.ipynb` : Visualisasi mentah, eksplorasi data , serta *source code* tahapan pra-proses dan uji coba pemodelan.
* **`Laporan Akhir/`**
  * `Laporan Akhir Projek Pembelajaran Mesin Kel 5.pdf` : Laporan akhir proyek yang memuat latar belakang, metodologi, proses pengolahan data, implementasi model, hasil evaluasi, analisis performa, dan kesimpulan penelitian.
  * `Projek Pembelajaran Mesin Final Kel 5.ipynb` : Notebook final yang berisi visualisasi data, proses preprocessing, augmentasi citra, ekstraksi fitur menggunakan MobileNetV3, pelatihan model Random Forest, evaluasi performa, serta analisis hasil klasifikasi.

## Metode
1. Exploratory Data Analysis (EDA) untuk melihat distribusi kelas, mengidentifikasi class imbalance, menampilkan sampel citra, dan untuk memahami karakteristik dataset.
2. Preprocessing yang meliputi tahapan resize citra menjadi 224 × 224 piksel, normalisasi piksel menggunakan preprocess_input MobileNetV3, serta stratified Train-Validation-Test Split
3. Data augmentasi dilakukan pada data latih menggunakan rotation, horizontal flip, zoom, shear, serta brightness adjustment untuk meningkatkan variasi data dan mengurangi overfitting.
4. MobileNetV3 pre-trained ImageNet digunakan sebagai feature extractor. Lapisan klasifikasi dihapus dan output fitur digunakan sebagai representasi numerik citra daun padi.
5. Feature vector hasil ekstraksi MobileNetV3 digunakan sebagai input model Random Forest. Hyperparameter yang digunakan:
   - n_estimators = 200
   - max_depth = 20
   - min_samples_split = 5
   - min_samples_leaf = 2
   - class_weight = balanced
  
## Hasil Evaluasi 
| Metrik | Nilai |
|---------|---------|
| Accuracy | 0.8168 |
| Precision (Macro) | 0.8140 |
| Recall (Macro) | 0.7141 |
| F1-Score (Macro) | 0.7399 |

## Analisis Hasil
Hasil evaluasi menunjukkan bahwa kombinasi MobileNetV3 sebagai feature extractor dan Random Forest sebagai classifier mampu menghasilkan akurasi sebesar 81,68% pada data uji. Nilai Macro F1-Score sebesar 0,7399 menunjukkan bahwa model cukup mampu mengenali seluruh kelas penyakit meskipun terdapat ketidakseimbangan jumlah data pada setiap kelas. Performa terbaik diperoleh pada kelas dengan jumlah sampel yang relatif besar seperti Brown Spot, Bacterial Blight, Tungro, dan Leaf Scald. Sebaliknya, performa pada kelas minoritas seperti Sheath Rot, Stem Rot, dan Ragged Stunt Virus masih lebih rendah karena keterbatasan jumlah data pelatihan.

## Output 
Program menghasilkan beberapa output:
- Random Forest Model (.pkl)
- Confusion Matrix (.png)
- Evaluation Metrics (.png)
- Feature Importance (.csv)
- Prediction Results (.csv)

## Cara Menjalankan
1. Clone repository:
git clone https://github.com/alyanabilatamam/Projek-Machine-Learning
2. Install dependency:
pip install -r requirements.txt
3. Jalankan notebook:
jupyter notebook atau Google Colab
4. Jalankan seluruh cell secara berurutan.

## Kesimpulan
Penelitian ini berhasil mengimplementasikan kombinasi MobileNetV3 sebagai feature extractor dan Random Forest sebagai classifier untuk klasifikasi penyakit daun padi. Model memperoleh Accuracy sebesar 81,68% dan Macro F1-Score sebesar 0,74. Hasil tersebut menunjukkan bahwa pendekatan ekstraksi fitur CNN yang dikombinasikan dengan algoritma ensemble mampu menghasilkan performa klasifikasi yang baik dengan kebutuhan komputasi yang relatif efisien.
