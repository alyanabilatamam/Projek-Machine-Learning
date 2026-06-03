## Status Pengerjaan

Saat ini proyek telah menyelesaikan tahap Exploratory Data Analysis (EDA), preprocessing citra, augmentasi data, ekstraksi fitur menggunakan MobileNetV3, serta pelatihan awal model Random Forest. Evaluasi awal telah dilakukan untuk mengetahui performa dasar model sebelum proses optimasi lebih lanjut.

## Hasil Evaluasi Sementara

| Metrik    | Nilai |
| --------- | ----- |
| Accuracy  | 67.8% |
| Precision | 0.75  |
| Recall    | 0.55  |
| F1-Score  | 0.56  |

## Analisis Sementara

Hasil evaluasi awal menunjukkan bahwa kombinasi MobileNetV3 dan Random Forest telah mampu melakukan klasifikasi terhadap 18 kelas penyakit daun padi dengan akurasi sebesar 67,8%. Nilai precision yang relatif tinggi menunjukkan bahwa sebagian besar prediksi model sudah cukup tepat. Namun, nilai recall dan F1-Score masih relatif rendah, yang mengindikasikan bahwa model belum mampu mengenali seluruh kelas secara merata.

Berdasarkan hasil confusion matrix dan classification report, performa model masih dipengaruhi oleh ketidakseimbangan jumlah data pada setiap kelas (class imbalance). Kelas mayoritas seperti Brown Spot, Bacterial Blight, dan Tungro menunjukkan performa yang lebih baik dibandingkan beberapa kelas minoritas seperti Sheath Rot, Bacterial Streak, dan Hispa.

## Rencana Pengembangan Selanjutnya

Tahap berikutnya akan difokuskan pada:

1. Hyperparameter tuning Random Forest.
2. Evaluasi berbagai kombinasi parameter model.
3. Peningkatan performa klasifikasi pada kelas minoritas.
4. Analisis feature importance.
5. Evaluasi akhir menggunakan Accuracy, Precision, Recall, Macro F1-Score, dan Confusion Matrix.

Proyek saat ini masih berada pada tahap pengembangan dan evaluasi awal model, sehingga hasil yang ditampilkan belum merupakan hasil akhir penelitian.

