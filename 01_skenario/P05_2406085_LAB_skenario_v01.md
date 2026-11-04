# Lembar Skenario Pertemuan 5: Studi Kasus LAB

Tanggal: 28-10-2026 | NIM: 2406085 | Versi: v01
Kasus: Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus
Dokumen tabel (draw.io, satu halaman per tabel): `04_model_analisis/P05/LAB/P05_2406085_LAB_skenario_v01.drawio`
Isi tabel yang sama ada pada bagian 5 di bawah.

## 1. Acuan telaah

- Diagram acuan: diagram kumulatif Pertemuan 4 LAB (5 aktor, 12 use case, 2 collaboration, 17 hubungan menurut Tabel 4.5 jobsheet P04). Diagram tidak diubah pada pertemuan ini.
- Dua belas tabel skenario ditelaah satu per satu: aktor, relasi yang ditelusur, serta nama, ID, condition, dan extension point dicocokkan dengan diagram acuan. Tabel yang tidak memenuhi checklist diperbaiki (lihat bagian 3 dan 4).
- Kepala Laboratorium hanya mempunyai satu use case, yaitu LAB-UC07 Lihat Laporan Peminjaman, dan LAB-UC07 tidak mempunyai relasi lain. Tabel LAB-UC07 berdiri sendiri.

### Selisih berkas .drawio P04 terhadap jobsheet P04

Penulisan tabel mengikuti nama, ID, dan relasi pada jobsheet P04 (Tabel 4.5). Pada berkas `P04_2406085_LAB_usecase_v01.drawio` ditemukan selisih berikut. Berkas P04 tidak diubah pada pertemuan ini; perbaikannya menjadi pekerjaan P04 v02 dan perlu dicatat pada metadata dan logbook P04.

| No. | Selisih pada berkas P04 | Seharusnya (jobsheet P04) | Dampak pada tabel P05 |
|---|---|---|---|
| 1 | Aktor bernama "Petugas Laboran" dan "Kepala Laboran" | Petugas Laboratorium dan Kepala Laboratorium | Baris Aktor memakai nama jobsheet |
| 2 | Relasi dari Cetak bukti pengajuan ke Ajukan peminjaman berlabel «include» | «extend» dengan condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia | Tabel LAB-UC03 dan LAB-UC05 ditulis sebagai extend |
| 3 | Condition dan extension point tidak tertulis pada diagram | Tertulis sebagai catatan pada relasi extend | Condition dan extension point diambil dari jobsheet |
| 4 | Tidak ada asosiasi Petugas ke Kelola Data Peralatan (16 hubungan, seharusnya 17) | Asosiasi Petugas Laboratorium ke LAB-UC02 | Baris Aktor LAB-UC02 tetap Petugas Laboratorium |
| 5 | Label use case berkapitalisasi berbeda (mis. "Ajukan peminjaman", "Periksa ketersediaan", "Cetak bukti pengajuan") | Ajukan Peminjaman, Periksa Ketersediaan, Cetak Bukti Pengajuan, dan seterusnya | Nama pada tabel memakai penulisan jobsheet |

## 2. Checklist hasil telaah (12 tabel)

Pemeriksaan otomatis dilakukan dengan membaca ulang berkas .drawio hasil (bukan dari data sumber).

