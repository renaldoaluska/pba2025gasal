# 📊 Analisis Sentimen Ulasan Aplikasi TransJogja

Repositori ini berisi proyek analisis sentimen terhadap ulasan pengguna aplikasi **TransJogja** yang diambil dari Google Play Store. Proyek ini mencakup seluruh alur kerja, mulai dari pengumpulan data (*scraping*), pemrosesan awal teks (*preprocessing*), pelabelan, hingga analisis data eksploratif (EDA) untuk mendapatkan wawasan mendalam dari ulasan pengguna.

---

### 👨‍💻 Data Diri
* **Nama:** Alfa Renaldo Aluska
* **NRP:** 5026221144
* **Mata Kuliah:** Pengolahan Bahasa Alami (A) Gasal 2025
* **Program Studi:** S1 Sistem Informasi
* **Institusi:** Institut Teknologi Sepuluh Nopember (ITS)

---

### 📂 Struktur Repositori

Repositori ini diatur ke dalam beberapa file berdasarkan tahapan pengerjaan:

* `1-TransJogja_Scraping.ipynb`: Kode Python khusus untuk proses scraping data ulasan Trans Jogja (menghasilkan `df_transjog_raw.csv`).
* `2-TransJogja_Praproses.ipynb`: Kode Python untuk text preprocessing atau pembersihan teks (mengambil `df_transjog_raw.csv` dan menghasilkan `df_transjog_clean.csv`).
* `3-TransJogja_Labelling-BOW-TFIDF.ipynb`: Kode Python untuk memberi label sentimen, feature extraction (BoW), dan feature weighting (TF-IDF). (menghasilkan `df_transjog_clean_label.csv`).
* `4-TransJogja_EDA-Sentiment.ipynb`: Kode Python untuk Exploratory Data Analysis (EDA) dan analisis sentimen (menggunakan `df_transjog_clean_label.csv`).
* `df_transjog_raw.csv`: Dataset mentah hasil scraping dari notebook #1.
* `df_transjog_clean.csv`: Dataset bersih hasil pemrosesan dari notebook #2.
* `df_transjog_clean_label.csv`: Dataset bersih yang telah diberi label dari notebook #3.
* `README.md`: File dokumentasi atau penjelasan ringkas tentang proyek.

---

### 📓 Notebooks
Berikut adalah penjelasan dan tautan pratinjau (*preview*) untuk setiap Jupyter Notebook dalam proyek ini.

