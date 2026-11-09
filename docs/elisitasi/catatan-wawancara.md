# Catatan Wawancara — Sistem Informasi Stok dan Penjualan Toko Bangunan

- **Pewawancara / Pencatat:** Muhammad Rapianur (Pewawancara Utama) & Rekan Tim (Pencatat).
- **Subjek Proyek:** Sistem Informasi Pengelolaan Stok, Transaksi Kasir, dan Piutang Toko Bangunan di Sampit.

---

## Bagian 1: Catatan Simulasi Wawancara (Langkah 6 & 7 — Persona 1 Toko Bangunan)

- **Tanggal / Lokasi:** 04 November 2026 / Laboratorium Komputer D3 TI Politeknik Sampit.
- **Narasumber Simulasi:** Toko Bangunan "Maju Jaya" (Ibu Rahma - Pemilik, Kasir K, Staf Gudang G).

### Tabel Catatan Sesi Simulasi

| No | Pertanyaan | Jawaban Ringkas Narasumber | Fakta / Asumsi | Perlu Konfirmasi? |
|:--:|------------|----------------------------|:--------------:|:-----------------:|
| 1 | Bagaimana pencatatan stok barang gudang dilakukan saat ini? | Barang masuk dan sisa stok dicatat di buku tulis besar oleh pegawai gudang. Hampir tiap akhir bulan jumlah catatan di buku selisih dengan hitungan fisik semen dan cat di rak. | **Fakta** | Tidak (Sudah dicek fisik buku) |
| 2 | Berapa banyak variasi produk yang dijual dan bagaimana penetapan harganya? | Ada sekitar 150 jenis material (semen, cat, pipa, paku, seng). Harga kulakan dari distributor dan harga jual ke pembeli bisa naik-turun hampir setiap minggu. | **Fakta** | Tidak |
| 3 | Bagaimana pencatatan transaksi di meja kasir dan koordinasi ke gudang? | Kasir menulis penjualan di buku nota kertas rangkap dua (putih untuk pembeli, merah untuk toko). Pegawai gudang sering tidak tahu barang apa saja yang baru terjual sehingga terlambat mengurangi stok. | **Fakta** | Tidak |
| 4 | Bagaimana alur pembelian dengan tempo bagi kontraktor langganan? | Beberapa kontraktor kecil diperbolehkan mengambil barang dengan tempo pembayaran dua minggu. Catatan utang ditulis di buku terpisah dan sering terlewat untuk ditagih jika tidak dicek satu-satu. | **Fakta** | Tidak |
| 5 | Laporan berkala apa yang paling dibutuhkan oleh pemilik toko? | Pemilik toko (Ibu R) ingin memeriksa setiap hari Sabtu sore: daftar barang apa yang paling banyak laku dan barang apa saja yang stoknya sudah hampir habis agar bisa segera kulakan ulang. | **Fakta** | Tidak |
| 6 | Bagaimana kondisi infrastruktur listrik dan koneksi internet di lokasi toko? | Aliran listrik dari PLN cukup sering padam bergilir, dan koneksi internet di dalam area gudang/toko sering lambat atau hilang sinyal sama sekali. | **Fakta** | Perlu konfirmasi durasi rata-rata pemadaman |
| 7 | Bagaimana kebiasaan dan kemampuan staf dalam memakai perangkat komputer? | Kasir dan staf gudang sudah berumur dan tidak terbiasa memakai aplikasi rumit. Pemilik meminta antarmuka yang sangat simpel, tidak banyak tombol menu, dan tulisan/font harus berukuran besar agar jelas dibaca. | **Fakta** | Perlu konfirmasi ukuran font minimal |
| 8 | Berapa anggaran dan apa saja perangkat keras yang tersedia di toko? | Anggaran toko terbatas, tidak bersedia membayar biaya langganan bulanan software (*SaaS*). Perangkat yang ada saat ini hanya satu unit laptop kantor lama dan satu buah handphone Android milik Ibu R. | **Fakta** | Tidak |
| 9 | Apakah kontraktor sering melunasi utang sebagian (mencicil) atau sekaligus lunas? | Sebagian kontraktor membayar lunas sekaligus dalam 2 minggu, namun ada yang mencicil separuh dulu saat termin proyek cair. | **Asumsi** | Ya (dikonfirmasi pada wawancara nyata) |
| 10 | Apakah ada batasan minimum stok yang seragam untuk semua barang? | Dugaan awal tiap barang minimal sisa 5 unit, namun untuk material seperti semen batas amannya adalah 20 sak, sedangkan cat oplos cukup 2 kaleng. | **Asumsi** | Ya (dikonfirmasi pada wawancara nyata) |

