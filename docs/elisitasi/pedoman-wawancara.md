# Pedoman Wawancara — Sistem Informasi Stok dan Penjualan Toko Bangunan "Maju Jaya"

## A. Konteks
- **Klien / Lokasi:** Toko Bangunan "Maju Jaya", Baamang, Sampit, Kotawaringin Timur.
- **Masalah Utama:**
  1. Terjadinya selisih antara pencatatan stok di buku gudang dengan jumlah fisik barang riil pada akhir bulan.
  2. Keterlambatan informasi barang terjual antara kasir (nota kertas rangkap) dan petugas gudang, sehingga stok lambat diperbarui.
  3. Piutang tempo pembelian kontraktor sering terlambat atau terlupa ditagih akibat pencatatan manual di buku terpisah.
- **Ruang Lingkup:**
  - *Di dalam proyek (In-Scope):*
    1. Pencatatan data barang masuk, barang keluar, dan rekonsiliasi stok opname.
    2. Pencatatan transaksi penjualan kasir dengan pemotongan stok otomatis.
    3. Notifikasi barang yang menipis (di bawah batas minimum) dan ringkasan barang terlaris mingguan.
    4. Pencatatan transaksi tempo (piutang kontraktor) dan pemantauan tanggal jatuh tempo tagihan.
  - *Di luar proyek (Out-of-Scope):*
    1. Integrasi otomatis payment gateway perbankan (pembayaran tetap tunai/transfer manual).
    2. Sistem akuntansi perpajakan lengkap (faktur pajak/e-faktur).
    3. Aplikasi native Android/iOS di app store (cukup aplikasi web responsif dan ringan).
- **Pemangku Kepentingan (Stakeholders):**

| Pemangku Kepentingan | Peran | Kepentingan | Cara Dilibatkan |
|----------------------|-------|-------------|-----------------|
| Ibu Rahma / Bapak H | Pemilik Toko (Pengambil keputusan) | Memantau ringkasan omzet, stok menipis, barang terlaris tiap Sabtu, dan mengontrol piutang | Wawancara mendalam & evaluasi berkala |
| Staf Gudang | Pengelola stok fisik | Kemudahan mencatat barang masuk, cek sisa stok, dan kecepatan penyesuaian stok opname | Wawancara & observasi alur bongkar muat |
| Kasir Toko | Operator transaksi penjualan | Kemudahan mencatat penjualan cepat, cetak nota, dan pengecekan ketersediaan barang | Wawancara & observasi saat jam sibuk |
| Kontraktor Kecil | Pelanggan kredit/tempo | Kejelasan status nota tempo, batas waktu pembayaran, dan rincian barang yang diambil | Studi dokumen nota piutang |

- **Batasan yang Diketahui:**
  - *Waktu:* Proyek harus selesai sebelum Minggu 16 semester ini.
  - *Perangkat:* Menggunakan 1 unit laptop kerja lama di meja kasir/kantor dan 1 ponsel pintar Android milik pemilik.
  - *Infrastruktur:* Jaringan internet toko sering tidak stabil dan sering terjadi pemadaman listrik di area sekitar.
  - *Kemampuan Pengguna:* Staf toko tidak terbiasa menggunakan komputer canggih; membutuhkan antarmuka yang bersih, tombol besar, alur kerja sederhana, dan teks berukuran besar.
  - *Biaya/Anggaran:* Anggaran terbatas; sistem tidak boleh membebani biaya langganan bulanan (*zero recurring fees*).

- **Teknik Elisitasi Dipilih:**

| Teknik Dipilih | Siapa / Apa yang Menjadi Sumber | Alasan Memilih |
|----------------|---------------------------------|----------------|
| Wawancara Mendalam (*Semi-structured Interview*) | Pemilik toko, kasir, dan staf gudang | Menggali keluhan harian, alur komunikasi saat barang keluar, kendala penagihan tempo, dan kebutuhan fitur laporan mingguan. |
| Studi Dokumen (*Document Analysis*) | Buku stok gudang, buku nota rangkap penjualan, dan buku catatan piutang kontraktor | Mengetahui format data nyata (nama 150 barang, variasi satuan zak/batang/truk, format nomor nota, jatuh tempo pembayaran). |
| Observasi Langsung | Meja kasir dan area gudang saat jam ramai transaksi | Melihat secara langsung jeda waktu pencatatan penjualan hingga staf gudang mengetahuinya serta interaksi fisik dengan nota kertas. |

---

