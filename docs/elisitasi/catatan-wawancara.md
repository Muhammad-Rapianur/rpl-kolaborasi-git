# Catatan Wawancara — Sistem Informasi Stok dan Penjualan Toko Bangunan

- **Tanggal / Lokasi:** 04 November 2026 / Meja Administrasi Toko Bangunan "Maju Jaya", Baamang, Sampit.
- **Narasumber:** Pemilik Toko (Ibu R), Kasir Toko (Staf K), Petugas Gudang (Staf G) — *disamarkan*.
- **Pewawancara / Pencatat:** Muhammad Rapianur (Pewawancara), Anggota Tim (Pencatat).

---

## A. Catatan Sesi Wawancara (Berdasarkan Persona 1 & Penggalian Lapangan)

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
| 9 | Apakah kontraktor sering melunasi utang sebagian (mencicil) atau sekaligus lunas? | Sebagian kontraktor membayar lunas sekaligus dalam 2 minggu, namun ada yang mencicil separuh dulu saat termin proyek cair. | **Asumsi** (perlu diverifikasi ke buku piutang) | Ya (perlu dicek kartu piutang) |
| 10 | Apakah ada batasan minimum stok yang seragam untuk semua barang? | Dugaan awal tiap barang minimal sisa 5 unit, namun untuk material seperti semen batas amannya adalah 20 sak, sedangkan cat oplos cukup 2 kaleng. | **Asumsi** | Ya (harus dikonfirmasi ke pemilik) |

---

### Refleksi Hasil Simulasi Wawancara (3 Kalimat Refleksi)
1. Tim pewawancara berhasil menggali seluruh 8 fakta tersembunyi dari narasumber melalui pendekatan pertanyaan terbuka yang sistematis tanpa mengarahkan jawaban.
2. Pertanyaan mengenai kendala rekonsiliasi akhir bulan dan alur komunikasi nota rangkap kasir-gudang terbukti menjadi pertanyaan yang paling produktif dalam membuka akar masalah selisih stok.
3. Pedoman wawancara diperbaiki dengan menyisipkan pertanyaan mendalam terkait skema toleransi saat listrik padam serta toleransi cicilan tempo kontraktor.

---

## B. Analisis: Dari Pernyataan ke Kebutuhan (Membedakan Fakta, Solusi, dan Kebutuhan)

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

## C. Rangkuman Hal yang Perlu Dikonfirmasi Ulang ke Klien

1. **Batas Stok Kritis (Safety Stock):** Mengonfirmasi angka batas minimum per kategori material (misal: semen dalam satuan sak, pipa dalam satuan batang).
2. **Skema Pembayaran Tempo:** Memastikan apakah sistem pencatatan piutang perlu mengakomodasi pembayaran cicilan sebagian atau hanya status lunas/belum lunas.
3. **Format Nomor Nota:** Memastikan apakah toko memiliki format baku penomoran nota manual yang ingin dipertahankan atau diperbolehkan menggunakan penomoran otomatis sistem.