- ✔️ Seluruh field terisi pada 12 tabel: Nama use case, Aktor, Tujuan, Deskripsi, kolom Kegiatan dan Respon sistem, Skenario Normal, Skenario Alternative, Skenario Akhir.
- ✔️ Langkah berurutan, satu aksi per langkah, penomoran berlanjut dari Skenario Normal ke Skenario Alternative tanpa pengulangan nomor. Satu aksi per langkah ditinjau manual: langkah yang memuat daftar field atau data (misalnya tanggal pinjam, tanggal rencana kembali, dan keperluan) dihitung satu aksi.
- ✔️ Kolom Kegiatan berisi aksi aktor dan kolom Respon sistem berisi tanggapan sistem. Mengikuti gaya Tabel 5.1, baris syarat cabang alternatif dan baris pemanggilan use case yang disertakan ditulis pada kolom Kegiatan.
- ✔️ Data dan status disebut eksplisit (ditinjau manual): tanggal pinjam, tanggal rencana kembali, keperluan peminjaman, status Menunggu Keputusan, Disetujui, Ditolak, Dipinjam, Selesai, dan nilai kondisi Baik, Rusak Ringan, Rusak Berat.
- ✔️ Include ditulis sebagai langkah rujukan pada Skenario Normal: LAB-UC03 langkah 2 ke LAB-UC04, LAB-UC11 langkah 6 ke LAB-UC12, tanpa menyalin langkahnya.
- ✔️ Extend ditulis sebagai cabang bersyarat pada Skenario Alternative LAB-UC03 (langkah 14 dan 15) dengan condition [mahasiswa memilih cetak], extension point Bukti pengajuan tersedia, dan rujukan ke Tabel skenario LAB-UC05.
- ✔️ Generalization aktor: LAB-UC01 dan LAB-UC03 ditulis satu kali atas nama Peminjam; tidak ada tabel ganda untuk Mahasiswa dan Dosen.
- ✔️ Generalization use case: LAB-UC02 memuat perilaku bersama; LAB-UC08, LAB-UC09, LAB-UC10 merujuk ke Tabel skenario LAB-UC02 untuk langkah bersama.
- ✔️ Collaboration LAB-CO01 dan LAB-CO02 disebut pada keterangan tabel LAB-UC03 dan LAB-UC11, tanpa langkah kegiatan sendiri.
- ✔️ Setiap tabel mempunyai Skenario Alternative dan Skenario Akhir.
- ✔️ Nama, ID, dan aktor sama dengan diagram acuan menurut jobsheet P04. ⚠️ Berkas .drawio P04 memiliki selisih (bagian 1) yang perlu diperbaiki pada P04 v02 agar sama persis.
- ✔️ Kepala Laboratorium: LAB-UC07 berdiri sendiri; langkahnya tidak memuat include, extend, generalization, atau realization.
- ✔️ Berkas diagram P04 tidak diubah; dokumen skenario disimpan dengan nama dan versi yang benar.

## 3. Lembar penelusuran

| Tabel | Use case | Relasi yang ditelusur | Hasil pencocokan |
|---|---|---|---|
| 5.3 | LAB-UC01 Lihat Ketersediaan Peralatan | Asosiasi Peminjam ke LAB-UC01 (baris Aktor); generalization Mahasiswa dan Dosen ke Peminjam (catatan berlaku); kebutuhan LAB-R01, LAB-R07 | Cocok |
| 5.1 | LAB-UC03 Ajukan Peminjaman | Asosiasi Peminjam ke LAB-UC03 (baris Aktor); include LAB-UC03 ke LAB-UC04 (langkah 2); extend LAB-UC05 ke LAB-UC03 dengan condition dan extension point (langkah 14 dan 15); realization LAB-CO01 ke LAB-UC03 (keterangan); generalization aktor | Cocok setelah perbaikan |
| 5.4 | LAB-UC04 Periksa Ketersediaan | Include LAB-UC03 ke LAB-UC04 (langkah 1 sebagai pemanggilan); tidak ada asosiasi aktor langsung | Cocok |
| 5.5 | LAB-UC05 Cetak Bukti Pengajuan | Asosiasi khusus Mahasiswa ke LAB-UC05; extend LAB-UC05 ke LAB-UC03; condition dan extension point | Cocok setelah perbaikan |
| 5.6 | LAB-UC02 Kelola Data Peralatan | Asosiasi Petugas Laboratorium ke LAB-UC02; generalization LAB-UC08, LAB-UC09, LAB-UC10 ke LAB-UC02 | Cocok dengan jobsheet P04; garis asosiasi belum tergambar pada berkas .drawio P04 |
| 5.7 | LAB-UC08 Tambah Data Peralatan | Generalization LAB-UC08 ke LAB-UC02; asosiasi Petugas hanya ke LAB-UC02 (diwarisi, tidak digambar ke LAB-UC08) | Cocok |
| 5.8 | LAB-UC09 Ubah Data Peralatan | Generalization LAB-UC09 ke LAB-UC02 | Cocok |
| 5.9 | LAB-UC10 Hapus Data Peralatan | Generalization LAB-UC10 ke LAB-UC02 | Cocok |
| 5.10 | LAB-UC06 Proses Keputusan Peminjaman | Asosiasi Petugas Laboratorium ke LAB-UC06; tidak ada relasi antar use case | Cocok setelah perbaikan |
| 5.11 | LAB-UC07 Lihat Laporan Peminjaman | Satu asosiasi Kepala Laboratorium ke LAB-UC07; LAB-UC07 tanpa relasi lain | Cocok |
| 5.12 | LAB-UC11 Catat Pengembalian Peralatan | Asosiasi Petugas Laboratorium ke LAB-UC11; include LAB-UC11 ke LAB-UC12 (langkah 6); realization LAB-CO02 ke LAB-UC11 (keterangan) | Cocok setelah perbaikan |
| 5.13 | LAB-UC12 Periksa Kondisi Peralatan | Include LAB-UC11 ke LAB-UC12 (langkah 1 sebagai pemanggilan); tidak ada asosiasi aktor langsung | Cocok setelah perbaikan |