### Refleksi Hasil Simulasi (3 Kalimat Refleksi Sesuai Langkah 6)
1. Tim pewawancara berhasil menggali seluruh 8 fakta tersembunyi dari narasumber melalui pendekatan pertanyaan terbuka yang sistematis tanpa mengarahkan jawaban.
2. Pertanyaan mengenai kendala rekonsiliasi akhir bulan dan alur komunikasi nota rangkap kasir-gudang terbukti menjadi pertanyaan yang paling produktif dalam membuka akar masalah selisih stok.
3. Pedoman wawancara diperbaiki dengan menyisipkan pertanyaan mendalam terkait skema toleransi saat listrik padam serta toleransi cicilan tempo kontraktor.

### Analisis Kebutuhan dari Catatan Simulasi (Langkah 7)

| No | Pernyataan dari Catatan | Jenis | Kebutuhan di Baliknya (Bebas dari Istilah Teknologi) |
|:--:|-------------------------|:-----:|------------------------------------------------------|
| 1 | "Saya ingin aplikasi di ponsel agar bisa cek stok dari mana saja." | **Solusi** | Pemilik toko membutuhkan akses data ringkasan stok secara praktis tanpa harus selalu datang langsung ke meja kasir. |
| 2 | "Hampir tiap akhir bulan jumlah di buku berbeda dengan jumlah fisik." | **Fakta** | Sistem memerlukan mekanisme pencatatan stok keluar-masuk secara terpusat serta fitur penyesuaian (*stok opname*) yang mencatat alasan selisih. |
| 3 | "Kasir mencatat pada nota rangkap, gudang tidak tahu barang apa yang baru terjual." | **Fakta** | Data penjualan kasir harus secara otomatis dan langsung memotong kuantitas stok barang tanpa memerlukan komunikasi manual antar-staf. |
| 4 | "Buatkan tombol scan barcode canggih untuk 150 barang kami." | **Solusi** | Kasir membutuhkan cara cepat untuk mencari dan memilih barang saat transaksi penjualan ramai tanpa risiko salah memasukkan nama produk. |
| 5 | "Piutang kontraktor dicatat di buku terpisah dan sering terlupa ditagih." | **Fakta** | Pengelola toko memerlukan sistem pengingat visual (*warning indicator*) untuk setiap nota tempo yang telah mendekati atau melewati batas waktu 14 hari. |
| 6 | "Saya ingin tahu setiap Sabtu: barang terlaris dan barang yang stoknya hampir habis." | **Kebutuhan** | Pemilik toko memerlukan laporan ringkas berkala mingguan yang menampilkan produk dengan penjualan tertinggi serta daftar produk di bawah batas aman untuk pengadaan ulang. |
| 7 | "Pegawai tidak terbiasa dengan komputer; tampilan harus sederhana dengan tulisan besar." | **Kebutuhan** | Antarmuka pengguna harus memiliki keterbacaan tinggi, ukuran font besar, kontras visual jelas, dan alur langkah kerja yang seminimal mungkin. |
| 8 | "Listrik sering padam dan internet toko tidak stabil; kami tidak mau langganan bulanan." | **Fakta** | Aplikasi harus dapat dioperasikan secara lokal (*offline-first* di jaringan lokal), ringan untuk laptop spesifikasi lama, dan bebas biaya berlangganan berkala. |

---

## Bagian 2: Catatan Wawancara Klien Nyata di Lapangan (Langkah 11 & Langkah 12)

- **Tanggal / Waktu:** Sabtu, 07 November 2026, Pukul 14.00 – 14.45 WIB.
- **Lokasi:** Toko Bahan Bangunan di Jl. Tjilik Riwut Km 3, Baamang Tengah, Sampit.
- **Narasumber (Disamarkan):** Bapak H (Pemilik Usaha Toko Bangunan) dan Mas D (Kasir & Pengawas Muatan Barang).
- **Status Etika:** Izin lisan dan tertulis disetujui; nama pribadi, nomor kontak, dan omzet keuangan riil disamarkan.

### Catatan Hasil Wawancara Nyata Lapangan

