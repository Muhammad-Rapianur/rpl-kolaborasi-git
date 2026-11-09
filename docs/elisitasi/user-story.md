# Daftar User Story — Sistem Informasi Stok dan Penjualan Toko Bangunan "Maju Jaya"

Dokumen ini memuat daftar kebutuhan pengguna yang dirumuskan ke dalam format *User Story* dengan kriteria penerimaan terukur (*Given–When–Then*) yang memenuhi kriteria **INVEST** (*Independent, Negotiable, Valuable, Estimable, Small, Testable*).

---

## US-01: Pencatatan Transaksi Penjualan Tunai
Sebagai **Kasir Toko**,  
saya ingin **mencatat transaksi penjualan barang secara tunai dan mencetak nota**,  
agar **transaksi terekam rapi serta pembeli mendapatkan bukti pembelian yang sah**.

**Kriteria Penerimaan:**
- **Given** kasir memilih barang "Semen Gresik 50kg" sebanyak 3 sak dengan harga @Rp65.000, **When** kasir menekan tombol "Simpan Transaksi", **Then** total penjualan Rp195.000 tersimpan ke riwayat transaksi dan rincian nota siap dicetak.
- **Given** keranjang transaksi masih kosong atau kuantitas barang diisi 0, **When** kasir menekan tombol "Simpan Transaksi", **Then** sistem menolak memproses transaksi dan menampilkan pesan "Pilih minimal 1 barang dengan jumlah valid".

*Sumber: Catatan Wawancara No. 3 [Asumsi: Tidak]*

---

## US-02: Pengurangan Stok Otomatis Saat Transaksi Berhasil
Sebagai **Petugas Gudang**,  
saya ingin **stok barang otomatis berkurang setiap kali kasir menyelesaikan transaksi**,  
agar **saya tidak perlu mencatat manual dari nota kertas kasir untuk mengetahui sisa barang riil**.

**Kriteria Penerimaan:**
- **Given** stok barang "Cat Tembok Putih 5kg" berjumlah 12 ember, **When** kasir menyelesaikan penjualan 4 ember, **Then** jumlah stok barang di sistem seketika menjadi 8 ember.
- **Given** stok barang "Pipa PVC 3/4 inch" tersisa 5 batang, **When** kasir mencoba memasukkan transaksi penjualan 8 batang, **Then** sistem menolak transaksi dengan pesan "Stok tidak mencukupi, sisa stok tersedia: 5 batang" dan jumlah stok awal tidak berubah.

*Sumber: Catatan Wawancara No. 1 & No. 3 [Asumsi: Tidak]*

---

## US-03: Pencatatan Barang Masuk dari Pemasok
Sebagai **Petugas Gudang**,  
saya ingin **menginput data penerimaan barang masuk beserta nomor surat jalan dari pemasok**,  
agar **jumlah stok bertambah secara akurat sesuai kiriman fisik distributor**.

**Kriteria Penerimaan:**
- **Given** stok tercatat "Semen Tiga Roda" adalah 20 sak, **When** petugas gudang menginput barang masuk 50 sak dengan nomor surat jalan "SJ-102", **Then** stok barang di sistem terbarui menjadi 70 sak dan riwayat penerimaan tersimpan.
- **Given** petugas gudang mengisi angka penerimaan dengan nilai negatif (-10) atau bukan angka, **When** tombol simpan ditekan, **Then** sistem menampilkan pesan "Jumlah barang masuk harus berupa angka bulat positif" dan data ditolak.

*Sumber: Catatan Wawancara No. 1 [Asumsi: Tidak]*

---

## US-04: Penyesuaian Stok Fisik Akhir Bulan (Stok Opname)
Sebagai **Petugas Gudang**,  
saya ingin **melakukan penyesuaian (*stok opname*) antara data sistem dan hitungan fisik riil**,  
agar **selisih barang akibat kerusakan, kebocoran, atau susut dapat disesuaikan dengan alasan yang jelas**.

