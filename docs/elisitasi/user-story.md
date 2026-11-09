# Daftar User Story — Sistem Informasi Stok dan Penjualan Toko Bangunan "Maju Jaya"

Dokumen ini memuat daftar kebutuhan pengguna hasil wawancara klien nyata (Langkah 11–13 Jobsheet 3) yang dirumuskan ke dalam format *User Story* dengan kriteria penerimaan terukur (*Given–When–Then*) yang memenuhi kriteria **INVEST** (*Independent, Negotiable, Valuable, Estimable, Small, Testable*).

---

## US-01: Pencatatan Transaksi Penjualan Tunai
Sebagai **Kasir Toko**,  
saya ingin **mencatat transaksi penjualan barang secara tunai dan mencetak nota**,  
agar **transaksi terekam rapi serta pembeli mendapatkan bukti pembelian yang sah**.

**Kriteria Penerimaan:**
- **Given** kasir memilih barang "Semen Gresik 50kg" sebanyak 3 sak dengan harga @Rp68.000, **When** kasir menekan tombol "Simpan Transaksi", **Then** total penjualan Rp204.000 tersimpan ke riwayat transaksi dan rincian nota siap dicetak.
- **Given** keranjang transaksi masih kosong atau kuantitas barang diisi 0, **When** kasir menekan tombol "Simpan Transaksi", **Then** sistem menolak memproses transaksi dan menampilkan pesan "Pilih minimal 1 barang dengan jumlah valid".

*Sumber: Catatan Wawancara Nyata No. 3 [Status: Terkonfirmasi Klien Nyata]*

---

## US-02: Pengurangan Stok Otomatis Saat Transaksi Berhasil
Sebagai **Petugas Gudang**,  
saya ingin **stok barang otomatis berkurang setiap kali kasir menyelesaikan transaksi**,  
agar **saya tidak perlu mencatat manual dari lembar nota kuning kasir untuk mengetahui sisa barang riil**.

**Kriteria Penerimaan:**
- **Given** stok barang "Cat Tembok Putih 5kg" berjumlah 12 ember, **When** kasir menyelesaikan penjualan 4 ember, **Then** jumlah stok barang di sistem seketika terbarui menjadi 8 ember.
- **Given** stok barang "Pipa PVC 3/4 inch" tersisa 5 batang, **When** kasir mencoba memasukkan transaksi penjualan 8 batang, **Then** sistem menolak transaksi dengan pesan "Stok tidak mencukupi, sisa stok tersedia: 5 batang" dan jumlah stok awal tidak berkurang.

*Sumber: Catatan Wawancara Nyata No. 2 & No. 3 [Status: Terkonfirmasi Klien Nyata]*

---

## US-03: Pencatatan Barang Masuk dari Pemasok Beserta Kondisi Fisik
Sebagai **Petugas Gudang**,  
saya ingin **menginput data penerimaan barang masuk dari pemasok beserta nomor surat jalan dan mencatat sak semen yang rusak/pecah**,  
agar **hanya barang dalam kondisi utuh yang masuk sebagai stok siap jual**.

**Kriteria Penerimaan:**
- **Given** kiriman 100 sak Semen Gresik datang dengan nomor SJ "SJ-889" di mana 3 sak bocor/rusak, **When** petugas gudang menginput jumlah masuk 100 dengan catatan rusak 3 sak, **Then** stok siap jual bertambah 97 sak dan 3 sak masuk ke log retur/kerusakan.
- **Given** petugas gudang mengisi angka penerimaan dengan nilai negatif (-10) atau bukan angka, **When** tombol simpan ditekan, **Then** sistem menampilkan pesan "Jumlah barang masuk harus berupa angka bulat positif" dan data ditolak.

*Sumber: Catatan Wawancara Nyata No. 1 & No. 2 [Status: Terkonfirmasi Klien Nyata]*

---

## US-04: Penyesuaian Stok Fisik Akhir Bulan (Stok Opname)
Sebagai **Petugas Gudang**,  
saya ingin **melakukan penyesuaian (*stok opname*) antara data sistem dan hitungan fisik riil**,  
agar **selisih barang akibat susut timbangan atau barang pecah tercatat beserta alasan keterangannya**.