Perbaikan terhadap tabel jobsheet, per tabel:

- 5.3 LAB-UC01: Langkah diberi nomor dan dipisah satu aksi per langkah; isi tidak berubah.
- 5.1 LAB-UC03: Cabang extend diberi frasa cabang dari langkah dan aktornya ditulis Mahasiswa (condition [mahasiswa memilih cetak] hanya berlaku untuk mahasiswa); langkah yang memuat dua tanggapan sistem dipecah.
- 5.4 LAB-UC04: Langkah penutup yang bukan perilaku LAB-UC04 (melanjutkan penyimpanan pengajuan) diganti dengan penyampaian hasil ke alur pengajuan.
- 5.5 LAB-UC05: Alternatif Mahasiswa tidak memilih cetak diganti Mahasiswa membatalkan pencetakan, karena bila cetak tidak dipilih LAB-UC05 memang tidak berjalan (perilaku itu milik LAB-UC03).
- 5.6 LAB-UC02: Langkah dipisah satu aksi per langkah; isi tidak berubah.
- 5.7 LAB-UC08: Ditambah langkah rujukan ke langkah bersama LAB-UC02; langkah dipisah satu aksi per langkah.
- 5.8 LAB-UC09: Ditambah langkah rujukan ke langkah bersama LAB-UC02; cabang data tidak ditemukan dirujuk ke langkah pemilihan data.
- 5.9 LAB-UC10: Ditambah langkah rujukan ke langkah bersama LAB-UC02; langkah dipisah satu aksi per langkah.
- 5.10 LAB-UC06: Cabang penolakan dirujuk ke langkah penetapan keputusan (semula langkah pemilihan+penetapan digabung dan cabang merujuk langkah 4); ditambah tanggapan menampilkan data pengajuan terpilih agar satu aksi per langkah.
- 5.11 LAB-UC07: Isi tidak berubah.
- 5.12 LAB-UC11: Skenario Akhir dilengkapi jalur jumlah alat tidak sesuai (sebelumnya hanya jalur status bukan Dipinjam); langkah yang memuat beberapa tanggapan dipecah.
- 5.13 LAB-UC12: Deskripsi semula menyatakan tidak ada interaksi langsung dengan aktor padahal langkah 3 melibatkan petugas; kini dinyatakan interaksi terjadi melalui alur LAB-UC11.

## 4. Temuan telaah

1. Penomoran langkah pada hasil telaah berbeda dari tabel jobsheet karena langkah yang memuat dua tanggapan sistem dipisah (aturan satu aksi per langkah). Contoh: cabang extend pada LAB-UC03 menjadi langkah 14 dan 15, bukan 11 dan 12.
2. Cabang extend pada Tabel 5.1 jobsheet belum memuat frasa cabang dari langkah dan menuliskan aktor Peminjam padahal condition [mahasiswa memilih cetak] hanya berlaku untuk mahasiswa.
3. Alternatif LAB-UC05 pada jobsheet (Mahasiswa tidak memilih cetak) bertentangan dengan sifat extend: bila cetak tidak dipilih, LAB-UC05 tidak berjalan dan LAB-UC03 selesai tanpa cabang.
4. Cabang penolakan pada LAB-UC06 merujuk langkah yang bukan langkah penetapan keputusan.
5. Skenario Akhir LAB-UC11 belum mencakup jalur jumlah alat tidak sesuai.
6. Deskripsi LAB-UC12 menyatakan tidak ada interaksi langsung dengan aktor, padahal petugas memilih nilai kondisi; kini dinyatakan interaksi terjadi melalui alur LAB-UC11.
7. Catatan penulisan jobsheet (untuk dikonfirmasi ke dosen): rujukan "Tabel 5.0" pada kesalahan umum d sebenarnya Tabel 5 (aturan pemetaan); aturan 3e menyebut frasa cabang "di awal" langkah, sedangkan contoh menuliskannya di akhir (hasil telaah mengikuti contoh); format berkas deliverable pada jobsheet tidak seragam (.md pada ringkasan dan .drawio pada langkah SIA).

