# Analisis Sentimen Layanan Trans Jogja Menggunakan Data Twitter

Repositori ini berisi rangkaian analisis untuk tugas mata kuliah **Pengolahan Bahasa Alami (PBA)**. Proyek ini bertujuan untuk melakukan analisis sentimen terhadap opini publik mengenai layanan bus Trans Jogja berdasarkan data yang dikumpulkan dari platform media sosial Twitter.

---

### 👨‍💻 Data Diri
* **Nama:** Alfa Renaldo Aluska
* **NRP:** 5026221144
* **Mata Kuliah:** Pengolahan Bahasa Alami (A)
* **Program Studi:** S1 Sistem Informasi
* **Institusi:** Institut Teknologi Sepuluh Nopember (ITS)

---

### 📂 Struktur Repositori

Repositori ini diatur ke dalam beberapa folder berdasarkan tahapan pengerjaan:

* `📁 week2/`: Berisi *notebook* untuk proses **pengumpulan data** mentah dari Twitter dan **pembersihan teks** awal.
    * `PBA_Week2.ipynb`: Python code untuk *scraping*.
    * `df_transjog_raw.csv`: Dataset mentah hasil *scraping*.
    * `df_transjog_clean.csv`: Dataset setelah melalui tahap pembersihan teks.
* `📁 week4/`: Berisi *notebook* untuk **analisis data eksploratif (EDA)**, **pelabelan sentimen**, **pemodelan machine learning**, dan **evaluasi**.
    * `1_PBA_Week4.ipynb`: Python code untuk *label sentimen* dan eksplorasi awal.
    * `2_PBA_EDA_Sentiment.ipynb`: Python code untuk EDA dan analisis sentimen*.
    * `df_transjog_clean_label.csv`: Dataset bersih yang telah diberi label sentimen.

---

### 🚀 Alur Kerja Analisis

Analisis dilakukan melalui beberapa tahapan utama yang terdokumentasi dalam *notebook* Jupyter berikut:

#### **1. Pengumpulan dan Pembersihan Data Awal**
* **Notebook:** `PBA_Week2.ipynb`
* **Deskripsi:** Tahap ini fokus pada *scraping* data twit berbahasa Indonesia dengan kata kunci "Trans Jogja". Data mentah yang diperoleh kemudian melalui serangkaian proses *pre-processing* untuk membersihkan teks dari *noise*.
* **Langkah-langkah:**
    * *Web Scraping* data dari Twitter.
    * *Case Folding*: Mengubah seluruh teks menjadi huruf kecil.
    * Pembersihan Teks: Menghapus URL, *mention* (`@username`), *hashtag* (`#`), tanda baca, dan angka.
    * *Tokenization*: Memecah kalimat menjadi token kata.
    * *Stopword Removal*: Menghapus kata-kata umum yang tidak memiliki makna signifikan (misalnya: "yang", "di", "dan").
    * *Stemming*: Mengubah kata ke bentuk dasarnya menggunakan library Sastrawi.

#### **2. Pemodelan Klasifikasi, Evaluasi, dan Tuning**
* **Notebook:** `PBA_Week4.ipynb`
* **Deskripsi:** Tahap ini adalah inti dari analisis, yaitu membangun dan mengevaluasi model *machine learning* untuk mengklasifikasikan sentimen secara otomatis.
* **Langkah-langkah:**
    1.  **Ekstraksi Fitur:** Mengubah data teks menjadi representasi numerik menggunakan metode **TF-IDF**.
    2.  **Pembuatan Model:** Melatih 5 model klasifikasi yang berbeda:
        * Logistic Regression
        * Support Vector Machine (SVM)
        * Naive Bayes
        * Decision Tree
        * Random Forest
    3.  **Evaluasi Model:** Kinerja setiap model diukur menggunakan metrik *Accuracy*, *Precision*, *Recall*, *F1-Score*, dan divisualisasikan dengan *Confusion Matrix*. Model **Random Forest** menunjukkan performa terbaik pada evaluasi awal dengan akurasi **~89%**.
    4.  **Hyperparameter Tuning:** Melakukan optimisasi pada model Random Forest menggunakan **GridSearchCV** untuk menemukan kombinasi parameter terbaik.


#### **3. Analisis Data Eksploratif (EDA) & Visualisasi Sentimen**
* **Notebook:** `2_PBA_EDA_Sentiment.ipynb`
* **Deskripsi:** Setelah data bersih dan dilabeli, dilakukan analisis eksploratif mendalam untuk memahami karakteristik data dan distribusi sentimen.
* **Analisis yang Dilakukan:**
    * 📊 **Distribusi Sentimen:** Visualisasi perbandingan jumlah sentimen positif, negatif, dan netral.
    * 📝 **Analisis Panjang Teks:** Melihat distribusi jumlah kata per twit untuk setiap kategori sentimen.
    * ☁️ **Word Cloud:** Mengidentifikasi kata-kata yang paling dominan pada setiap kategori sentimen.
    * 📊 **Top N-grams:** Menemukan frasa (pasangan kata/bigram) yang paling sering muncul untuk mendapatkan konteks yang lebih baik.
    * 🎨 **Visualisasi Kluster PCA:** Menggunakan *Principal Component Analysis (PCA)* pada fitur TF-IDF untuk memvisualisasikan pengelompokan sentimen dalam ruang 2D.
---

### 📈 Hasil Akhir

Setelah melalui proses *hyperparameter tuning*, model **Random Forest** berhasil mencapai performa yang lebih optimal dengan **akurasi sekitar 90.3%** pada data uji. Hal ini menunjukkan bahwa model tersebut cukup andal dalam mengklasifikasikan sentimen publik terhadap layanan Trans Jogja berdasarkan data teks dari Twitter.

---

### 🔗 Pratinjau Notebook

Klik tautan di bawah ini untuk melihat pratinjau kode dan hasil analisis di setiap *notebook* secara langsung di GitHub:

* **[Notebook Minggu 2: Pengumpulan & Pembersihan Data](https://github.com/renaldoaluska/pba2025gasal/blob/main/week2/PBA_Week2.ipynb)**
* **[Notebook Minggu 4: Pemodelan & Evaluasi Klasifikasi](https://github.com/renaldoaluska/pba2025gasal/blob/main/week4/1_PBA_Week4.ipynb)**
* **[Notebook Minggu 4: EDA & Visualisasi Sentimen](https://github.com/renaldoaluska/pba2025gasal/blob/main/week4/2_PBA_EDA_Sentiment.ipynb)**

---

### 🛠️ Teknologi yang Digunakan

* **Bahasa Pemrograman:** Python 3
* **Library Utama:**
    * `pandas` & `numpy` untuk manipulasi data.
    * `snscrape` untuk pengumpulan data Twitter.
    * `nltk` & `sastrawi` untuk prapemrosesan teks.
    * `scikit-learn` untuk ekstraksi fitur, pemodelan, dan evaluasi.
    * `matplotlib` & `seaborn` untuk visualisasi data.
    * `wordcloud` untuk membuat visualisasi *word cloud*.