**Kriteria Penerimaan:**
- **Given** stok sistem "Paku Campur 5cm" adalah 15 kg dan hasil timbang fisik adalah 13 kg, **When** petugas gudang memasukkan jumlah fisik 13 kg dan memilih keterangan "Susut timbangan", **Then** stok sistem berubah menjadi 13 kg dan log penyesuaian mencatat selisih -2 kg.
- **Given** petugas gudang mengisi nilai stok fisik baru yang berbeda tanpa mengisi kolom keterangan, **When** formulir dikirim, **Then** sistem mewajibkan pengisian alasan dengan pesan "Keterangan alasan selisih stok wajib diisi".

*Sumber: Catatan Wawancara Nyata No. 2 [Status: Terkonfirmasi Klien Nyata]*

---

## US-05: Pembaruan Harga Modal dan Harga Jual Material
Sebagai **Pemilik Toko**,  
saya ingin **memperbarui harga modal (beli) dan harga eceran barang saat menerima memo harga baru setiap hari Senin**,  
agar **toko tidak merugi akibat kenaikan harga distributor dari Banjarmasin**.

**Kriteria Penerimaan:**
- **Given** harga jual "Besi Beton 10mm" saat ini Rp75.000, **When** pemilik toko memperbarui harga jual menjadi Rp78.000, **Then** transaksi penjualan kasir berikutnya otomatis menggunakan nominal baru Rp78.000.
- **Given** pemilik toko keliru menginput harga jual yang lebih rendah dari harga modal (misal beli Rp70.000, jual diisi Rp65.000), **When** data disimpan, **Then** sistem memunculkan dialog konfirmasi: "Peringatan: Harga jual lebih rendah dari harga modal. Lanjutkan?".

*Sumber: Catatan Wawancara Nyata No. 7 [Status: Terkonfirmasi Klien Nyata]*

---

## US-06: Peringatan Stok Kritis Berdasarkan Batas Minimum Kategori
Sebagai **Pemilik Toko**,  
saya ingin **melihat penanda visual merah untuk material yang stoknya berada di bawah batas aman (semen < 25 sak, besi < 40 batang)**,  
agar **saya dapat segera menghubungi distributor sebelum stok di gudang kosong**.

**Kriteria Penerimaan:**
- **Given** ambang batas aman Semen Gresik disetel 25 sak dan sisa stok adalah 18 sak, **When** pemilik membuka halaman ringkasan stok, **Then** produk tersebut ditandai dengan lencana merah bertuliskan "Stok Kritis (Sisa 18 sak)".
- **Given** sisa stok Besi Beton 10mm adalah 50 batang dengan batas minimum 40 batang, **When** halaman stok dibuka, **Then** produk berstatus normal tanpa penanda merah.

*Sumber: Catatan Wawancara Nyata No. 6 [Status: Terkonfirmasi Klien Nyata]*

---

## US-07: Laporan Mingguan Rekapitulasi Hari Sabtu Sore
Sebagai **Pemilik Toko**,  
saya ingin **melihat laporan ringkasan volume penjualan material tertinggi dan sisa piutang setiap Sabtu sore**,  
agar **saya dapat menyiapkan anggaran kulakan untuk pengiriman hari Senin pagi**.

**Kriteria Penerimaan:**
- **Given** dalam periode 7 hari terakhir terjual Semen (140 sak), Seng (35 lembar), Cat (10 ember), dan Paku (8 kg), **When** pemilik memilih menu "Laporan Mingguan", **Then** sistem menampilkan urutan produk terlaris berdasarkan kuantitas fisik yang terjual.
- **Given** tidak ada transaksi pada filter periode tanggal yang dipilih, **When** laporan dipanggil, **Then** sistem menampilkan pesan informatif "Tidak ada data transaksi pada rentang waktu ini".

*Sumber: Catatan Wawancara Nyata No. 8 [Status: Terkonfirmasi Klien Nyata]*

---

## US-08: Pencatatan Transaksi Tempo Beserta Identitas Mandor/Tukang Pengambil
Sebagai **Kasir Toko**,  
saya ingin **mencatat transaksi tempo 14 hari dengan mencantumkan nama kontraktor penanggung jawab dan nama tukang pengambil barang**,  
agar **kontraktor tidak menyangkal barang yang telah diambil oleh pekerjanya saat ditagih**.