## 5. Tabel skenario hasil telaah

### Tabel 5.3 Skenario Use Case LAB-UC01 Lihat Ketersediaan Peralatan

| Nama use case | LAB-UC01 Lihat Ketersediaan Peralatan |
|---|---|
| Aktor | Peminjam (berlaku untuk Mahasiswa dan Dosen) |
| Tujuan | Peminjam dapat mengetahui peralatan yang tersedia sebelum mengajukan peminjaman |
| Deskripsi | Peminjam membuka fungsi ketersediaan dan melihat daftar peralatan beserta status ketersediaannya |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Peminjam membuka fungsi Lihat Ketersediaan Peralatan |  |
|  | 2. Sistem menampilkan daftar peralatan beserta status ketersediaannya |
| **Skenario Alternative** | |
| 3. Tidak ada peralatan yang tersedia pada daftar (cabang dari langkah 2) |  |
|  | 4. Sistem menampilkan pesan tidak ada peralatan yang tersedia |
| Skenario Akhir | Use case selesai jika daftar peralatan beserta status ketersediaannya ditampilkan; jika tidak ada peralatan yang tersedia, use case selesai dengan pesan tersebut. |

Keterangan tabel: aktor umum Peminjam berlaku untuk Mahasiswa dan Dosen (generalization aktor), sehingga skenario ditulis satu kali. Tidak ada perbedaan perilaku antara Mahasiswa dan Dosen pada use case ini.

### Tabel 5.1 Skenario Use Case LAB-UC03 Ajukan Peminjaman

| Nama use case | LAB-UC03 Ajukan Peminjaman |
|---|---|
| Aktor | Peminjam (berlaku untuk Mahasiswa dan Dosen) |
| Tujuan | Pengajuan peminjaman tercatat dan dapat diproses oleh petugas |
| Deskripsi | Peminjam memilih peralatan yang tersedia, mengisi data peminjaman, dan mengirim pengajuan |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Peminjam memilih peralatan yang akan dipinjam |  |
|  | 2. Sistem menjalankan Periksa Ketersediaan, include LAB-UC04 (lihat Tabel skenario LAB-UC04) |
| 3. Peminjam mengisi tanggal pinjam, tanggal rencana kembali, dan keperluan peminjaman |  |
|  | 4. Sistem memeriksa kelengkapan isian |
|  | 5. Sistem menampilkan ringkasan pengajuan |
| 6. Peminjam mengirim pengajuan |  |
|  | 7. Sistem menyimpan pengajuan dengan status Menunggu Keputusan |
|  | 8. Sistem menampilkan nomor pengajuan sebagai konfirmasi |
| **Skenario Alternative** | |
| 9. Peralatan yang dipilih tidak tersedia (cabang dari langkah 2) |  |
|  | 10. Sistem menampilkan pesan peralatan tidak tersedia; pengajuan tidak dilanjutkan |
| 11. Isian pengajuan tidak lengkap (cabang dari langkah 4) |  |
|  | 12. Sistem menampilkan pesan isian belum lengkap |
|  | 13. Sistem meminta peminjam melengkapi isian |
| 14. Mahasiswa memilih cetak bukti (cabang dari langkah 8; condition [mahasiswa memilih cetak]; extension point Bukti pengajuan tersedia; extend LAB-UC05 Cetak Bukti Pengajuan, lihat Tabel skenario LAB-UC05) |  |
|  | 15. Sistem menampilkan bukti pengajuan dengan nomor pengajuan sesuai Tabel skenario LAB-UC05 |
| Skenario Akhir | Use case selesai jika pengajuan tersimpan dengan status Menunggu Keputusan; jika peralatan tidak tersedia atau isian tidak lengkap, pengajuan tidak tersimpan dan peminjam kembali ke daftar peralatan atau melengkapi isian. |

Keterangan tabel: use case ini direalisasikan oleh collaboration LAB-CO01 Ajukan Peminjaman. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. Include LAB-UC04 menjadi langkah 2; extend LAB-UC05 menjadi langkah 14 dan 15. Aktor Peminjam berlaku untuk Mahasiswa dan Dosen; cabang cetak bukti hanya berlaku untuk Mahasiswa. Dasar langkah: kebutuhan LAB-R03 dan LAB-R07.