**Kriteria Penerimaan:**
- **Given** stok sistem "Paku Campur 5cm" adalah 15 kg dan hasil timbang fisik adalah 13 kg, **When** petugas gudang memasukkan jumlah fisik 13 kg dan memilih keterangan "Susut timbangan", **Then** stok sistem berubah menjadi 13 kg dan log penyesuaian mencatat selisih -2 kg.
- **Given** petugas gudang mengisi nilai stok fisik baru yang berbeda tanpa mengisi kolom keterangan, **When** formulir dikirim, **Then** sistem mewajibkan pengisian alasan dengan pesan "Keterangan alasan selisih stok wajib diisi".

*Sumber: Catatan Wawancara No. 1 [Asumsi: Tidak]*

---

## US-05: Pembaruan Harga Beli dan Harga Jual Material
Sebagai **Pemilik Toko**,  
saya ingin **memperbarui harga modal (beli) dan harga jual barang secara fleksibel**,  
agar **harga jual selalu mengikuti fluktuasi harga distributor mingguan tanpa menimbulkan kerugian**.

**Kriteria Penerimaan:**
- **Given** harga jual "Besi Beton 10mm" saat ini Rp75.000, **When** pemilik toko memperbarui harga jual menjadi Rp78.000, **Then** transaksi penjualan berikutnya otomatis menggunakan nominal baru Rp78.000.
- **Given** pemilik toko keliru menginput harga jual yang lebih rendah dari harga beli (misal beli Rp70.000, jual diisi Rp65.000), **When** data disimpan, **Then** sistem memunculkan dialog konfirmasi: "Peringatan: Harga jual lebih rendah dari harga modal. Lanjutkan?".

*Sumber: Catatan Wawancara No. 2 [Asumsi: Tidak]*

---

## US-06: Peringatan Stok Kritis (Batas Minimum)
Sebagai **Pemilik Toko**,  
saya ingin **melihat penanda visual untuk produk-produk yang jumlah stoknya sudah menipis**,  
agar **saya dapat segera membuat daftar pesanan barang (*reorder*) sebelum stok habis total**.

**Kriteria Penerimaan:**
- **Given** ambang batas aman "Semen Gresik" disetel 20 sak dan sisa stok adalah 14 sak, **When** pemilik membuka halaman ringkasan stok, **Then** produk tersebut ditandai dengan lencana merah bertuliskan "Stok Kritis (Sisa 14 sak)".
- **Given** stok produk adalah 30 sak dengan ambang batas 20 sak, **When** daftar stok dibuka, **Then** produk tidak memiliki penanda merah dan masuk kategori stok aman.

*Sumber: Catatan Wawancara No. 5 [Asumsi: Tidak]*

---

## US-07: Laporan Mingguan Barang Terlaris Setiap Hari Sabtu
Sebagai **Pemilik Toko**,  
saya ingin **melihat laporan 5 barang dengan volume penjualan tertinggi selama satu minggu**,  
agar **saya dapat merencanakan alokasi modal dan tata letak penyimpanan barang terlaris di akhir pekan**.

**Kriteria Penerimaan:**
- **Given** dalam periode 7 hari terakhir terjual Semen (120 sak), Pipa (40 batang), Cat (15 ember), dan Paku (10 kg), **When** pemilik membuka filter laporan "Minggu Ini", **Then** sistem menampilkan grafik/tabel urutan 1 sampai 4 berdasarkan kuantitas barang paling banyak terjual.
- **Given** tidak ada transaksi penjualan sama sekali pada rentang tanggal yang dipilih, **When** laporan mingguan dipanggil, **Then** halaman menampilkan pesan informatif "Tidak ada data transaksi penjualan pada rentang waktu ini".

*Sumber: Catatan Wawancara No. 5 [Asumsi: Tidak]*

---