| No | Topik / Pertanyaan | Hasil Catatan Lapangan (Jawaban Narasumber) | Fakta / Asumsi | Status Verifikasi |
|:--:|--------------------|--------------------------------------------|:--------------:|:-----------------:|
| 1 | Alur barang masuk dari distributor | Pemasok semen (Gresik, Conch) datang 1–2 kali seminggu membawa Surat Jalan. Mas D memeriksa fisik sak semen apakah ada yang sobek/mengeras, lalu menandatangani surat jalan dan menyalin jumlahnya ke buku stok gudang. | **Fakta** | Terverifikasi (Melihat fisik buku gudang) |
| 2 | Kendala selisih stok semen dan cat | Semen sering bocor saat bongkar muat dan cat kemasan kaleng terkadang rembes atau tertukar kode warna saat pembeli membatalkan pesanan di gudang. Akibatnya stok buku gudang sering lebih banyak daripada semen utuh yang tersisa di palet. | **Fakta** | Terverifikasi |
| 3 | Alur transaksi penjualan harian | Kasir menulis nota rangkap tiga: lembar 1 (putih) untuk pembeli, lembar 2 (merah) untuk arsip kasir, dan lembar 3 (kuning) diserahkan ke kuli panggul/gudang untuk pengeluaran barang. Jika toko ramai, lembar kuning sering menumpuk dan baru dicek sore hari. | **Fakta** | Terverifikasi (Melihat nota fisik) |
| 4 | Alur pembelian tempo kontraktor | Kontraktor langganan (sekitar 6–8 orang) sering menelepon atau mengutus tukangnya mengambil barang proyek. Nota ditulis tempo (maksimal 14 hari) dan diselipkan di papan jepit (*clipboard*). Sering terjadi tukang yang mengambil berbeda-beda orang sehingga kontraktor sempat lupa rincian barangnya. | **Fakta** | Terverifikasi |
| 5 | Skema pelunasan piutang tempo | Kontraktor hampir tidak pernah membayar persis lunas sekaligus jika proyek masih berjalan. Mereka biasanya menyetor uang cicilan Rp500.000 atau Rp1.000.000 setiap menerima termin dari pemilik rumah, lalu kasir menuliskan sisa saldo di lembar nota bon tersebut. | **Fakta** | Terverifikasi (Memvalidasi Asumsi Simulasi No. 9) |
| 6 | Penentuan stok minimum (*safety stock*) | Batas aman berbeda-beda: Semen minimal 25 sak (karena pengiriman butuh 2 hari), Besi beton minimal 40 batang, sedangkan paku dan kawat bendrat minimal 2 dus. | **Fakta** | Terverifikasi (Memvalidasi Asumsi Simulasi No. 10) |
| 7 | Perubahan harga bahan bangunan | Harga semen dan besi naik-turun mengikuti harga distributor Banjarmasin. Bapak H biasanya menerima daftar harga baru via WhatsApp setiap hari Senin pagi dan mencatat harga jual baru di selembar kertas memo di meja kasir. | **Fakta** | Terverifikasi |
| 8 | Laporan mingguan yang diinginkan | Pemilik toko membutuhkan rekapitulasi setiap Sabtu sore: berapa sak semen terjual, berapa total bon tempo yang belum dibayar dan sudah lewat 2 minggu, serta daftar barang apa yang perlu diorder ke distributor pada Senin pagi. | **Fakta** | Terverifikasi |
| 9 | Kondisi operasional komputer & listrik | Laptop kasir adalah laptop lama (Asus RAM 4GB, Core i3 generasi awal). Listrik kadang padam 1–2 jam saat hujan deras. Aplikasi harus bisa jalan offline di laptop kasir tanpa koneksi internet luar. | **Fakta** | Terverifikasi |
| 10 | Preferensi tampilan oleh staf | Mas D menyatakan: "Yang penting kalau ada pembeli ramai, cari nama barangnya cepat, hurufnya besar-besar, dan total harga otomatis muncul tanpa harus hitung pakai kalkulator lagi." | **Fakta** | Terverifikasi |

---

### Hasil Studi Dokumen Lapangan (Langkah 12)
1. **Buku Nota Rangkap Tiga:** Berisi kolom Tanggal, Nama Pelanggan/Tukang, Nama Barang, Satuan, Kuantitas, Harga Satuan, dan Jumlah. Terdapat cap stempel "LUNAS" (tinta merah) atau "TEMPO ... HARI" (tinta biru).
2. **Buku Bon Gantung Piutang:** Memuat nama kontraktor, nomor nota tempo, total tagihan, riwayat cicilan bertanggal, dan sisa utang.
3. **Memo Daftar Harga Mingguan:** Kertas memo tempel berisi daftar harga pokok dan harga eceran terbaru untuk semen, seng gelombang, dan besi beton.

---

### Refleksi Wawancara Nyata Lapangan (3 Kalimat)
1. Wawancara lapangan secara langsung membuktikan bahwa skema pembayaran kontraktor mayoritas berupa cicilan bertahap dan identitas nama pengambil barang (tukang/sopir) wajib tercatat di nota.
2. Penelusuran fisik terhadap buku nota dan bon gantung memberikan gambaran pasti mengenai struktur data transaksi, batas tempo 14 hari, dan kebutuhan konversi satuan material.
3. Kebutuhan operasional toko yang berjalan secara offline-lokal pada satu laptop lama menjadi batasan arsitektur utama yang wajib diakomodasi oleh sistem.