### Tabel 5.4 Skenario Use Case LAB-UC04 Periksa Ketersediaan

| Nama use case | LAB-UC04 Periksa Ketersediaan |
|---|---|
| Aktor | Peminjam (berjalan di dalam LAB-UC03 Ajukan Peminjaman) |
| Tujuan | Ketersediaan peralatan yang dipilih terperiksa sebelum pengajuan disimpan |
| Deskripsi | Sistem memeriksa jumlah dan status peralatan yang dipilih peminjam dan menyampaikan hasilnya kepada alur pengajuan. Use case ini berjalan di dalam LAB-UC03 melalui include dan tidak mempunyai interaksi langsung dengan aktor |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Alur pengajuan LAB-UC03 memanggil Periksa Ketersediaan dengan peralatan yang dipilih |  |
|  | 2. Sistem memeriksa jumlah dan status peralatan tersebut |
|  | 3. Sistem menyatakan peralatan tersedia |
|  | 4. Sistem menyampaikan hasil tersedia kepada alur pengajuan LAB-UC03 |
| **Skenario Alternative** | |
| 5. Peralatan tidak tersedia atau jumlah tidak mencukupi (cabang dari langkah 2) |  |
|  | 6. Sistem menyampaikan hasil tidak tersedia kepada alur pengajuan LAB-UC03; pengajuan berhenti |
| Skenario Akhir | Use case selesai jika hasil pemeriksaan tersampaikan kepada alur pengajuan; hasil tersedia melanjutkan pengajuan, hasil tidak tersedia menghentikan pengajuan. |

Keterangan tabel: use case yang disertakan oleh LAB-UC03 (include). Pada diagram tidak ada asosiasi langsung dari aktor ke LAB-UC04; baris Aktor menunjuk peminjam pada LAB-UC03 yang memanggilnya.

### Tabel 5.5 Skenario Use Case LAB-UC05 Cetak Bukti Pengajuan

| Nama use case | LAB-UC05 Cetak Bukti Pengajuan |
|---|---|
| Aktor | Mahasiswa (asosiasi khusus) |
| Tujuan | Bukti pengajuan tercetak sebagai tambahan bersyarat pada pengajuan |
| Deskripsi | Mahasiswa yang memilih cetak pada konfirmasi pengajuan menerima bukti pengajuan dengan nomor pengajuan. Cabang ini berlaku dengan condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia pada LAB-UC03 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Mahasiswa memilih cetak bukti pada konfirmasi pengajuan |  |
|  | 2. Sistem menampilkan bukti pengajuan dengan nomor pengajuan dan status Menunggu Keputusan |
| 3. Mahasiswa mengonfirmasi pencetakan |  |
|  | 4. Sistem mencetak bukti pengajuan |
| **Skenario Alternative** | |
| 5. Mahasiswa membatalkan pencetakan (cabang dari langkah 3) |  |
|  | 6. Sistem menutup bukti pengajuan tanpa mencetak; pengajuan tetap tersimpan dengan status Menunggu Keputusan |
| Skenario Akhir | Use case selesai jika bukti pengajuan tercetak; jika mahasiswa membatalkan pencetakan, bukti tidak tercetak dan pengajuan tetap tersimpan. Bila mahasiswa tidak memilih cetak, use case ini tidak dijalankan dan LAB-UC03 selesai tanpa cabang ini. |

Keterangan tabel: use case tambahan (extend) pada LAB-UC03 dengan condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia. Use case dasar tetap selesai tanpa cabang ini.

### Tabel 5.6 Skenario Use Case LAB-UC02 Kelola Data Peralatan

| Nama use case | LAB-UC02 Kelola Data Peralatan |
|---|---|
| Aktor | Petugas Laboratorium |
| Tujuan | Data peralatan terkelola melalui satu fungsi pengelolaan bersama |
| Deskripsi | Petugas membuka fungsi pengelolaan data peralatan, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya masing-masing |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Petugas membuka fungsi Kelola Data Peralatan |  |
|  | 2. Sistem menampilkan daftar data peralatan |
| 3. Petugas memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus |  |
|  | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih |
| 5. Petugas mengisi atau mengonfirmasi data |  |
|  | 6. Sistem memeriksa kelengkapan dan keabsahan data |
| 7. Petugas menyimpan perubahan |  |
|  | 8. Sistem menyimpan perubahan data peralatan |
|  | 9. Sistem menampilkan konfirmasi penyimpanan |
| **Skenario Alternative** | |
| 10. Data tidak lengkap atau tidak sah (cabang dari langkah 6) |  |
|  | 11. Sistem menolak penyimpanan |
|  | 12. Sistem menampilkan pesan kesalahan data |
| Skenario Akhir | Use case selesai jika perubahan data peralatan tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

