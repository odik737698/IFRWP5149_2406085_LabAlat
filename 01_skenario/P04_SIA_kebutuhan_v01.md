<!-- Skenario tugas (salinan dari jobsheet Pertemuan 4; berkas lengkap: P04_SIA_skenario_v01.md) -->
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa: menambah data mahasiswa baru, mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh collaboration yang bersesuaian.

<!-- Kebutuhan Tugas -->
| ID | Kebutuhan Tugas |
|---|---|
| SIA-R01 s.d. SIA-R06 | Kebutuhan Pertemuan 2 dan 3 tetap berlaku dan tidak berubah arti (lihat jobsheet Pertemuan 2 dan 3). |
| SIA-R07 | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik. |
| SIA-R08 | Dosen dapat menginput nilai mata kuliah yang diampunya. |
| SIA-R09 | Mahasiswa dapat melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. |
| SIA-R10 | Admin Akademik dapat mengelola data mahasiswa. |
| SIA-R11 | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus, yaitu tambah, ubah, dan hapus data mahasiswa. |
| SIA-R12 | Model menunjukkan collaboration yang merealisasikan use case Input Nilai Mata Kuliah dan Lihat KHS. |

<!-- Batas dan asumsi -->
- Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02 (Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap mempunyai identitas berbeda.
- Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
- Kalender akademik pada tugas ini adalah agenda resmi institusi (awal semester, batas KRS, masa ujian, dan sejenisnya); tidak sama dengan jadwal kuliah pada Pertemuan 2.
- Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai yang diinput belum terpublikasi; KHS hanya menampilkan nilai yang sudah dipublikasikan.
- Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data akademik aktif. Ketentuan ini fiktif untuk latihan.
- Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari Pertemuan 3. Pembayaran dan perancangan basis data berada di luar tugas ini.

<!-- Pertanyaan terbuka: belum dimodelkan, bukan dianggap selesai -->
## Pertanyaan terbuka

| No. | Pertanyaan | Dampak pada model |
|---|---|---|
| 1 | Siapa yang menetapkan nilai menjadi "terpublikasi", dan kapan? Skenario hanya menyatakan nilai yang diinput belum terpublikasi. | Belum ada aktor atau use case publikasi nilai. SIA-UC09 hanya mengandalkan status Dipublikasikan yang diasumsikan sudah ada. |
| 2 | Apakah publikasi berlaku per semester ("semester yang nilainya sudah dipublikasikan", SIA-R09) atau per nilai ("hanya menampilkan nilai yang sudah dipublikasikan")? | SIA-UC09 A1 memakai tafsir per semester; perlu dikonfirmasi. |
| 3 | Berapa rentang nilai yang sah dan bagaimana skalanya (angka, huruf, bobot)? | SIA-UC08 A2 menyebut "rentang yang sah" tanpa angka agar tidak mengarang aturan. |
| 4 | Dapatkah dosen mengoreksi nilai setelah tersimpan, dan adakah batas waktu input nilai? Bagaimana bila masa perkuliahan belum berakhir? | Tidak dimodelkan; belum ada use case ubah nilai. Prasyarat hanya menyatakan masa perkuliahan telah berakhir. |
| 5 | Bolehkah dosen menyimpan sebagian nilai (draf), atau penyimpanan harus lengkap? | SIA-UC08 mengasumsikan penyimpanan utuh bila ada nilai tidak sah; kelengkapan isian belum diatur. |
| 6 | Apa yang dimaksud "data akademik aktif" pada aturan Hapus Data Mahasiswa (KRS berjalan, nilai, atau lainnya)? | SIA-UC13 hanya menyatakan penghapusan ditolak bila mahasiswa memiliki data akademik aktif. |
| 7 | Dapatkah satu orang berperan sebagai Dosen sekaligus Dosen Wali? | Dosen Wali dipertahankan sebagai aktor terpisah dari Pertemuan 3 tanpa generalization ke Dosen. |
| 8 | Siapa yang mengisi dan mengelola kalender akademik? | Di luar tugas; SIA-UC07 hanya melihat. |

<!-- Uji konsistensi (Langkah 8) -->
## Uji konsistensi tiga situasi

**Situasi A: Mahasiswa melihat kalender akademik tanpa garis asosiasi langsung dari Mahasiswa.**
Tetap benar. Mahasiswa adalah aktor khusus dari Civitas Akademika (panah generalization dari Mahasiswa dengan segitiga kosong menempel pada Civitas Akademika). Civitas Akademika punya satu asosiasi ke SIA-UC07 Lihat Kalender Akademik, dan aktor khusus mewarisi seluruh asosiasi aktor umum. Karena itu Mahasiswa (dan juga Dosen) dapat melihat kalender akademik tanpa garis sendiri; menggambar garis yang sama dari Mahasiswa dan Dosen justru menggandakan asosiasi warisan. Mahasiswa hanya menggambar asosiasi langsung untuk fungsi khususnya: SIA-UC01, SIA-UC03, SIA-UC05, dan SIA-UC09.

**Situasi B: Dosen yang bukan pengampu mencoba menginput nilai.**
Menurut deskripsi SIA-UC08, prasyarat "dosen adalah pengampu mata kuliah yang dipilih" tidak terpenuhi. Alur alternatif A1 berlaku pada langkah 2: sistem menolak, tidak menampilkan isian nilai, dan memberi tahu bahwa dosen bukan pengampu. Pascakondisi gagal berlaku: tidak ada nilai baru yang tersimpan dan data nilai tidak berubah.

**Situasi C: Admin Akademik menghapus data mahasiswa yang masih memiliki data akademik aktif.**
Menurut aturan tugas, Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data akademik aktif. Karena itu penghapusan ditolak: SIA-UC13 tidak menghasilkan data yang terhapus, data mahasiswa dan data akademiknya tetap, dan tidak ada perubahan yang tersimpan. Definisi "data akademik aktif" masih pertanyaan terbuka no. 6.

<!-- Pemetaan kebutuhan ke diagram: kriteria penerimaan -->
## Keterlacakan kebutuhan ke diagram kumulatif

| Kebutuhan | Representasi pada diagram |
|---|---|
| SIA-R01 s.d. SIA-R06 | Tetap: SIA-UC01 sampai SIA-UC06, «include» UC03 ke UC04, «extend» UC05 ke UC03, aktor Mahasiswa, Admin Akademik, Dosen Wali. |
| SIA-R07 | Aktor Civitas Akademika, generalization Mahasiswa dan Dosen ke Civitas Akademika, SIA-UC07, satu asosiasi Civitas Akademika ke SIA-UC07. |
| SIA-R08 | Aktor Dosen dan SIA-UC08, asosiasi Dosen ke SIA-UC08. |
| SIA-R09 | SIA-UC09, asosiasi Mahasiswa ke SIA-UC09. |
| SIA-R10 | SIA-UC10, asosiasi Admin Akademik ke SIA-UC10. |
| SIA-R11 | SIA-UC11, SIA-UC12, SIA-UC13 dengan tiga generalization ke SIA-UC10. |
| SIA-R12 | SIA-CO01 dan SIA-CO02 dengan dua realization ke SIA-UC08 dan SIA-UC09. |
