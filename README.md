# UAS-Deep-Learning
Repositori ini berisi hasil pekerjaan saya untuk UAS Deep Learning. Disini, saya membuat model DistilBert yang dapat mengklasifikasikan teks-teks pada dataset berdasarkan label yang merepresentasikan emosi berdasarkan ekspresi dari teks-teks yang tersedia. Sebelum membuat model, saya melakukan label encoding untuk mengubah data-data pada kolom “label” menjadi numerik. Berikutnya, dilakukan pemisahan menjadi train, test, dan validation dengan bobot 70% untuk training, 15% untuk testing, dan 15% untuk validation. Setelah train test validation split, model DistilBert dibuat menggunakan library keras_nlp untuk membuat processor dengan kodingan berikut:
 
preprocessor = keras_nlp.models.DistilBertPreprocessor.from_preset(
    "distil_bert_base_en_uncased",
    sequence_length = 130
)

Dimana saya menggunakan model dasar DistilBert dengan nilai sequence_length sebesar 130. 

dan model klasifikasi dengan kodingan berikut:

model = keras_nlp.models.DistilBertClassifier.from_preset(
    "distil_bert_base_en_uncased",
    num_classes = 6,
    preprocessor = preprocessor
)

Setelah membuat modelnya, dilakukan pelatihan dan evaluasi terhadap model DistilBert yang telah saya buat. Dengan tujuan untuk melihat nilai akurasi yang dihasilkan dari proses training dan testing dari model tersebut. 

Hasilnya menunjukkan bahwa akurasi training pada epoch terakhir sebesar 0.9664 (96.64%) dan akurasi validasi sebesar 0.9257 (92.57%). Nilai precision yang dihasilkan sebesar 0.912 (91.2%), recall sebesar 0.899 (89.9%), F1-Score sebesar 0.902 (90.2%), dan accuracy sebesar 0.932 (93.2%). Nilai precision yang dihasilkan sebesar 0.912 (91.2%), recall sebesar 0.899 (89.9%), F1-Score sebesar 0.902 (90.2%), dan accuracy sebesar 0.932 (93.2%).

Dari hasil precision, recall, F1-Score, dan accuracy sangat tinggi yang berarti model DistilBERT yang dibuat melakukan kinerja yang baik dalam melakukan klasifikasi. Nilai precision yang tinggi menunjukkan bahwa perolehan nilai yang benar-benar positif yang dilakukan oleh model DistilBERT sangat baik. Nilai recall yang tinggi menunjukkan bahwa model banyak menemukan nilai yang terprediksi positif dengan baik. Nilai F1-Score yang tinggi menunjukkan hubungan precision dan recall sangat seimbang. Nilai accuracy yang tinggi menjadi nilai yang menunjukkan kinerja model yang baik dalam melakukan tugas klasifikasi.