Keterangan tabel: use case UMUM bagi LAB-UC08, LAB-UC09, dan LAB-UC10. Tabel ini memuat perilaku bersama; ketiga tabel khusus hanya memuat perilaku pembeda dan merujuk ke tabel ini untuk langkah bersama.

### Tabel 5.7 Skenario Use Case LAB-UC08 Tambah Data Peralatan

| Nama use case | LAB-UC08 Tambah Data Peralatan |
|---|---|
| Aktor | Petugas Laboratorium |
| Tujuan | Data peralatan baru tersimpan sebagai bentuk khusus dari pengelolaan data peralatan |
| Deskripsi | Petugas mengisi data peralatan baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario LAB-UC02 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Petugas memilih bentuk pengelolaan tambah (langkah bersama LAB-UC02 langkah 1 sampai 3; lihat Tabel skenario LAB-UC02) |  |
|  | 2. Sistem menampilkan formulir data peralatan baru |
| 3. Petugas mengisi data peralatan baru |  |
|  | 4. Sistem memeriksa kelengkapan data |
| 5. Petugas menyimpan data |  |
|  | 6. Sistem menyimpan data peralatan baru |
|  | 7. Sistem menampilkan konfirmasi penyimpanan |
| **Skenario Alternative** | |
| 8. Data tidak lengkap (cabang dari langkah 4) |  |
|  | 9. Sistem menolak penyimpanan |
|  | 10. Sistem meminta petugas melengkapi data |
| Skenario Akhir | Use case selesai jika data peralatan baru tersimpan; jika data tidak lengkap, data tidak tersimpan. |

Keterangan tabel: use case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data baru tersimpan. Langkah bersama mengikuti Tabel skenario LAB-UC02.

### Tabel 5.8 Skenario Use Case LAB-UC09 Ubah Data Peralatan

| Nama use case | LAB-UC09 Ubah Data Peralatan |
|---|---|
| Aktor | Petugas Laboratorium |
| Tujuan | Data peralatan berubah sebagai bentuk khusus dari pengelolaan data peralatan |
| Deskripsi | Petugas memilih data peralatan, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario LAB-UC02 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Petugas memilih bentuk pengelolaan ubah (langkah bersama LAB-UC02 langkah 1 sampai 3; lihat Tabel skenario LAB-UC02) |  |
| 2. Petugas memilih data peralatan yang akan diubah |  |
|  | 3. Sistem menampilkan data peralatan saat ini |
| 4. Petugas mengubah data peralatan |  |
|  | 5. Sistem memeriksa perubahan data |
| 6. Petugas menyimpan perubahan |  |
|  | 7. Sistem menyimpan data peralatan yang diubah |
|  | 8. Sistem menampilkan konfirmasi penyimpanan |
| **Skenario Alternative** | |
| 9. Data peralatan tidak ditemukan (cabang dari langkah 2) |  |
|  | 10. Sistem menampilkan pesan data peralatan tidak ditemukan |
| Skenario Akhir | Use case selesai jika perubahan data peralatan tersimpan; jika data tidak ditemukan, perubahan tidak tersimpan. |

Keterangan tabel: use case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data peralatan berubah. Langkah bersama mengikuti Tabel skenario LAB-UC02.

### Tabel 5.9 Skenario Use Case LAB-UC10 Hapus Data Peralatan

