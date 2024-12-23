# UAS Deep Learning

# Anggota Kelompok
| Nama                     | NPM       |
|------------------------- |-----------|
| Rosalia Dina Marina S    | G1A021017 |
| Esti Asmareta Ayu        | G1A021042 |
| Mira Juwita Ali          | G1A021056 |

# Deskripsi Proyek
Proyek ini bertujuan untuk membangun model peringkasan teks otomatis menggunakan arsitektur Encoder-Decoder yang dilengkapi dengan mekanisme Attention LSTM dan GRU. Model ini dirancang untuk meringkas ulasan yang terdapat pada situs Universitas Bengkulu, memberikan ringkasan yang lebih singkat dan informatif dari ulasan lengkap.

# Dataset
Dataset yang digunakan berisi 200 sampel ulasan dari situs Universitas Bengkulu (unib.ac.id). Dataset terdiri dari:  
**text**     : Ulasan dari situs.  
**summary**  : Ringkasan ulasan.  
![Data Load Dataset]

# Modeling
## Pengolahan Data
**Text Cleaning:**
- Menghapus tag HTML menggunakan **BeautifulSoup**.
- Melakukan tokenisasi teks dan menyaring token yang bukan alfanumerik.
- Menghilangkan *stopwords* untuk memfokuskan pada kata-kata yang bermakna.

**Transformasi Data**:
- Mengonversi teks menjadi urutan bilangan bulat, di mana setiap kata direpresentasikan oleh indeks dalam kosakata.
- Menggunakan **padding** untuk memastikan semua urutan memiliki panjang yang sama dengan menambahkan nol pada urutan yang lebih pendek.

## Arsitektur Model
Arsitektur yang digunakan adalah Encoder-Decoder dengan mekanisme Attention LSTM dan GRU.
**Encoder**              : Memproses urutan input dan menghasilkan context vector.
**Mekanisme Attention**  : Untuk memilih bagian input yang relevan pada setiap langkah decoding.
**Decoder**              : Menghasilkan urutan output secara bertahap, satu kata dalam satu waktu.

## Kompilasi Model
**Loss Function**  : Sparse Categorical Crossentropy
**Optimizer**      : RMSprop
**Metrics**        : Accuracy

## Pelatihan Model
- Model dilatih menggunakan dataset pelatihan dan divalidasi dengan membagi data menjadi bagian validasi.
- EarlyStopping akan digunakan untuk mencegah overfitting.
- Model dilatih selama 100 epoch

# Hasil Pelatihan
Setelah melatih model, didapatkan hasil dari epoch pelatihan terakhir
**accuracy: 0.7661**
**loss: 1.3172**

## Visualisasi Grafik


# Kesimpulan
**Accuracy (0.7661):**
Akurasi menunjukkan bahwa model telah belajar dengan cukup baik untuk mengenali pola dalam data dan dapat digunakan untuk test summarization pada model yang baru dilatih dengan dataset yang terbatas (200 sampel)

**Loss (1.3172):**
Nilai loss sebesar 1.3172 menunjukkan bahwa model masih memiliki kesalahan dalam memprediksi output yang dapat disebabkan oleh ukuran dataset yang kecil (200 sampel).

Model menunjukkan kinerja yang cukup baik dengan akurasi 76.61%. Namun model dapat ditingkatkan akurasi dengan menambahkan ukuran dataset.