## US-08: Pencatatan Transaksi Pembelian Tempo Kontraktor
Sebagai **Kasir Toko**,  
saya ingin **mencatat transaksi pembelian kredit tempo beserta identitas kontraktor dan tanggal jatuh tempo 14 hari**,  
agar **transaksi terdata jelas sebagai piutang toko dan tidak tercampur dengan kas tunai**.

**Kriteria Penerimaan:**
- **Given** kontraktor "Pak Hendra" mengambil material senilai Rp2.500.000 pada 09 November 2026 dengan tempo 14 hari, **When** kasir menyimpan transaksi tempo, **Then** sistem mencatat piutang baru berstatus "Belum Lunas" dengan jatuh tempo otomatis pada 23 November 2026.
- **Given** kasir memilih jenis transaksi tempo namun kolom nama kontraktor dibiarkan kosong, **When** kasir menekan tombol simpan, **Then** sistem menolak dan memunculkan pesan "Nama kontraktor/pelanggan wajib dipilih untuk transaksi tempo".

*Sumber: Catatan Wawancara No. 4 [Asumsi: Tidak]*

---

## US-09: Notifikasi dan Daftar Pantau Piutang Jatuh Tempo
Sebagai **Pemilik Toko**,  
saya ingin **melihat daftar tagihan piutang kontraktor yang mendekati atau telah melewati masa tempo**,  
agar **piutang dapat segera ditagih dan tidak ada uang toko yang macet**.

**Kriteria Penerimaan:**
- **Given** hari ini adalah tanggal 24 November 2026 dan nota piutang senilai Rp2.500.000 jatuh tempo pada 23 November 2026, **When** pemilik membuka menu Piutang, **Then** nota tersebut bertanda merah terang dengan status "Jatuh Tempo (Lewat 1 Hari)".
- **Given** nota piutang jatuh tempo dalam 2 hari ke depan, **When** menu Piutang dibuka, **Then** nota tersebut bertanda kuning "Mendekati Jatuh Tempo (Sisa 2 Hari)".

*Sumber: Catatan Wawancara No. 4 [Asumsi: Tidak]*

---

## US-10: Pencatatan Pembayaran dan Pelunasan Piutang
Sebagai **Kasir Toko**,  
saya ingin **mencatat penerimaan uang pelunasan piutang dari kontraktor**,  
agar **saldo piutang yang bersangkutan berkurang atau dinyatakan lunas**.

**Kriteria Penerimaan:**
- **Given** sisa piutang Kontraktor A pada nota tempo adalah Rp1.500.000, **When** kasir menginput penerimaan pelunasan sebesar Rp1.500.000, **Then** status nota berubah menjadi "Lunas" dan sisa tagihan menjadi Rp0.
- **Given** sisa piutang Kontraktor A adalah Rp1.500.000, **When** kontraktor membayar cicilan awal sebesar Rp700.000, **Then** sisa piutang nota otomatis terbarui menjadi Rp800.000 dengan status "Sebagian".

*Sumber: Catatan Wawancara No. 4 [Asumsi: Ya, terkait opsi cicilan]*

---

## US-11: Pencarian Cepat Data Barang untuk Kasir
Sebagai **Kasir Toko**,  
saya ingin **mencari nama barang dari daftar 150 material dengan mengetikkan beberapa huruf kata kunci**,  
agar **pelayanan kasir tetap cepat saat melayani antrean pembeli di toko**.

**Kriteria Penerimaan:**
- **Given** kasir mengetikkan kata "semen" pada bilah pencarian, **When** tombol ketik direspons sistem, **Then** daftar seketika memfilter dan menampilkan semua varian semen ("Semen Gresik 50kg", "Semen Tiga Roda 50kg", "Semen Putih").
- **Given** kasir mengetikkan nama barang yang tidak dijual di toko seperti "Kabel Listrik", **When** sistem memproses pencarian, **Then** muncul keterangan "Barang tidak ditemukan".

*Sumber: Catatan Wawancara No. 2 [Asumsi: Tidak]*

---

