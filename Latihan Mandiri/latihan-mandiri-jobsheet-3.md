# Latihan Mandiri — Jobsheet 3

## 1. Mengubah Pertanyaan
Mengubah tiga pertanyaan tertutup/mengarahkan menjadi pertanyaan terbuka dan netral:

### Butir 1 (Menghilangkan kesan mengarahkan/subjektif)
- **Sebelum (Mengarahkan & Tertutup):**  
  > "Apakah Ibu merasa pencatatan stok di buku tulis manual itu merepotkan dan sering bikin pusing?"  
  *(Kelemahan: Mengarahkan narasumber untuk mengeluh dengan kata "merepotkan" dan hanya dijawab ya/tidak).*
- **Sesudah (Terbuka & Netral):**  
  > "Bagaimana alur dan pengalaman Bapak/Ibu saat melakukan pencatatan serta pengecekan stok barang di gudang selama ini?"  
  *(Alasan: Netral, tidak menghakimi proses manual, dan memberi keleluasaan bagi narasumber untuk menjelaskan apa adanya).*

### Butir 2 (Menghilangkan bias solusi teknologi)
- **Sebelum (Mengarahkan ke Solusi Aplikasi):**  
  > "Bukankah lebih praktis dan cepat kalau kasir memakai komputer daripada menulis nota rangkap manual?"  
  *(Kelemahan: Menggiring narasumber untuk memuji komputer sebelum masalah sejatinya dipahami).*
- **Sesudah (Terbuka & Netral):**  
  > "Bagaimana langkah-langkah yang dilakukan kasir mulai dari pembeli memesan barang, penulisan nota, hingga barang diambil dari gudang?"  
  *(Alasan: Berfokus pada alur kerja nyata sehingga pewawancara dapat mengamati jeda waktu dan kebiasaan kasir).*

### Butir 3 (Menghilangkan pertanyaan sensitif tertutup)
- **Sebelum (Tertutup Ya/Tidak):**  
  > "Apakah toko ini sering kecolongan piutang kontraktor yang tidak tertagih tepat waktu?"  
  *(Kelemahan: Nada menghakimi, dapat membuat narasumber merasa tersinggung atau defensif).*
- **Sesudah (Terbuka & Netral):**  
  > "Bagaimana prosedur yang berjalan di toko saat ada kontraktor yang membeli barang dengan sistem pembayaran tempo dua minggu?"  
  *(Alasan: Memberi ruang bagi narasumber untuk menceritakan mekanisme bon gantung, pencatatan di buku terpisah, dan kendala penagihannya).*

---

## 2. Peran Berbeda
**Fitur Terpilih:** Pencatatan dan Pengelolaan Transaksi Penjualan Tempo (Piutang Kontraktor)

### A. Peran: Kasir Toko (Fokus Operasional & Pelayanan)
**User Story:**  
Sebagai **Kasir Toko**,  
saya ingin **mencatat transaksi tempo dengan memilih nama kontraktor serta mencantumkan nama tukang yang mengambil barang**,  
agar **transaksi tersimpan cepat dan lembar nota tempo siap dicetak tanpa memperlambat antrean toko**.

**Kriteria Penerimaan (Given–When–Then):**
- **Given** kontraktor "Pak Hendra" mengambil barang dengan tempo 14 hari, **When** kasir memilih opsi "Tempo", menginput nama pengambil "Tukang Joko", dan menekan "Simpan", **Then** sistem menyimpan transaksi dan mencetak nota bertuliskan stempel status "TEMPO JATUH TEMPO 14 HARI" dalam waktu kurang dari 3 detik.
- **Given** kasir memilih opsi bayar "Tempo" namun kolom nama kontraktor dibiarkan kosong, **When** tombol simpan ditekan, **Then** sistem menolak memproses dan menampilkan pesan validasi "Pilih kontraktor terdaftar untuk transaksi tempo".

### B. Peran: Pemilik Toko (Fokus Pengawasan & Risiko Finansial)
**User Story:**  
Sebagai **Pemilik Toko**,  
saya ingin **memantau total akumulasi piutang per kontraktor dan membatasi transaksi jika melebihi batas batas kredit (plafon)**,  
agar **toko terhindar dari risiko kredit macet dan saya dapat mengontrol arus kas usaha**.

