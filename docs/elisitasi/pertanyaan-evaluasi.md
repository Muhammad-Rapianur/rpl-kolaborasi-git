# Jawaban Pertanyaan Evaluasi — Jobsheet 3

**Mata Kuliah:** Rekayasa Perangkat Lunak  
**Topik:** Menggali Kebutuhan Klien dan Menulis User Story dengan Bantuan AI  
**Nama Mahasiswa:** Muhammad Rapianur  
**NIM:** 24554010004  
**Kelas:** Sistem Informasi / D3 Teknologi Informasi  

---

### 1. Bedakan kebutuhan dan solusi. Berikan satu contoh dari proyek Anda dan tulis ulang solusi itu sebagai kebutuhan.

- **Perbedaan Mendasar:**
  - **Kebutuhan (*Requirement*):** Merupakan masalah mendasar, kendala operasional, atau tujuan bisnis yang ingin diatasi oleh pengguna/klien (*what and why*). Kebutuhan bersifat independen dari teknologi tertentu.
  - **Solusi (*Solution*):** Merupakan wujud konkret, rancangan fitur, atau implementasi teknis yang dibayangkan untuk menjawab kebutuhan tersebut (*how*). Meloncat langsung ke solusi sebelum memahami kebutuhan berisiko menghasilkan fitur yang rumit, mahal, atau bahkan tidak menyelesaikan akar permasalahan pengguna.

- **Contoh Kasus pada Proyek Toko Bangunan:**
  - **Pernyataan Berupa Solusi:**  
    > *"Saya ingin dibuatkan aplikasi mobile di smartphone berbasis Android agar saya bisa mengecek stok semen kapan saja."*
  - **Ditulis Ulang Sebagai Kebutuhan Murni:**  
    > *"Pemilik toko membutuhkan kemudahan untuk memantau ringkasan sisa stok barang dan status barang yang hampir habis secara cepat dan fleksibel tanpa harus selalu berdiri memeriksa buku catatan di meja kasir."*

---

### 2. Mengapa pertanyaan “Bukankah lebih baik kalau pakai aplikasi?” buruk untuk wawancara? Tulis ulang menjadi pertanyaan yang baik.

- **Mengapa Pertanyaan Ini Buruk:**
  1. **Mengarahkan Jawaban (*Leading Question*):** Pertanyaan ini menyiratkan opini penanya bahwa menggunakan aplikasi pasti lebih unggul, sehingga memicu kecenderungan narasumber untuk sekadar mengiyakan demi bersikap sopan (*acquiescence bias*).
  2. **Pertanyaan Tertutup (*Closed-Ended*):** Narasumber cenderung hanya menjawab *"Ya, boleh"* atau *"Iya, betul"*, tanpa menceritakan bagaimana proses sebenarnya berjalan di lapangan.
  3. **Menutupi Kendala Nyata:** Pertanyaan ini menutup peluang untuk mengungkap fakta penting seperti ketidakmampuan staf dalam mengoperasikan komputer, listrik toko yang sering padam, atau keterbatasan anggaran perangkat.

- **Tulis Ulang Menjadi Pertanyaan yang Baik (Terbuka dan Netral):**
  > *"Bagaimana alur kerja yang Bapak/Ibu lakukan saat ini mulai dari pencatatan barang yang terjual hingga pengecekan sisa stok di gudang, dan kendala apa yang paling sering dihadapi selama proses tersebut?"*

---

### 3. Sebutkan empat teknik elisitasi dan kapan masing-masing paling tepat.

| No | Teknik Elisitasi | Kapan Paling Tepat Digunakan |
|:--:|------------------|------------------------------|
| 1 | **Wawancara (*Interview*)** | Paling tepat digunakan pada tahap awal untuk memahami perspektif mendalam, keluhan, proses kerja, dan harapan pemangku kepentingan utama (seperti pemilik toko dan kasir) melalui komunikasi dua arah yang fleksibel. |
| 2 | **Observasi (*Observation*)** | Paling tepat digunakan untuk melihat cara kerja riil di lapangan secara langsung saat jam sibuk, terutama ketika kebiasaan pengguna berbeda dari apa yang diceritakan atau saat pengguna kesulitan menjabarkan rutinitasnya secara verbal. |
| 3 | **Studi Dokumen (*Document Analysis*)** | Paling tepat digunakan untuk memahami format data eksisting, variabel yang wajib ada, serta aturan pencatatan yang sah melalui pemeriksaan langsung terhadap berkas fisik (misalnya buku nota rangkap 3, buku stok gudang, dan buku bon piutang). |
| 4 | **Kuesioner / Angket (*Questionnaire*)** | Paling tepat digunakan ketika pengembang perlu menjaring data atau umpan balik dari responden dalam jumlah besar dan tersebar geografis secara cepat dengan pertanyaan terstandar yang terukur secara statistik. |