**Kriteria Penerimaan:**
- **Given** tukang "Pak Joko" mengambil barang atas nama kontraktor "Pak Hendra" senilai Rp2.500.000 pada 09 November 2026, **When** kasir menyimpan transaksi tempo, **Then** nota tempo tercatat dengan nama kontraktor "Pak Hendra", pengambil "Pak Joko", status "Belum Lunas", dan jatuh tempo 23 November 2026.
- **Given** kasir memilih jenis transaksi tempo namun kolom nama kontraktor dibiarkan kosong, **When** kasir menekan simpan, **Then** sistem menampilkan validasi "Nama kontraktor wajib dipilih untuk transaksi tempo".

*Sumber: Catatan Wawancara Nyata No. 4 [Status: Terkonfirmasi Klien Nyata]*

---

## US-09: Daftar Pantau dan Penanda Visual Piutang Jatuh Tempo
Sebagai **Pemilik Toko**,  
saya ingin **melihat daftar tagihan bon tempo kontraktor dengan penanda warna kuning (sisa 3 hari) dan merah (lewat jatuh tempo)**,  
agar **staf toko dapat segera menagih sebelum utang menumpuk**.

**Kriteria Penerimaan:**
- **Given** tanggal hari ini adalah 24 November 2026 dan nota tempo jatuh tempo pada 23 November 2026, **When** pemilik membuka menu Piutang, **Then** nota tersebut disorot merah dengan keterangan "Jatuh Tempo (Lewat 1 Hari)".
- **Given** nota piutang jatuh tempo dalam 2 hari ke depan, **When** menu Piutang dibuka, **Then** nota tersebut disorot warna kuning dengan keterangan "Mendekati Jatuh Tempo (Sisa 2 Hari)".

*Sumber: Catatan Wawancara Nyata No. 4 & No. 8 [Status: Terkonfirmasi Klien Nyata]*

---

## US-10: Pencatatan Pembayaran Piutang Bertahap (Cicilan)
Sebagai **Kasir Toko**,  
saya ingin **mencatat pembayaran piutang kontraktor secara bertahap (cicilan) dan mencetak bukti tanda terima sisa utang**,  
agar **saldo piutang terbarui secara transparan sesuai termin pencairan proyek kontraktor**.

**Kriteria Penerimaan:**
- **Given** saldo piutang kontraktor pada nota tempo adalah Rp3.000.000, **When** kontraktor menyetor cicilan Rp1.000.000, **Then** sistem mencatat riwayat cicilan bertanggal, memperbarui sisa utang menjadi Rp2.000.000, dan status nota menjadi "Cicilan Sebagian".
- **Given** sisa piutang adalah Rp1.000.000, **When** kontraktor membayar lunas Rp1.000.000, **Then** status nota otomatis berubah menjadi "Lunas" dan sisa utang menjadi Rp0.

*Sumber: Catatan Wawancara Nyata No. 5 [Status: Terkonfirmasi Klien Nyata]*

---

## US-11: Pencarian Cepat Material Bangunan Ramah Keyboard
Sebagai **Kasir Toko**,  
saya ingin **mencari nama barang dari 150 varian material cukup dengan mengetik 2-3 huruf di keyboard tanpa mouse**,  
agar **saya dapat melayani antrean pembeli dengan sigap tanpa memperlambat pelayanan**.

**Kriteria Penerimaan:**
- **Given** kasir mengetikkan kata "besi" pada kotak input pencarian, **When** sistem merespons, **Then** daftar seketika memfilter seluruh varian besi beton ("Besi Beton 8mm", "Besi Beton 10mm", "Besi Ulir 12mm").
- **Given** kasir mengetikkan nama material yang tidak ada seperti "Keramik Marmer Italia", **When** pencarian diproses, **Then** sistem menampilkan pesan "Material tidak ditemukan".

*Sumber: Catatan Wawancara Nyata No. 10 [Status: Terkonfirmasi Klien Nyata]*

---

## US-12: Antarmuka Keterbacaan Tinggi dengan Font Besar (Minimal 16px)
Sebagai **Kasir dan Petugas Gudang**,  
saya ingin **antarmuka aplikasi memiliki ukuran font minimal 16px, tombol berukuran besar, dan kontras warna yang jelas**,  
agar **staf yang sudah berumur dapat mengoperasikan sistem dengan mudah tanpa kelelahan mata**.

**Kriteria Penerimaan:**
- **Given** aplikasi dibuka pada laptop lama kasir (resolusi layar 1366×768), **When** halaman transaksi atau stok ditampilkan, **Then** seluruh teks nama barang dan angka harga berukuran minimal 16px serta tombol "Simpan" berukuran minimal 44 piksel.
- **Given** staf salah menginput karakter huruf pada kolom angka kuantitas, **When** tombol ditekan, **Then** pesan kesalahan tampil dalam kotak berwarna merah menyala dengan tulisan tebal yang instruksinya jelas.