* **1. Pengumpulan Data (Scraping)**
    * **File**: [`1-TransJogja_Scraping.ipynb`](https://github.com/renaldoaluska/pba2025gasal/blob/main/1-TransJogja_Scraping.ipynb)
    * **Deskripsi**: Notebook ini bertanggung jawab untuk tahap paling awal proyek, yaitu mengambil data ulasan Trans Jogja langsung dari Google Play Store. Hasil dari notebook ini adalah dataset mentah (`df_transjog_raw.csv`).

* **2. Pembersihan Data (Preprocessing)**
    * **File**: [`2-TransJogja_Praproses.ipynb`](https://github.com/renaldoaluska/pba2025gasal/blob/main/2-TransJogja_Praproses.ipynb)
    * **Deskripsi**: Notebook ini mengambil data mentah dari tahap #1 dan fokus pada pembersihan teks (*text preprocessing*). Proses ini mencakup serangkaian langkah seperti *case folding*, normalisasi kata (kamus slang), penghapusan *stopwords*, emoji, dan tanda baca. Output-nya adalah `df_transjog_clean.csv`.

* **3. Pelabelan Sentimen dan Ekstraksi Fitur**
    * **File**: [`3-TransJogja_Labelling-BOW-TFIDF.ipynb`](https://github.com/renaldoaluska/pba2025gasal/blob/main/3-TransJogja_Labelling-BOW-TFIDF.ipynb)
    * **Deskripsi**: Notebook ini mengambil data bersih dari tahap #2 untuk diberi label sentimen (positif, negatif, netral) berdasarkan skor ulasan. Setelah itu, dilakukan transformasi teks menjadi fitur numerik menggunakan metode Bag-of-Words (BoW) dan TF-IDF. Hasilnya adalah `df_transjog_clean_label.csv`.

* **4. Analisis Data Eksploratif (EDA) dan Visualisasi**
    * **File**: [`4-TransJogja_EDA-Sentiment.ipynb`](https://github.com/renaldoaluska/pba2025gasal/blob/main/4-TransJogja_EDA-Sentiment.ipynb)
    * **Deskripsi**: Notebook ini menggunakan dataset bersih yang telah dilabel (`df_transjog_clean_label.csv`) untuk melakukan analisis eksploratif dan visualisasi sentimen ulasan. Analisis mencakup distribusi label, frekuensi kata, *word cloud*, bigram, serta identifikasi kata unik per label. Selain itu, digunakan representasi TF-IDF dan reduksi dimensi PCA untuk menampilkan kluster sentimen dalam ruang 2D, diakhiri dengan rekap *insight* ringkas sebagai penutup.
  
---

### ⏳ Alur Kerja Proyek

Proyek ini dibagi menjadi empat notebook utama yang dijalankan secara berurutan, dari pengumpulan data hingga analisis:

1.  **Pengumpulan Data (Notebook #1: Scraping)**
    * Mengambil ulasan pengguna aplikasi **TransJogja** dari Google Play Store menggunakan teknik *scraping*.
    * Menyimpan data mentah ke dalam file `df_transjog_raw.csv`.

2.  **Pembersihan Data (Notebook #2: Praproses)**
    * Memuat data mentah (`df_transjog_raw.csv`).
    * Melakukan pembersihan teks (*text cleaning*) secara mendalam, seperti *case folding*, normalisasi kata (kamus slang), penghapusan tanda baca, angka, *stopwords*, dan emoji.
    * Menyimpan data yang sudah bersih ke file `df_transjog_clean.csv`.

3.  **Pelabelan Sentimen & Ekstraksi Fitur (Notebook #3: Labelling & Feature)**
    * Memuat data bersih (`df_transjog_clean.csv`).
    * Memberi label sentimen (**Positif**, **Negatif**, **Netral**) berdasarkan skor rating ulasan.
    * Mengubah teks bersih menjadi representasi numerik menggunakan metode **Bag-of-Words (BoW)** dan **TF-IDF**.
    * Menyimpan dataset final (`df_transjog_clean_label.csv`) yang siap untuk dianalisis.

4.  **Analisis Data Eksploratif & Visualisasi (Notebook #4: EDA)**
    * Memuat dataset bersih yang telah dilabel (`df_transjog_clean_label.csv`).
    * Melakukan eksplorasi terhadap distribusi label sentimen dan karakteristik teks (panjang teks, jumlah kata, dsb.).
    * Menampilkan *word cloud* dan analisis *N-gram* (bigram) untuk menemukan kata dan frasa populer di tiap kategori sentimen.
    * Menerapkan representasi **TF-IDF** dan reduksi dimensi **PCA** untuk visualisasi kluster sentimen dalam ruang 2D.
    * Menyimpulkan hasil EDA melalui rekap *insight* sebagai penutup analisis.

---

### 🛠️ Teknologi dan Pustaka yang Digunakan

Proyek ini dibangun menggunakan Python dengan beberapa pustaka utama, antara lain:

* **Pengumpulan Data**: `google-play-scraper`
* **Manipulasi Data**: `pandas`, `numpy`
* **Pemrosesan Teks**: `nltk`, `re`
* **Representasi Fitur**: `scikit-learn` (untuk CountVectorizer dan TfidfVectorizer)
* **Visualisasi Data**: `matplotlib`, `seaborn`, `wordcloud`