## US-12: Antarmuka Keterbacaan Tinggi dengan Tulisan Besar
Sebagai **Kasir dan Petugas Gudang**,  
saya ingin **antarmuka aplikasi memiliki ukuran font besar (minimal 16px) dan tombol aksi yang jelas**,  
agar **saya yang belum mahir komputer dapat mengoperasikan aplikasi dengan nyaman tanpa takut salah klik**.

**Kriteria Penerimaan:**
- **Given** aplikasi dijalankan pada layar laptop lama kasir (resolusi 1366×768), **When** halaman transaksi dibuka, **Then** teks nama barang dan nominal harga berukuran minimal 16px serta tombol aksi utama memiliki tinggi minimal 44 piksel.
- **Given** pengguna salah menginput data karakter pada kolom angka, **When** tombol ditekan, **Then** peringatan muncul dalam kotak berlatar warna kontras dengan tulisan tebal yang instruksinya mudah dipahami.

*Sumber: Catatan Wawancara No. 7 [Asumsi: Tidak]*

---

## US-13: Pengoperasian Offline Lokal pada Laptop Kasir
Sebagai **Kasir Toko**,  
saya ingin **aplikasi tetap berfungsi normal di localhost tanpa bergantung pada jaringan internet luar**,  
agar **operasional transaksi dan pencatatan stok tidak terhenti saat internet toko mati**.

**Kriteria Penerimaan:**
- **Given** koneksi internet eksternal terputus atau modem toko mati, **When** kasir membuka peramban di `http://127.0.0.1:5000`, **Then** aplikasi tetap terbuka normal dan seluruh proses simpan transaksi berjalan sukses.
- **Given** aplikasi melayani database 150 produk pada laptop berspesifikasi prosesor lama, **When** membuka halaman utama stok, **Then** waktu muat halaman tidak melebihi 2 detik.

*Sumber: Catatan Wawancara No. 6 & No. 8 [Asumsi: Tidak]*

---

## Tinjauan Saran AI terhadap User Story (Langkah 9 Jobsheet 3)

Tabel berikut mendokumentasikan evaluasi tim terhadap saran yang diberikan oleh asisten AI saat peninjauan kriteria INVEST:

| ID Story | Saran dari Asisten AI | Sesuai Kebutuhan Klien? | Kecil dan Teruji? | Keputusan Tim | Alasan Keputusan |
|:--------:|-----------------------|:-----------------------:|:-----------------:|:-------------:|------------------|
| **US-01** | Tambahkan integrasi QRIS dan pembayaran kartu debit bank otomatis pada nota. | Tidak | Tidak | **Tolak** | Toko bangunan "Maju Jaya" hanya melayani transaksi uang tunai (*cash*) dan nota tempo. Menambah pembayaran digital memperbesar cakupan dan membebani biaya. |
| **US-02** | Gunakan scanner barcode nirkabel berkamera untuk memotong stok. | Tidak | Ya | **Ubah** | Klien tidak memiliki alat scanner barcode fisik dan staf gaptek. Fitur diubah menjadi pencarian teks instan yang ramah keyboard. |
| **US-06** | Berikan angka batas aman kuantitatif (*Given-When-Then*) yang berbeda untuk tiap kategori barang (misal semen 20 sak, pipa 5 batang). | Ya | Ya | **Terima** | Saran AI sangat bagus karena kriteria penerimaan menjadi sangat teruji, objektif, dan realistis terhadap kondisi riil toko. |
| **US-09** | Kirim notifikasi pesan SMS/WhatsApp Gateway otomatis ke nomor handphone kontraktor saat jatuh tempo. | Tidak | Tidak | **Tolak** | Klien tidak bersedia membayar biaya langganan API gateway pesan berkala. Cukup penanda visual merah pada layar laptop pemilik toko. |
| **US-10** | Izinkan pencatatan pembayaran tempo secara bertahap (cicilan) dan bukan hanya pelunasan langsung. | Ya | Ya | **Terima** | Sesuai dengan fakta lapangan di mana sebagian kontraktor mencicil saat dana proyek termin cair sebagian. |

