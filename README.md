# Pemrosesan Bahasa Alami pada Tweet Bencana

## Laporan Proyek

**[https://sugatagh.github.io/dsml/projects/natural-language-processing-with-disaster-tweets/](https://sugatagh.github.io/dsml/projects/natural-language-processing-with-disaster-tweets/)**

## Notebook Kaggle

**[https://www.kaggle.com/sugataghosh/natural-language-processing-with-disaster-tweets](https://www.kaggle.com/sugataghosh/natural-language-processing-with-disaster-tweets)**

## Ringkasan

* Tweet yang berkaitan dengan bencana berpotensi memberikan peringatan dini kepada pihak berwenang agar mereka dapat mengambil tindakan untuk mengurangi kerusakan dan menyelamatkan nyawa.

* Pada proyek ini, kami berupaya memprediksi apakah sebuah tweet menunjukkan adanya bencana nyata atau tidak.

* Dilakukan **analisis eksplorasi data** secara menyeluruh pada dataset.

* Kami mempertimbangkan sejumlah proses **normalisasi teks**, yaitu **konversi huruf menjadi huruf kecil**, **penghapusan spasi berlebih**, **penghapusan tanda baca**, **penghapusan karakter unicode** (termasuk tag **HTML**, **emoji**, dan **URL** yang diawali dengan **http**), **penggantian akronim**, **penggantian bentuk kontraksi kata**, **penghapusan stopwords**, **koreksi ejaan**, **stemming**, **lemmatization**, **penghilangan kata non-alfabet**, serta **retensi kata yang relevan berdasarkan kelas kata (part-of-speech)**.

* Kami menerapkan representasi teks **bag of words** dan memperluas analisis ke **bag of bigrams** serta representasi campuran yang menggabungkan kata dan bigram.

* Selanjutnya, dilakukan representasi teks **TF-IDF**. Seperti sebelumnya, kami melakukan analisis unigram, bigram, dan campuran.

* Terakhir, kami menggunakan embedding **word2vec** untuk representasi teks.

* Untuk setiap pendekatan representasi teks, kami menerapkan sejumlah **algoritma klasifikasi**, yaitu **logistic regression**, **k-nearest neighbors classifier**, **decision tree**, **support vector machine** dengan **radial basis function kernel**, **random forest**, **stochastic gradient descent**, **ridge classifier**, **XGBoost classifier**, dan **AdaBoost classifier**. Kinerja model dibandingkan berdasarkan **nilai rata-rata F1-score** dari **5 pengulangan** **6-fold cross-validation**.

* **Support Vector Machine** dengan **radial basis function kernel** yang bekerja pada data hasil embedding **word2vec** memberikan hasil terbaik berdasarkan nilai rata-rata **F1-score** dari **5 pengulangan** **6-fold cross-validation**, yaitu **0.783204**.

Apakah kamu ingin saya langsung membuatkan file `README.md` baru dalam Bahasa Indonesia?
