# Jurnal Vibe Coding — Rekayasa Perangkat Lunak

**Nama:** Muhammad Rapianur  
**NIM:** 24554010004  
**Kelas:** Sistem Informasi / D3 Teknologi Informasi  
**Proyek:** Sistem Informasi Pengelolaan Stok dan Penjualan Toko Bangunan "Maju Jaya"

---

## Log Siklus Vibe Coding (Jobsheet 1 s.d. Jobsheet 3)

| No | Modul / Jobsheet | Tujuan | Prompt (Ringkas) | Hasil AI | Keputusan | Alasan Keputusan |
|:--:|:----------------:|--------|------------------|----------|:---------:|------------------|
| 1 | Jobsheet 1 | Beranda + formulir nama | Buat web Flask 1 halaman: judul 'Halo Sampit!', waktu server, dan formulir sapaan nama tanpa DB & JS, aman XSS. | Berkas `app.py`, `templates/index.html`, dan penjelasan cara kerja 5 butir. | **Terima** | Semua kriteria penerimaan terpenuhi, berjalan lancar di localhost, dan terbukti aman dari serangan XSS saat diuji dengan tag `<b>tes</b>`. |
| 2 | Jobsheet 1 | Tambah salam sesuai waktu | Tambahkan fungsi `salam_waktu(jam)` untuk salam dinamis (pagi, siang, sore, malam) sebelum waktu server tanpa menambah paket baru. | Potongan kode fungsi `salam_waktu(jam)` pada `app.py` dan pembaruan elemen `{{ salam }}` di `templates/index.html`. | **Terima** | Lolos uji seluruh batas jam (3, 4, 10, 11, 14, 15, 17, 18) via terminal dan sapaan waktu tampil presisi di beranda. |
| 3 | Jobsheet 1 | Halaman baru `/tentang` | Tambahkan rute `/tentang` yang menampilkan data identitas mahasiswa (nama, NIM, kelas, kelompok) dan navigasi bolak-balik ke beranda. | Rute baru pada `app.py`, templat `templates/tentang.html`, serta tautan navigasi di `templates/index.html`. | **Terima** | Tampilan profil mahasiswa tampil lengkap, berstatus HTTP 200, dan navigasi bolak-balik berfungsi mulus. |
| 4 | Jobsheet 1 | Validasi batas karakter di server | Tambahkan pembatasan panjang nama maksimal 50 karakter di sisi server untuk mengantisipasi manipulasi Inspect Element pada klien. | Pemotongan string `[:50]` di `app.py` dan penambahan atribut `maxlength="50"` di `index.html`. | **Terima** | Terbukti berhasil menahan input 80 karakter yang dimanipulasi via F12 menjadi tepat 50 karakter saat diproses server. |
| 5 | Jobsheet 1 | Eksperimen prompt | Bandingkan luaran prompt singkat 'Buatkan aplikasi web Halo Sampit' dengan prompt terstruktur 4 unsur. | Analisis komparasi jumlah berkas, kesesuaian batasan, dan efisiensi waktu pengerjaan. | **Terima** | Membuktikan bahwa prompt terstruktur jauh lebih unggul dan langsung menghasilkan kode siap pakai tanpa dependensi berlebih. |
| 6 | Jobsheet 3 (Langkah 4) | Penyusunan draf pedoman wawancara | Buat 15 pertanyaan wawancara netral dan terbuka untuk menggali alur kerja toko bangunan, masalah stok, dan piutang. | Draf 15 pertanyaan wawancara berkategori, namun beberapa pertanyaan mengarahkan narasumber ke solusi aplikasi ("Bukankah lebih baik pakai software?"). | **Ubah** | Mengubah 3 pertanyaan mengarahkan menjadi pertanyaan terbuka netral dan menyisipkan 3 pertanyaan permintaan contoh dokumen nyata (surat jalan, nota rangkap, buku bon). |
| 7 | Jobsheet 3 (Langkah 9) | Kritik INVEST user story simulasi | Kritik draf user story simulasi Persona 1 toko bangunan berdasarkan kriteria INVEST dan sarankan kriteria Given-When-Then. | AI menyarankan kriteria Given-When-Then terukur, namun menambahkan fitur pemindai barcode nirkabel dan pembayaran e-wallet/QRIS otomatis. | **Tolak** | Menolak fitur scanner barcode dan QRIS karena toko bangunan klien berskala lokal yang hanya melayani pembayaran tunai (*cash*) atau bon tempo, tidak punya alat scanner, dan staf gaptek. Menerima format angka terukur Given-When-Then. |
| 8 | Jobsheet 3 (Langkah 13) | Finalisasi user story klien nyata | Kritik 14 user story hasil wawancara lapangan klien nyata di Sampit (toko material semen, besi, pipa) dengan kendala listrik/laptop lama. | AI menyarankan integrasi WhatsApp Gateway tagihan otomatis ke kontraktor dan pemisahan modul retur material rusak. | **Ubah** | Menerima saran pemisahan pencatatan material rusak (US-03) dan pencatatan nama tukang pengambil barang (US-08), tetapi menolak modul WhatsApp gateway otomatis karena membebani biaya langganan API berbayar yang ditolak pemilik toko. |