| Nama use case | LAB-UC10 Hapus Data Peralatan |
|---|---|
| Aktor | Petugas Laboratorium |
| Tujuan | Data peralatan terhapus sebagai bentuk khusus dari pengelolaan data peralatan |
| Deskripsi | Petugas memilih data peralatan, mengonfirmasi penghapusan, dan sistem menghapus data tersebut; langkah bersama mengikuti Tabel skenario LAB-UC02 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Petugas memilih bentuk pengelolaan hapus (langkah bersama LAB-UC02 langkah 1 sampai 3; lihat Tabel skenario LAB-UC02) |  |
| 2. Petugas memilih data peralatan yang akan dihapus |  |
|  | 3. Sistem memeriksa peralatan tidak sedang dipinjam dan tidak memiliki pengajuan aktif |
| 4. Petugas mengonfirmasi penghapusan |  |
|  | 5. Sistem menghapus data peralatan |
|  | 6. Sistem menampilkan konfirmasi penghapusan |
| **Skenario Alternative** | |
| 7. Peralatan sedang dipinjam atau memiliki pengajuan aktif (cabang dari langkah 3) |  |
|  | 8. Sistem menolak penghapusan |
|  | 9. Sistem menampilkan pesan peralatan masih terpakai |
| Skenario Akhir | Use case selesai jika data peralatan terhapus; jika peralatan sedang dipinjam atau memiliki pengajuan aktif, data tidak terhapus. |

Keterangan tabel: use case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data peralatan terhapus, dengan syarat peralatan tidak sedang dipinjam dan tidak memiliki pengajuan aktif. Langkah bersama mengikuti Tabel skenario LAB-UC02.

### Tabel 5.10 Skenario Use Case LAB-UC06 Proses Keputusan Peminjaman

| Nama use case | LAB-UC06 Proses Keputusan Peminjaman |
|---|---|
| Aktor | Petugas Laboratorium |
| Tujuan | Pengajuan peminjaman mendapat keputusan setuju atau tolak |
| Deskripsi | Petugas memeriksa pengajuan yang berstatus Menunggu Keputusan, menetapkan persetujuan atau penolakan, dan sistem menyampaikan keputusan |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Petugas membuka daftar pengajuan yang berstatus Menunggu Keputusan |  |
|  | 2. Sistem menampilkan daftar pengajuan tersebut |
| 3. Petugas memilih pengajuan |  |
|  | 4. Sistem menampilkan data pengajuan terpilih |
| 5. Petugas menetapkan persetujuan |  |
|  | 6. Sistem mengubah status pengajuan menjadi Disetujui |
|  | 7. Sistem menampilkan konfirmasi persetujuan |
| **Skenario Alternative** | |
| 8. Petugas menetapkan penolakan (cabang dari langkah 5) |  |
|  | 9. Sistem mengubah status pengajuan menjadi Ditolak |
|  | 10. Sistem menampilkan konfirmasi penolakan |
| 11. Pengajuan tidak ditemukan atau statusnya sudah berubah (cabang dari langkah 3) |  |
|  | 12. Sistem menampilkan pesan pengajuan tidak dapat diproses |
| Skenario Akhir | Use case selesai jika pengajuan berstatus Disetujui atau Ditolak; jika pengajuan tidak dapat diproses, status tidak berubah. |

Keterangan tabel: use case berdiri sendiri tanpa relasi antar use case; satu-satunya asosiasi adalah Petugas Laboratorium ke LAB-UC06.

### Tabel 5.11 Skenario Use Case LAB-UC07 Lihat Laporan Peminjaman

| Nama use case | LAB-UC07 Lihat Laporan Peminjaman |
|---|---|
| Aktor | Kepala Laboratorium |
| Tujuan | Laporan peminjaman dapat dilihat oleh kepala laboratorium |
| Deskripsi | Kepala Laboratorium membuka fungsi laporan dan melihat laporan peminjaman pada periode yang dipilih |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Kepala Laboratorium membuka fungsi Lihat Laporan Peminjaman |  |
|  | 2. Sistem menampilkan daftar periode laporan |
| 3. Kepala Laboratorium memilih periode |  |
|  | 4. Sistem menampilkan laporan peminjaman periode tersebut |
| **Skenario Alternative** | |
| 5. Tidak ada data peminjaman pada periode yang dipilih (cabang dari langkah 4) |  |
|  | 6. Sistem menampilkan pesan tidak ada data peminjaman pada periode tersebut |
| Skenario Akhir | Use case selesai jika laporan periode yang dipilih ditampilkan; jika tidak ada data, use case selesai dengan pesan tersebut. |

Keterangan tabel: satu-satunya use case Kepala Laboratorium. Tabel ini berdiri sendiri dan tidak memuat langkah include, extend, generalization, atau realization.

### Tabel 5.12 Skenario Use Case LAB-UC11 Catat Pengembalian Peralatan

