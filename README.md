---

## **Analisis Sentimen dan Klasifikasi Keluhan Pelanggan pada Ulasan Produk Tokopedia Menggunakan IBM Granite**

### **Project Overview**

Proyek ini bertujuan untuk menganalisis ulasan negatif (rating 1 & 2\) dari dataset *Tokopedia Product Reviews* guna mengidentifikasi keluhan utama pelanggan dan memberikan rekomendasi yang dapat ditindaklanjuti (*actionable*) kepada para penjual atau produsen di platform tersebut. Dengan memahami akar masalah dari ketidakpuasan pelanggan, para pelaku bisnis dapat melakukan perbaikan yang terarah pada produk dan layanan mereka. Proses analisis ini memanfaatkan model *Large Language Model* (LLM) **IBM Granite** untuk melakukan **klasifikasi keluhan** ke dalam kategori-kategori spesifik dan **meringkas** ribuan ulasan menjadi poin-poin masalah yang mudah dipahami, sehingga mempercepat proses pengambilan keputusan bisnis.

---

### **Insight & Findings (Temuan & Wawasan)**

Setelah melakukan analisis terhadap 100 sampel ulasan negatif, ditemukan pola keluhan yang signifikan sebagai berikut:

1. **Dominasi Masalah Kualitas Produk**: Sebagian besar keluhan pelanggan (lebih dari 40%) berpusat pada **kualitas produk yang buruk**. Ringkasan dari AI menunjukkan bahwa masalah spesifik di kategori ini meliputi:  
   * **Barang tidak berfungsi sebagaimana mestinya**: Contohnya, staples yang tidak bisa digunakan atau sepatu dengan ukuran sisi kiri dan kanan yang berbeda.  
   * **Barang cacat atau rusak saat diterima**: Pelanggan menerima produk yang sudah rusak bahkan sebelum dibuka, yang menimbulkan kekecewaan tambahan karena proses pengembalian yang rumit.  
   * **Kualitas bahan yang jelek**: Ulasan sering menyebutkan bahwa bahan produk tidak kokoh dan mudah rusak.  
2. **Ketidaksesuaian Produk dengan Deskripsi**: Kategori keluhan terbesar kedua adalah **produk yang tidak sesuai dengan deskripsi** yang ditampilkan di halaman penjualan (sekitar 30%). Temuan utama di area ini adalah:  
   * **Perbedaan fisik**: Pelanggan menerima barang yang berbeda dari gambar, baik dari segi model, warna, maupun ukuran.  
   * **Informasi yang menyesatkan**: Deskripsi produk dianggap tidak akurat, seperti klaim fitur atau kelengkapan yang ternyata tidak sesuai saat produk diterima.  
3. **Masalah Terkait Pengiriman dan Pelayanan**: Meskipun bukan keluhan utama, masalah terkait **pengiriman** dan **pelayanan penjual** juga muncul secara konsisten. AI berhasil meringkas keluhan ini menjadi:  
   * **Pengiriman lambat**: Beberapa pelanggan mengeluhkan waktu pengiriman yang sangat lama, bahkan hingga setengah bulan.  
   * **Respons penjual yang buruk**: Penjual dianggap tidak responsif dalam menanggapi keluhan atau pertanyaan terkait status pengiriman.  
   * **Paket tidak lengkap**: Ada laporan mengenai item dalam paket yang tidak lengkap, sehingga produk tidak dapat digunakan.

---

### **Raw dataset link**

https://www.kaggle.com/datasets/farhan999/tokopedia-product-reviews?resource=download

### **Conclusion & Recommendation (Kesimpulan & Rekomendasi)**

#### **Kesimpulan**

Analisis ulasan negatif pelanggan Tokopedia secara jelas menunjukkan bahwa **kualitas produk** dan **akurasi informasi (deskripsi produk)** adalah dua area paling kritis yang menyebabkan ketidakpuasan pelanggan. Masalah ini lebih dominan dibandingkan dengan isu pengiriman atau pelayanan. Ketidaksesuaian antara ekspektasi yang dibangun melalui halaman produk dengan realitas produk yang diterima menjadi sumber utama kekecewaan.

**Rekomendasi**

Berdasarkan kesimpulan di atas, berikut adalah rekomendasi yang dapat ditindaklanjuti untuk para penjual:

1. **Prioritaskan Audit Kualitas Produk**:  
   * **Rekomendasi**: Penjual harus secara rutin melakukan pengecekan kualitas (*quality control*) pada produk mereka, terutama sebelum pengiriman. Pastikan setiap produk berfungsi dengan baik dan tidak memiliki cacat fisik.  
   * **Dampak**: Ini akan secara langsung mengurangi jumlah keluhan terbesar dan meningkatkan kepercayaan pelanggan.  
2. **Tingkatkan Akurasi Deskripsi dan Visual Produk**:  
   * **Rekomendasi**: Gunakan foto produk asli (*real picture*) dan tulis deskripsi yang jujur serta detail, mencakup informasi bahan, ukuran (dengan panduan yang jelas), dan kelengkapan paket. Hindari informasi yang berpotensi menyesatkan.  
   * **Dampak**: Mengatur ekspektasi pelanggan dengan benar akan menurunkan angka pengembalian barang dan ulasan negatif terkait ketidaksesuaian.  
3. **Perbaiki Standar Pengemasan dan Komunikasi**:  
   * **Rekomendasi**: Meskipun pengiriman cepat, gunakan kemasan yang lebih aman untuk mencegah kerusakan selama transit. Selain itu, tingkatkan responsivitas dalam berkomunikasi dengan pelanggan, terutama jika ada kendala.  
   * **Dampak**: Meningkatkan pengalaman pelanggan secara keseluruhan dan menunjukkan profesionalisme penjual.

---

### **AI Support Explanation (Penjelasan Dukungan AI)**

Dalam proyek ini, **IBM Granite (model ibm-granite/granite-3.3-8b-instruct)** digunakan melalui platform **Replicate** dengan bantuan pustaka **LangChain** untuk dua tugas utama:

1. **Klasifikasi Teks**: Model LLM diberikan *prompt* yang berisi sebuah ulasan pelanggan beserta daftar kategori keluhan yang telah ditentukan (misalnya, "Kualitas Produk", "Pengiriman"). Model kemudian bertugas untuk **mengklasifikasikan** ulasan tersebut ke dalam salah satu kategori yang paling relevan. Kemampuan ini memungkinkan analisis ribuan ulasan secara otomatis dan konsisten.  
2. **Summarization (Peringkasan)**: Setelah ulasan dikelompokkan berdasarkan kategori keluhannya, model LLM diberikan *prompt* untuk **meringkas** kumpulan ulasan dalam setiap kategori menjadi 2-3 poin masalah utama. Ini sangat membantu dalam mengekstrak *insight* secara cepat tanpa harus membaca semua ulasan secara manual.

Penggunaan AI secara signifikan **mempercepat proses analisis** dan **meningkatkan kualitas wawasan** dengan mengubah data teks tidak terstruktur menjadi informasi yang terstruktur dan mudah ditindaklanjuti.