## B. Tujuan Wawancara
1. Memahami alur kerja lengkap pencatatan stok masuk dari supplier hingga barang keluar melalui penjualan kasir.
2. Mengidentifikasi penyebab utama selisih data stok buku gudang dengan stok fisik di lapangan.
3. Mengetahui format pencatatan transaksi tempo/piutang kontraktor dan alasan mengapa tagihan sering terlupa.
4. Mengetahui kebutuhan spesifik laporan mingguan yang diharapkan pemilik toko setiap hari Sabtu.
5. Menemukan batasan teknis terkait kenyamanan penggunaan antarmuka bagi staf yang awam komputer.

---

## C. Daftar Pertanyaan Wawancara

| No | Kategori | Pertanyaan Utama | Pertanyaan Lanjutan |
|:--:|----------|------------------|---------------------|
| 1 | Proses saat ini | Bagaimana alur kerja sehari-hari saat ada barang masuk dari pemasok (*supplier*) hingga disimpan di gudang? | Bisakah diperlihatkan contoh surat jalan atau catatan penerimaan barang yang terakhir kali diterima? *(Permintaan Contoh Dokumen)* |
| 2 | Proses saat ini | Bagaimana proses pencatatan yang dilakukan kasir saat melayani transaksi penjualan barang kepada pelanggan? | Apakah kasir langsung mengabari orang gudang saat barang diambil pembeli, atau ada jeda waktu tertentu? |
| 3 | Masalah | Kendala apa yang paling sering dihadapi saat melakukan pencocokan (*stok opname*) antara fisik barang dengan catatan buku di akhir bulan? | Bisa diceritakan kejadian terakhir ketika terjadi selisih stok barang dalam jumlah besar? |
| 4 | Masalah | Bagaimana alur transaksi pembelian dengan sistem tempo oleh kontraktor selama ini dijalankan? | Mengapa tagihan piutang tersebut kerap kali terlupa untuk ditagih tepat waktu? |
| 5 | Data | Data apa saja yang wajib dicatat pada sebuah nota penjualan toko bangunan? | Boleh kami melihat dan memotret lembar nota rangkap yang biasa diberikan kepada pembeli? *(Permintaan Contoh Dokumen)* |
| 6 | Data | Bagaimana cara toko mengelola sekitar 150 jenis barang dengan harga beli dan jual yang sering berubah tiap minggunya? | Di mana daftar perubahan harga tersebut saat ini disimpan atau dicatat? |
| 7 | Data | Bagaimana format pencatatan daftar piutang kontraktor yang berjalan saat ini? | Bisakah kami melihat contoh buku catatan piutang atau kartu utang pelanggan yang digunakan? *(Permintaan Contoh Dokumen)* |
| 8 | Pengguna | Siapa saja staf yang nantinya akan mengoperasikan sistem di meja kasir maupun di gudang? | Sejauh mana tingkat kenyamanan atau kebiasaan staf dalam mengoperasikan laptop atau komputer? |
| 9 | Pengguna | Tampilan antarmuka seperti apa yang paling nyaman digunakan oleh kasir dan staf gudang saat toko sedang ramai pembeli? | Apakah ukuran tulisan, kontras warna, atau penggunaan navigasi keyboard menjadi kebutuhan utama? |
| 10 | Kendala | Apa yang biasanya terjadi pada proses pelayanan toko jika aliran listrik padam atau jaringan internet terputus? | Berapa lama pemadaman listrik biasanya berlangsung di wilayah toko? |
| 11 | Kendala | Mengingat perangkat yang tersedia adalah satu laptop lama dan ponsel, apakah aplikasi diharapkan bisa diakses dari kedua perangkat tersebut? | Apakah laptop tersebut diletakkan menetap di meja kasir? |
| 12 | Harapan | Informasi apa saja yang diharapkan dapat dilihat setiap hari Sabtu mengenai performa barang di toko? | Apakah membutuhkan rangkuman barang paling laris serta daftar barang yang stoknya sudah kritis di bawah batas minimum? |
| 13 | Harapan | Seperti apa mekanisme pengingat (*reminder*) yang ideal agar piutang tempo kontraktor tidak lewat dari dua minggu? | Apakah cukup berupa penanda warna merah pada daftar tagihan yang mendekati jatuh tempo? |
| 14 | Harapan | Apa tolak ukur keberhasilan bagi toko jika aplikasi pencatatan stok dan penjualan ini sudah diterapkan nantinya? | Berapa estimasi waktu maksimal yang diharapkan untuk mencatat satu transaksi nota? |

---

