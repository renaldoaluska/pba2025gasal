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

* `1_TransJogja_Scraping-Praproses-Labeling-BoW-TFIDF.ipynb`: Python code scraping, praproses, labeling, BoW, dan TF-IDF.
* `2_PBA_EDA_Sentiment.ipynb`: Python code untuk EDA dan analisis sentimen lanjutan.
* `df_transjog_raw.csv`: Dataset mentah hasil *scraping*.
* `df_transjog_clean.csv`: Dataset setelah melalui tahap pembersihan teks.
* `df_transjog_clean_label.csv`: Dataset bersih yang telah diberi label sentimen.

---

### 📓 Notebooks

Berikut adalah penjelasan dan tautan pratinjau (*preview*) untuk setiap Jupyter Notebook dalam proyek ini.

* **1. Pengumpulan dan Persiapan Data**
    * **File**: [`1_TransJogja_Scraping-Praproses-Labeling-BoW-TFIDF.ipynb`](https://github.com/renaldoaluska/pba2025gasal/blob/main/1_TransJogja_Scraping-Praproses-Labeling-BoW-TFIDF.ipynb)
    * **Deskripsi**: Notebook ini bertanggung jawab untuk tahap awal proyek, yaitu mengambil data ulasan langsung dari Google Play Store. Setelah data terkumpul, dilakukan serangkaian proses pembersihan teks (seperti *case folding* dan penghapusan emoji), pelabelan sentimen berdasarkan skor, dan transformasi teks menjadi fitur numerik menggunakan metode Bag-of-Words (BoW) dan TF-IDF.

* **2. Analisis Data Eksploratif (EDA) dan Visualisasi**  
    * **File**: [`2_TransJogja_EDA_Sentiment.ipynb`](https://github.com/renaldoaluska/pba2025gasal/blob/main/2_TransJogja_EDA_Sentiment.ipynb)  
    * **Deskripsi**: Notebook ini menggunakan dataset hasil pembersihan dari tahap sebelumnya untuk melakukan analisis eksploratif dan visualisasi sentimen ulasan pengguna TransJogja.  
      Analisis mencakup distribusi label sentimen, panjang teks, frekuensi kata, *word cloud*, bigram, serta identifikasi kata unik per label.  
      Selain itu, digunakan representasi *TF-IDF* dan reduksi dimensi *PCA* untuk menampilkan kluster sentimen dalam ruang 2D, diakhiri dengan rekap *insight* ringkas sebagai penutup.

---

### ⏳ Alur Kerja Proyek

Proyek ini terdiri dari dua tahap utama yang dilakukan secara berurutan:

1. **Pengumpulan dan Persiapan Data (Data Collection & Preprocessing)**  
   * Mengambil ulasan pengguna aplikasi **TransJogja** dari Google Play Store menggunakan teknik *web scraping*.  
   * Melakukan pembersihan teks (*text cleaning*) seperti *case folding*, penghapusan tanda baca, angka, dan emoji.  
   * Memberi label sentimen (**Positif**, **Negatif**, **Netral**) berdasarkan skor rating ulasan.  
   * Mengubah teks menjadi representasi numerik menggunakan metode **Bag-of-Words (BoW)** dan **TF-IDF**.  
   * Menyimpan dataset bersih untuk digunakan pada tahap analisis berikutnya.

2. **Analisis Data Eksploratif (Exploratory Data Analysis / EDA) dan Visualisasi**  
   * Memuat dataset bersih hasil tahap pertama.  
   * Melakukan eksplorasi terhadap distribusi label sentimen dan karakteristik teks (panjang teks, jumlah kata, dsb.).  
   * Menampilkan *word cloud* dan analisis *N-gram* (bigram & trigram) untuk menemukan kata dan frasa populer di tiap kategori sentimen.  
   * Mengidentifikasi kata unik khas tiap label serta hubungan antara panjang teks dan label sentimen.  
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