**Kriteria Penerimaan (Given–When–Then):**
- **Given** kontraktor "Pak Hendra" memiliki piutang berjalan Rp8.500.000 dengan plafon kredit Rp10.000.000, **When** kasir mencoba memasukkan transaksi tempo baru senilai Rp2.000.000 (total menjadi Rp10.500.000), **Then** sistem menolak transaksi dan menampilkan pesan "Transaksi melebihi batas plafon kredit Rp10.000.000; hubungi Pemilik Toko".
- **Given** terdapat nota tempo kontraktor yang belum dibayar dan sudah melewati batas waktu 14 hari, **When** pemilik membuka halaman ringkasan piutang, **Then** sistem menandai nota tersebut dengan baris warna merah menyala bertuliskan "Lewat Jatuh Tempo".

### Apa yang Berubah pada Kriteria Penerimaannya?
- **Sudut Pandang Kasir:** Kriteria penerimaan berorientasi pada kecepatan aksi input data (*usability*), kelengkapan identitas fisik pengambil barang di nota, dan kelancaran proses cetak struk di meja kasir.
- **Sudut Pandang Pemilik:** Kriteria penerimaan berorientasi pada keamanan bisnis dan mitigasi risiko (*business logic & control*), seperti validasi batas pagu kredit (*credit limit*), akumulasi saldo piutang, dan penanda visual keterlambatan pembayaran (*warning overdue*).

---

## 3. Mengkritik AI

### Simulasi 5 User Story Buatan AI (Tanpa Diberi Catatan Wawancara):
1. **US-AI-01:** Sebagai pelanggan, saya ingin membeli material bangunan secara online melalui katalog website dan membayar via e-wallet (GoPay/OVO) agar barang langsung dikirim.
2. **US-AI-02:** Sebagai staf gudang, saya ingin memindai barcode tiap sak semen menggunakan alat scanner nirkabel agar stok terpotong instan.
3. **US-AI-03:** Sebagai manajer logistik, saya ingin sistem otomatis membuat Purchase Order (PO) otomatis dan mengirim email ke pabrik semen saat stok menipis.
4. **US-AI-04:** Sebagai kasir, saya ingin mencatat penjualan barang dan memotong stok barang secara otomatis agar catatan stok di sistem selalu akurat.
5. **US-AI-05:** Sebagai akuntan toko, saya ingin aplikasi menghitung faktur pajak PPN 11% dan menghasilkan laporan laba rugi komprehensif bulanan.

### Analisis Perbandingan:
#### Yang Sesuai Kebutuhan Klien:
- **US-AI-04 (Pencatatan kasir & potong stok):** Ini adalah satu-satunya kebutuhan inti toko bangunan yang tepat sasaran dengan alur toko di Sampit.

#### Yang Karangan / Halusinasi AI (Tidak Sesuai Realitas Klien):
- **US-AI-01 (Katalog E-commerce & E-wallet):** Klien di Sampit melayani pembeli lokal secara tunai (*cash*) atau bon tempo kontraktor, bukan e-commerce online.
- **US-AI-02 (Scanner Barcode):** Material bangunan (semen, pasir, batu, besi) tidak memiliki stiker barcode eceran, dan toko tidak memiliki alat scanner barcode.
- **US-AI-03 (Auto-PO ke Pabrik):** Toko memesan barang secara manual via telepon/WhatsApp ke distributor Banjarmasin setelah memeriksa gudang setiap hari Sabtu sore.
- **US-AI-05 (Faktur Pajak & Akuntansi Kompleks):** Toko bangunan berskala UMKM keluarga; tidak memiliki staf akuntan khusus dan hanya membutuhkan rekap omzet mingguan serta daftar bon piutang sederhana.

### Kesimpulan dalam Tiga Kalimat (Sesuai Syarat Soal):
1. Tanpa catatan wawancara nyata, AI cenderung berhalusinasi mengasumsikan klien sebagai korporasi ritel modern dengan menambahkan fitur e-commerce, pemindai barcode, dan perpajakan rumit yang tidak dibutuhkan toko.
2. Sebaliknya, *user story* hasil elisitasi lapangan mampu menangkap kondisi faktual seperti keterbatasan laptop lama, operasional tanpa internet, sistem bon tempo kontraktor, dan kebutuhan huruf besar bagi staf berumur.
3. Dengan demikian, AI hanya berfungsi efektif sebagai alat bantu merapikan kriteria penerimaan, sedangkan penentuan kebutuhan sesungguhnya mutlak menuntut wawancara langsung ke narasumber di lapangan.