---

### 4. Jelaskan arti huruf I, N, V, E, S, T pada INVEST. Pilih dua huruf dan terapkan pada salah satu user story Anda.

- **Penjelasan Kriteria INVEST:**
  - **I — Independent:** User story sebisa mungkin berdiri sendiri dan tidak memiliki ketergantungan yang kaku dengan story lain, sehingga mudah dijadwalkan dan dikembangkan secara modular.
  - **N — Negotiable:** Story bukanlah kontrak harga mati; detail dan cara implementasinya terbuka untuk didiskusikan dan dinegosiasikan antara pengembang dan klien.
  - **V — Valuable:** Story harus memberikan manfaat nyata (*business value*) yang dapat dirasakan langsung oleh pengguna atau pemilik usaha.
  - **E — Estimable:** Tim pengembang dapat memperkirakan tingkat kerumitan, ukuran, dan durasi pengerjaan story tersebut.
  - **S — Small:** Ukuran story harus cukup kecil dan terfokus sehingga dapat diselesaikan tuntas dalam satu putaran sprint singkat (bukan tugas raksasa/epic).
  - **T — Testable:** Story harus memiliki kriteria keberhasilan yang jelas dan dapat diuji keterpenuhannya secara objektif (*dapat diverifikasi lolos atau gagal*).

- **Penerapan 2 Huruf pada US-02 (Pengurangan Stok Otomatis Saat Penjualan):**
  - **Small (S):** Story US-02 hanya berfokus pada satu fungsionalitas tunggal: *memotong stok barang saat transaksi penjualan kasir selesai*. Story ini tidak melebar ke modul laporan bulanan atau piutang, sehingga beban pengerjaannya terukur dan ringan.
  - **Testable (T):** Story US-02 memiliki kriteria penerimaan kuantitatif yang sangat jelas:  
    *Given stok awal Cat Tembok Putih adalah 12 ember, When kasir menyelesaikan transaksi penjualan 4 ember, Then jumlah stok di sistem seketika menjadi 8 ember.* Skenario ini dapat langsung diuji secara manual maupun otomatis dengan parameter yang pasti.

---

### 5. Mengapa catatan wawancara berisi data pribadi tidak boleh ditempel mentah ke AI? Bagaimana cara memanfaatkan AI dengan aman pada tahap ini?

- **Mengapa Tidak Boleh:**
  Menempelkan data pribadi mentah (seperti nama lengkap pelanggan, nomor telepon, alamat rumah, nomor KTP, atau nominal utang riil) ke asisten AI melanggar etika kejujuran akademik dan regulasi perlindungan data pribadi (*data privacy*). Data yang diunggah ke layanan AI berbasis *cloud* dapat disimpan di peladen pihak ketiga (*server storage*), berisiko terekspos saat terjadi insiden kebocoran data, atau berpotensi dijadikan korpus data pelatihan model generasi berikutnya.

- **Cara Memanfaatkan AI dengan Aman:**
  1. **Anonimisasi dan Samarkan Data (*Anonymization*):** Mengganti nama orang dengan inisial atau label peran (misal: "Bapak H / Pemilik Toko", "Kontraktor A", "Pelanggan 1") serta mengaburkan nominal keuangan sensitif sebelum mengirimkan teks prompt ke AI.
  2. **Gunakan AI Hanya untuk Pola dan Struktur:** Manfaatkan AI untuk merapikan kalimat kebutuhan, menyusun kerangka pertanyaan, mengelompokkan kategori, dan menyusun kriteria *Given–When–Then*, bukan untuk memproses basis data pribadi klien.
  3. **Verifikasi Mandiri:** Perlakukan seluruh tanggapan dan saran AI murni sebagai hipotesis yang wajib dikonfirmasi ulang secara langsung kepada narasumber manusia di lapangan.