## D. Etika dan Privasi
- **Izin Klien:** Izin wawancara diperoleh pada tanggal 04 November 2026 melalui konfirmasi pesan tertulis dan tatap muka bersama pemilik Toko Bangunan.
- **Perlindungan Data Pribadi:**
  - Nama pelanggan, nomor telepon, dan data pribadi kontraktor disamarkan menjadi inisial (misal: "Kontraktor A", "Pelanggan B").
  - Nominal saldo keuangan sensitif yang difoto untuk keperluan analisis telah disamarkan dengan seizin pemilik.
  - Rekaman suara dan foto lembar kerja hanya digunakan untuk keperluan akademik mata kuliah Rekayasa Perangkat Lunak.

---

## E. Pemeriksaan Kualitas Pertanyaan

| Pemeriksaan Kualitas Pertanyaan | Lolos? | Catatan / Perbaikan yang Dilakukan |
|---------------------------------|:------:|-----------------------------------|
| **Terbuka:** tidak bisa dijawab hanya "ya/tidak" | Ya | Pertanyaan menggunakan kata tanya "Bagaimana", "Ceritakan", dan "Apa saja", menghindari pertanyaan tertutup. |
| **Netral:** tidak mengarahkan ke solusi tertentu | Ya | Pertanyaan tidak mengarahkan narasumber untuk memuji atau memilih teknologi tertentu (misal: tidak bertanya "Bukankah lebih enak pakai aplikasi web?"). |
| **Satu topik per pertanyaan** | Ya | Setiap nomor pertanyaan memfokuskan satu hal spesifik (alur masuk, alur nota, atau alur piutang). |
| **Relevan dengan klien** | Ya | Konteks pertanyaan spesifik untuk karakteristik toko bangunan (150 jenis material, nota rangkap, tempo kontraktor, laptop lama). |
| **Menggali contoh nyata** | Ya | Terdapat pertanyaan eksplisit meminta contoh kejadian terakhir dan bukti fisik buku catatan. |
| **Permintaan contoh data/dokumen** | Ya | Terdapat 3 pertanyaan yang meminta contoh fisik dokumen (surat jalan/stok, nota rangkap kasir, buku piutang tempo). |

---

## F. Dokumentasi Izin Wawancara Klien Nyata (Langkah 11)

- **Tanggal Komunikasi Izin:** 06 November 2026, 09.15 WIB
- **Kanal:** Pesan WhatsApp & Kunjungan Pendahuluan
- **Narasumber (Disamarkan):** Bapak H (Pemilik Toko Bahan Bangunan di Jl. Tjilik Riwut, Sampit)
- **Teks Pesan Izin (Sesuai Lampiran C.1):**
  > *"Selamat pagi, Bapak H. Saya Muhammad Rapianur, mahasiswa D3 Teknologi Informasi Politeknik Sampit. Dalam tugas mata kuliah Rekayasa Perangkat Lunak, kelompok kami (3 orang) mempelajari kebutuhan usaha toko bangunan di sekitar Sampit untuk dibuatkan purwarupa aplikasi pencatatan stok dan penjualan sederhana sebagai latihan praktikum.*  
  > *Bolehkah kami mewawancarai Bapak sekitar 30–45 menit tentang cara pencatatan stok dan transaksi yang dipakai sekarang? Kami hanya mencatat hal yang berkaitan dengan alur kerja, data pribadi akan kami samarkan sepenuhnya, dan tidak ada kewajiban membeli atau memakai aplikasi.*  
  > *Bila berkenan, kami juga ingin melihat (dan memotret) contoh format buku/nota yang dipakai dengan seizin Bapak. Mohon kabari hari dan waktu yang nyaman bagi Bapak. Terima kasih banyak atas kesediaannya."*
- **Respons Klien:** Disetujui untuk dilaksanakan pada Sabtu, 07 November 2026 pukul 14.00 WIB saat aktivitas toko mulai lengang.

---

## G. Pembaruan dan Evaluasi Pedoman Pasca-Wawancara Lapangan (Langkah 13 poin 4)

Setelah pelaksanaan wawancara klien nyata di lapangan, pedoman dievaluasi sebagai berikut:
1. **Pertanyaan yang Dihapus/Disederhanakan:** Pertanyaan teknis awal mengenai jenis database atau jaringan ditiadakan karena membingungkan narasumber yang non-teknis. Pertanyaan difokuskan ke aspek fungsional ("Berapa lama transaksi bisa selesai?").
2. **Pertanyaan Tambahan yang Terbukti Sangat Produktif:**
   - *"Jika kontraktor mengutus tukangnya untuk mengambil barang, siapa yang menandatangani nota bon tempo?"* (Ternyata toko mencatat nama sopir/tukang pengambil di sudut nota agar kontraktor tidak menyangkal saat penagihan).
   - *"Bagaimana penanganan harga jika ada pelanggan borongan proyek?"* (Toko memiliki toleransi potongan harga manual untuk pembelian semen di atas 50 sak).