*Sumber: Catatan Wawancara Nyata No. 10 [Status: Terkonfirmasi Klien Nyata]*

---

## US-13: Pengoperasian Offline Lokal pada Laptop Kasir
Sebagai **Kasir Toko**,  
saya ingin **aplikasi tetap berfungsi normal di localhost tanpa memerlukan koneksi internet eksternal**,  
agar **operasional transaksi penjualan tidak terhambat saat jaringan internet toko mengalami gangguan atau mati**.

**Kriteria Penerimaan:**
- **Given** kabel internet terputus atau sinyal modem toko mati, **When** kasir membuka alamat `http://127.0.0.1:5000` di laptop kasir, **Then** aplikasi tetap terbuka normal dan seluruh proses transaksi penjualan dapat disimpan ke database lokal.
- **Given** aplikasi memuat database 150 produk pada laptop spesifikasi lama (RAM 4GB Core i3), **When** membuka halaman utama stok, **Then** waktu muat halaman tidak melebihi 2 detik.

*Sumber: Catatan Wawancara Nyata No. 9 [Status: Terkonfirmasi Klien Nyata]*

---

## US-14: Cetak Ringkas Lembar Nota Kasir dan Bukti Pengambilan Gudang
Sebagai **Kasir Toko**,  
saya ingin **mencetak format nota ringkas satu halaman yang memuat rincian pembelian dan tanda terima pengambilan gudang**,  
agar **pembeli memiliki bukti bayar dan petugas gudang memiliki acuan serah terima fisik material**.

**Kriteria Penerimaan:**
- **Given** transaksi penjualan tunai atau tempo berhasil disimpan, **When** kasir menekan tombol "Cetak Nota", **Then** peramban menampilkan jendela cetak (*print preview*) dengan format struk/nota bersih tanpa elemen navigasi website yang tidak perlu.
- **Given** nota dicetak untuk transaksi tempo, **Then** pada lembar cetak otomatis tertera cap teks status "TEMPO JATUH TEMPO: [Tanggal]" dan kolom tanda tangan pengambil barang.

*Sumber: Catatan Wawancara Nyata No. 3 & No. 4 [Status: Terkonfirmasi Klien Nyata]*

---

## Tinjauan Saran AI terhadap User Story Klien Nyata (Langkah 9 & 13)

Tabel evaluasi berdasarkan kriteria **INVEST** (*Independent, Negotiable, Valuable, Estimable, Small, Testable*):

| ID Story | Saran dari Asisten AI | Sesuai Kebutuhan Klien? | Kecil dan Teruji? | Keputusan Tim | Alasan Keputusan Rasional |
|:--------:|-----------------------|:-----------------------:|:-----------------:|:-------------:|---------------------------|
| **US-01** | Tambahkan integrasi otomatis QRIS dan pembayaran kartu debit bank. | Tidak | Tidak | **Tolak** | Toko bangunan "Maju Jaya" hanya melayani transaksi uang tunai (*cash*) dan tempo. Menambah pembayaran digital memperluas ruang lingkup dan menambah biaya. |
| **US-03** | Pisahkan pencatatan barang rusak/pecah ke dalam modul log retur terpisah. | Ya | Ya | **Terima** | Temuan nyata membuktikan semen bocor dan cat rembes sering terjadi saat pengiriman, sehingga harus dipisahkan dari stok siap jual. |
| **US-08** | Catat nama tukang/sopir yang mengambil barang selain nama kontraktor penanggung jawab. | Ya | Ya | **Terima** | Temuan nyata membuktikan kontraktor sering lupa rincian barang jika yang mengambil adalah tukang yang berganti-ganti orang. |
| **US-09** | Kirim notifikasi pesan SMS/WhatsApp Gateway otomatis ke nomor handphone kontraktor saat jatuh tempo. | Tidak | Tidak | **Tolak** | Klien menolak biaya langganan API gateway pesan berkala. Cukup penanda visual merah pada layar laptop pemilik toko. |
| **US-10** | Izinkan pencatatan pembayaran tempo secara bertahap (cicilan) dan bukan hanya pelunasan langsung. | Ya | Ya | **Terima** | Sangat sesuai dengan temuan faktual di mana kontraktor mencicil bon tempo mengikuti pencairan termin proyek. |