| Nama use case | LAB-UC11 Catat Pengembalian Peralatan |
|---|---|
| Aktor | Petugas Laboratorium |
| Tujuan | Pengembalian tercatat dan status peminjaman serta kondisi peralatan terbarui |
| Deskripsi | Petugas memilih peminjaman yang akan dikembalikan, mengonfirmasi alat yang kembali, dan menyimpan pencatatan. Prasyarat: peminjaman berstatus Dipinjam |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Petugas memilih peminjaman yang akan dikembalikan |  |
|  | 2. Sistem menampilkan data peminjaman terpilih beserta statusnya |
| 3. Petugas mengonfirmasi alat yang kembali dan jumlahnya |  |
|  | 4. Sistem menampung konfirmasi petugas |
|  | 5. Sistem memeriksa status peminjaman harus Dipinjam |
|  | 6. Sistem menjalankan Periksa Kondisi Peralatan, include LAB-UC12 (lihat Tabel skenario LAB-UC12) |
| 7. Petugas menyimpan pencatatan pengembalian |  |
|  | 8. Sistem menyimpan tanggal kembali dan kondisi peralatan |
|  | 9. Sistem mengubah status peminjaman menjadi Selesai |
| 10. Petugas melihat konfirmasi |  |
|  | 11. Sistem menampilkan ringkasan pengembalian |
| **Skenario Alternative** | |
| 12. Status bukan Dipinjam (cabang dari langkah 5) |  |
|  | 13. Sistem menolak pencatatan |
|  | 14. Sistem menampilkan status peminjaman saat ini |
| 15. Kondisi Rusak Ringan atau Rusak Berat dicatat pada Periksa Kondisi Peralatan (cabang dari langkah 6) |  |
|  | 16. Sistem menandai kondisi tersebut pada data peralatan |
|  | 17. Sistem melanjutkan pencatatan pengembalian ke langkah 7 tanpa denda |
| 18. Jumlah alat yang kembali tidak sesuai (cabang dari langkah 3) |  |
|  | 19. Sistem meminta petugas memeriksa kembali isian sebelum penyimpanan |
| Skenario Akhir | Use case selesai jika pengembalian tercatat dengan tanggal kembali dan kondisi peralatan serta status peminjaman menjadi Selesai; jika status bukan Dipinjam, tidak ada pengembalian baru yang tercatat dan status peminjaman tidak berubah; jika jumlah alat tidak sesuai, pencatatan tidak disimpan sampai jumlah sesuai atau dikoreksi. |

Keterangan tabel: use case ini direalisasikan oleh collaboration LAB-CO02 Catat Pengembalian Peralatan, tanpa langkah kegiatan sendiri. Include LAB-UC12 menjadi langkah 6. Keterlambatan dan denda belum dimodelkan pada pertemuan ini dan tidak menimbulkan aturan tambahan pada tabel ini.

### Tabel 5.13 Skenario Use Case LAB-UC12 Periksa Kondisi Peralatan

| Nama use case | LAB-UC12 Periksa Kondisi Peralatan |
|---|---|
| Aktor | Petugas Laboratorium (berjalan di dalam LAB-UC11 Catat Pengembalian Peralatan) |
| Tujuan | Kondisi peralatan yang dikembalikan terperiksa dan tercatat |
| Deskripsi | Sistem memeriksa kondisi peralatan yang dikembalikan dan mencatat nilainya sebagai bagian dari pencatatan pengembalian. Use case ini berjalan di dalam LAB-UC11 melalui include dan tidak mempunyai asosiasi langsung dengan aktor pada diagram; pemilihan nilai kondisi oleh petugas terjadi melalui alur LAB-UC11 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Alur pengembalian LAB-UC11 memanggil Periksa Kondisi Peralatan dengan peralatan yang dikembalikan |  |
|  | 2. Sistem menampilkan pilihan kondisi, yaitu Baik, Rusak Ringan, atau Rusak Berat |
| 3. Petugas memilih nilai kondisi peralatan |  |
|  | 4. Sistem mencatat nilai kondisi pada data pengembalian |
| **Skenario Alternative** | |
| 5. Petugas belum memilih nilai kondisi (cabang dari langkah 4) |  |
|  | 6. Sistem meminta petugas memilih nilai kondisi sebelum pencatatan disimpan |
| Skenario Akhir | Use case selesai jika nilai kondisi peralatan tercatat pada data pengembalian; jika nilai belum dipilih, pencatatan tidak disimpan sampai nilai dipilih. |

Keterangan tabel: use case yang disertakan oleh LAB-UC11 (include). Pada diagram tidak ada asosiasi langsung dari aktor ke LAB-UC12.
