# Telaah Skenario Pertemuan 6: Activity Diagram Studi Kasus LAB

Tanggal: 04-11-2026 | NIM: 2406085 | Versi: v01
Kasus: Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus
Acuan: Jobsheet Praktikum Pertemuan 6 (Revisi), tabel skenario Pertemuan 5 (`P05_2406085_LAB_skenario_v01.md`)
Diagram: `04_model_analisis/P06/LAB/` (7 berkas `.drawio` dan 7 `.png`, semuanya v01)

## 1. Acuan telaah

- Masukan activity diagram adalah tabel skenario Pertemuan 5, bukan diagram use case. Setiap action harus dapat ditunjuk langkah sumbernya.
- Tujuh use case utama mendapat satu activity masing-masing: LAB-UC01, LAB-UC02, LAB-UC03, LAB-UC05, LAB-UC06, LAB-UC07, dan LAB-UC11. LAB-UC04 dan LAB-UC12 menjadi action include; LAB-UC08, LAB-UC09, dan LAB-UC10 menjadi tiga cabang varian pada Activity Kelola Data Peralatan.
- Telaah ini membandingkan setiap activity dengan tabel P05 dan dengan Gambar 6.1 sampai 6.7 pada jobsheet. Diagram P04 dan dokumen P05 tidak diubah.
- Hasil hitung unsur diperoleh dari pembacaan ulang berkas `.drawio` (bukan dari catatan sumber).

## 2. Ringkasan tujuh activity

| Activity | Berkas (slug) | Use case sumber | Swimlane | Action | Decision | Merge | Fork/Join |
|---|---|---|---|---|---|---|---|
| Lihat Ketersediaan Peralatan | lihat_ketersediaan | LAB-UC01 | Peminjam, Sistem | 3 | 1 | 1 | 0 |
| Kelola Data Peralatan | kelola_data | LAB-UC02, UC08, UC09, UC10 | Petugas Laboratorium, Sistem | 17 | 4 | 1 | 0 |
| Peminjaman | peminjaman | LAB-UC03 (include UC04, extend UC05) | Mahasiswa, Sistem, Petugas Laboratorium | 7 | 2 | 2 | 0 |
| Cetak Bukti Pengajuan | cetak_bukti | LAB-UC05 | Mahasiswa, Sistem | 4 | 1 | 1 | 0 |
| Proses Keputusan Peminjaman | keputusan | LAB-UC06 | Petugas Laboratorium, Sistem | 6 | 2 | 1 | 0 |
| Pengembalian | pengembalian | LAB-UC11 (include UC12) | Mahasiswa, Sistem, Petugas Laboratorium | 7 | 1 | 1 | 1 pasang |
| Lihat Laporan Peminjaman | laporan | LAB-UC07 | Kepala Laboratorium, Sistem | 5 | 1 | 1 | 0 |

Semua diagram memiliki satu initial node dan satu activity final node.

## 3. Keterlacakan action ke tabel skenario P05

Keterangan kolom Padanan: **Sama** = bunyi dan urutan sesuai langkah P05; **Sebagian** = ada padanan tetapi bunyi, urutan, atau cakupan berbeda; **Baru** = tidak ada pada P05.

### 3.1 Activity Lihat Ketersediaan Peralatan (LAB-UC01, Tabel 5.3)

| Action / decision | Swimlane | Langkah sumber | Padanan |
|---|---|---|---|
| Membuka fungsi Lihat Ketersediaan Peralatan | Peminjam | LAB-UC01 langkah 1 | Sama |
| Menampilkan daftar peralatan beserta status ketersediaannya | Sistem | LAB-UC01 langkah 2 | Sama |
| Decision Peralatan tersedia? [tidak tersedia] / [tersedia] | Sistem | LAB-UC01 langkah 3 (cabang dari langkah 2) | Sama |
| Menampilkan pesan tidak ada peralatan yang tersedia | Sistem | LAB-UC01 langkah 4 | Sama |

### 3.2 Activity Kelola Data Peralatan (LAB-UC02, UC08, UC09, UC10, Tabel 5.6 sampai 5.9)

| Action / decision | Swimlane | Langkah sumber | Padanan |
|---|---|---|---|
| Membuka fungsi Kelola Data Peralatan | Petugas | LAB-UC02 langkah 1 | Sama |
| Menampilkan daftar data peralatan | Sistem | LAB-UC02 langkah 2 | Sama |
| Memilih bentuk pengelolaan (tambah, ubah, atau hapus) | Petugas | LAB-UC02 langkah 3 | Sama |
| Decision Bentuk pengelolaan yang dipilih? [tambah] [ubah] [hapus] | Sistem | Generalization LAB-UC08, UC09, UC10 ke LAB-UC02 | Sama |
| Menampilkan formulir data peralatan baru | Sistem | LAB-UC08 langkah 2 | Sama |
| Mengisi data peralatan baru | Petugas | LAB-UC08 langkah 3 | Sama |
| Memilih data peralatan yang akan diubah | Petugas | LAB-UC09 langkah 2 | Sama |
| Menampilkan data peralatan saat ini | Sistem | LAB-UC09 langkah 3 | Sama |
| Decision Data peralatan ditemukan? | Sistem | LAB-UC09 langkah 9 (cabang dari langkah 2) | Sebagian: pada P05 pemeriksaan terjadi sebelum langkah 3 |
| Mengubah data peralatan | Petugas | LAB-UC09 langkah 4 | Sama |
| Menampilkan pesan data peralatan tidak ditemukan | Sistem | LAB-UC09 langkah 10 | Sama |
| Memilih data peralatan yang akan dihapus | Petugas | LAB-UC10 langkah 2 | Sama |
| Memeriksa peralatan tidak sedang dipinjam dan tidak memiliki pengajuan aktif | Sistem | LAB-UC10 langkah 3 | Sama |
| Decision Syarat penghapusan terpenuhi? | Sistem | LAB-UC10 langkah 7 (cabang dari langkah 3) | Sama |
| Mengonfirmasi penghapusan | Petugas | LAB-UC10 langkah 4 | Sama |
| Menolak penghapusan dan menampilkan pesan peralatan masih terpakai | Sistem | LAB-UC10 langkah 8 dan 9 | Sama (dua respon digabung) |
| Memeriksa kelengkapan dan keabsahan data | Sistem | LAB-UC02 langkah 6 | Sama |
| Decision Data lengkap dan sah? | Sistem | LAB-UC02 langkah 10 (cabang dari langkah 6) | Sama |
| Menyimpan perubahan | Petugas | LAB-UC02 langkah 7 | Sama |
| Menyimpan perubahan dan menampilkan konfirmasi | Sistem | LAB-UC02 langkah 8 dan 9 | Sama (dua respon digabung) |
| Menolak penyimpanan dan menampilkan pesan kesalahan data | Sistem | LAB-UC02 langkah 11 dan 12 | Sama (dua respon digabung) |

### 3.3 Activity Peminjaman (LAB-UC03, Tabel 5.1; include UC04, extend UC05)

| Action / decision | Swimlane | Langkah sumber | Padanan |
|---|---|---|---|
| Mengisi formulir pengajuan peminjaman | Mahasiswa | LAB-UC03 langkah 3 | Sebagian: pada P05 langkah 3 terjadi setelah Periksa Ketersediaan (langkah 2) |
| Menyimpan data pengajuan peminjaman | Sistem | LAB-UC03 langkah 7 | Sebagian: pada P05 didahului pemeriksaan kelengkapan, ringkasan, dan pengiriman (langkah 4 sampai 6) |
| Periksa Ketersediaan (dari LAB-UC04) | Sistem | LAB-UC03 langkah 2 (include); LAB-UC04 langkah 1 sampai 4 | Sebagian: urutannya berbeda dari P05 |
| Decision Peralatan tersedia? | Sistem | LAB-UC03 langkah 9 (cabang dari langkah 2); LAB-UC04 langkah 5 dan 6 | Sama |
| Menerima pemberitahuan pengajuan tidak terpenuhi | Mahasiswa | LAB-UC03 langkah 10 | Sebagian: pada P05 langkah ini adalah respon Sistem |
| Memproses keputusan peminjaman | Petugas | LAB-UC06 (Tabel 5.10) | Sebagian: langkah milik use case lain; tidak ada pada tabel LAB-UC03 |
| Mencatat hasil akhir pengajuan | Sistem | LAB-UC03 langkah 7 dan 8 | Sebagian: tidak ada langkah berbunyi sama |
| Decision Mahasiswa memilih cetak bukti? [ya, memilih cetak] / [tidak] | Sistem | LAB-UC03 langkah 14 (extend; condition [mahasiswa memilih cetak]; extension point Bukti pengajuan tersedia) | Sama (condition identik) |
| Cetak Bukti Pengajuan (dari LAB-UC05) | Mahasiswa | LAB-UC03 langkah 14 dan 15; LAB-UC05 | Sama |

### 3.4 Activity Cetak Bukti Pengajuan (LAB-UC05, Tabel 5.5)

| Action / decision | Swimlane | Langkah sumber | Padanan |
|---|---|---|---|
| Decision Mahasiswa memilih cetak bukti? | Sistem | LAB-UC05 langkah 1; condition extend LAB-UC03 | Sebagian: P05 menaruh pembatalan pada langkah 5 (cabang dari langkah 3) |
| Menampilkan bukti pengajuan dengan nomor pengajuan dan status Menunggu Keputusan | Sistem | LAB-UC05 langkah 2 | Sama |
| Mengonfirmasi pencetakan | Mahasiswa | LAB-UC05 langkah 3 | Sama |
| Mencetak bukti pengajuan | Sistem | LAB-UC05 langkah 4 | Sama |
| Menutup konfirmasi tanpa mencetak bukti dan pengajuan tetap tersimpan | Sistem | LAB-UC05 langkah 6 | Sebagian: pada P05 didahului langkah 5 (Mahasiswa membatalkan pencetakan) |

### 3.5 Activity Proses Keputusan Peminjaman (LAB-UC06, Tabel 5.10)

| Action / decision | Swimlane | Langkah sumber | Padanan |
|---|---|---|---|
| Membuka daftar pengajuan yang berstatus Menunggu Keputusan | Petugas | LAB-UC06 langkah 1 | Sama |
| Menampilkan daftar pengajuan yang berstatus Menunggu Keputusan | Sistem | LAB-UC06 langkah 2 | Sama |
| Decision Pengajuan dapat diproses? | Sistem | LAB-UC06 langkah 11 (cabang dari langkah 3) | Sebagian: pada P05 pemeriksaan terjadi setelah petugas memilih pengajuan |
| Memilih pengajuan dan menetapkan persetujuan atau penolakan | Petugas | LAB-UC06 langkah 3 dan 5 | Sebagian: dua aksi petugas digabung; langkah 4 (Sistem menampilkan data pengajuan terpilih) tidak digambar |
| Menampilkan pesan pengajuan tidak dapat diproses | Sistem | LAB-UC06 langkah 12 | Sama |
| Decision Pengajuan disetujui? | Sistem | LAB-UC06 langkah 5 dan 8 | Sama |
| Mengubah status pengajuan menjadi Disetujui dan menampilkan konfirmasi | Sistem | LAB-UC06 langkah 6 dan 7 | Sama (dua respon digabung) |
| Mengubah status pengajuan menjadi Ditolak dan menampilkan konfirmasi penolakan | Sistem | LAB-UC06 langkah 9 dan 10 | Sama (dua respon digabung) |

### 3.6 Activity Pengembalian (LAB-UC11, Tabel 5.12; include UC12, Tabel 5.13)

| Action / decision | Swimlane | Langkah sumber | Padanan |
|---|---|---|---|
| Menyerahkan peralatan yang dipinjam | Mahasiswa | Tidak ada langkah Mahasiswa pada LAB-UC11; konteks langkah 3 | Sebagian: tabel P05 hanya memuat aksi Petugas |
| Catat Pengembalian Peralatan (LAB-UC11) | Petugas | LAB-UC11 langkah 1 sampai 5 | Sebagian: beberapa langkah diringkas menjadi satu action bernama use case |
| Fork | Petugas | Tidak ada | Baru (ditetapkan jobsheet untuk melatih fork dan join) |
| Periksa Kondisi Peralatan (dari LAB-UC12): kondisi fisik | Petugas | LAB-UC11 langkah 6 (include); LAB-UC12 langkah 1 sampai 4 | Sama |
| Periksa kelengkapan aksesori peralatan (unsur proses baru) | Petugas | Tidak ada | Baru, sudah diberi keterangan pada action |
| Join | Petugas | Tidak ada | Baru, berpasangan dengan fork |
| Decision Kondisi peralatan baik dan lengkap? | Sistem | LAB-UC11 langkah 15 sampai 17; LAB-UC12 nilai kondisi | Sebagian: P05 memakai tiga nilai (Baik, Rusak Ringan, Rusak Berat); guard "lengkap" berasal dari proses baru |
| Perbarui status peralatan menjadi tersedia | Sistem | Tidak ada. LAB-UC11 langkah 9 mengubah status peminjaman menjadi Selesai | Baru |
| Catat kerusakan atau kekurangan dan jadwalkan perbaikan | Petugas | LAB-UC11 langkah 15 dan 16 (kondisi rusak ditandai Sistem) | Sebagian: "jadwalkan perbaikan" tidak ada pada P05 |
| Menutup transaksi peminjaman | Sistem | LAB-UC11 langkah 8, 9, dan 11 | Sebagian |

### 3.7 Activity Lihat Laporan Peminjaman (LAB-UC07, Tabel 5.11)

| Action / decision | Swimlane | Langkah sumber | Padanan |
|---|---|---|---|
| Membuka fungsi Lihat Laporan Peminjaman | Kepala Laboratorium | LAB-UC07 langkah 1 | Sama |
| Menampilkan daftar periode laporan | Sistem | LAB-UC07 langkah 2 | Sama |
| Memilih periode laporan | Kepala Laboratorium | LAB-UC07 langkah 3 | Sama |
| Menampilkan laporan peminjaman periode yang dipilih | Sistem | LAB-UC07 langkah 4 | Sama |
| Decision Ada data peminjaman? [ada] / [tidak ada] | Sistem | LAB-UC07 langkah 5 (cabang dari langkah 4) | Sama |
| Menampilkan pesan tidak ada data peminjaman pada periode tersebut | Sistem | LAB-UC07 langkah 6 | Sama |

## 4. Temuan telaah

Diagram mahasiswa sesuai dengan Gambar 6.1 sampai 6.7 pada jobsheet. Temuan berikut adalah selisih antara rancangan activity pada jobsheet dan tabel skenario P05, sehingga perlu dikonfirmasi ke dosen sebelum dianggap kesalahan.

1. **Urutan Periksa Ketersediaan.** Pada Tabel 5.1 langkah 2, Periksa Ketersediaan terjadi sebelum peminjam mengisi data (langkah 3). Pada Activity Peminjaman, pengisian formulir dan penyimpanan data mendahuluinya.
2. **Memproses keputusan peminjaman pada alur LAB-UC03.** Langkah ini milik LAB-UC06 dan dijalankan Petugas Laboratorium; tabel LAB-UC03 tidak memuat langkah petugas.
3. **Mahasiswa pada Activity Pengembalian.** Aktor LAB-UC11 pada P05 hanya Petugas Laboratorium; action "Menyerahkan peralatan yang dipinjam" tidak punya langkah sumber.
4. **Guard Kondisi peralatan.** P05 memakai tiga nilai kondisi, sedangkan activity memakai dua guard. Guard "lengkap" bergantung pada unsur proses baru (aksesori).
5. **Action tanpa padanan pada P05.** "Perbarui status peralatan menjadi tersedia" dan "jadwalkan perbaikan" tidak ada pada tabel LAB-UC11 atau LAB-UC12. Keterlambatan dan denda juga belum dimodelkan pada P05.
6. **Cabang [tidak] pada Activity Cetak Bukti.** Activity menggambar [tidak] dari decision awal, sedangkan Tabel 5.5 menempatkan pembatalan setelah konfirmasi (langkah 5) dan menyatakan bahwa bila cetak tidak dipilih, LAB-UC05 tidak berjalan.
7. **Activity Proses Keputusan.** Dua aksi petugas (langkah 3 dan 5) digabung, langkah 4 tidak digambar, dan pemeriksaan "dapat diproses" ditempatkan sebelum pemilihan pengajuan.
8. **Alternatif P05 yang tidak digambar.** LAB-UC03 isian tidak lengkap (langkah 11 sampai 13); LAB-UC11 status bukan Dipinjam (langkah 12 sampai 14) dan jumlah alat tidak sesuai (langkah 18 dan 19); LAB-UC12 nilai kondisi belum dipilih (langkah 5 dan 6).
9. **Cabang [hapus].** Setelah merge, cabang hapus ikut melewati "Memeriksa kelengkapan dan keabsahan data" (LAB-UC02 langkah 6), padahal LAB-UC10 memiliki pemeriksaannya sendiri pada langkah 3.

## 5. Catatan perbandingan tugas mandiri (Activity Proses Keputusan Peminjaman)

Jobsheet Langkah 10 meminta mahasiswa menggambar tanpa melihat pembanding, memeriksa dengan checklist, lalu membandingkan dan mencatat setiap perbedaan beserta perbaikannya.

- Yang tersedia di repositori hanya berkas final `P06_2406085_LAB_activity_keputusan_v01`. Unsur dan alurnya sama dengan Gambar 6.6 pada jobsheet.
- Gambar pertama (sebelum membuka pembanding) dan catatan perbedaannya tidak tersimpan pada metadata maupun logbook, sehingga bagian ini belum dapat dinyatakan lengkap.
- Perbandingan yang dapat dilakukan dari berkas yang ada adalah diagram final terhadap Tabel 5.10 (lihat Bagian 3.5 dan temuan 7).

Tabel berikut disediakan untuk diisi mahasiswa dari gambar pertamanya.

| Unsur | Gambar pertama mahasiswa | Pembanding (jobsheet) | Perbedaan | Perbaikan |
|---|---|---|---|---|
| Decision Pengajuan dapat diproses? | [diisi mahasiswa] | Setelah daftar ditampilkan, sebelum pemilihan | [diisi mahasiswa] | [diisi mahasiswa] |
| Aksi petugas memilih dan menetapkan | [diisi mahasiswa] | Satu action gabungan | [diisi mahasiswa] | [diisi mahasiswa] |
| Decision Pengajuan disetujui? dan guard | [diisi mahasiswa] | [disetujui] dan [ditolak] | [diisi mahasiswa] | [diisi mahasiswa] |
| Cabang tidak dapat diproses | [diisi mahasiswa] | Berakhir langsung pada activity final node | [diisi mahasiswa] | [diisi mahasiswa] |

## 6. Checklist hasil pemeriksaan

- ✔️ Satu initial node dan satu activity final node pada ketujuh diagram; tidak ada action yang terputus dan tidak ada panah tanpa ujung.
- ✔️ Setiap decision memiliki guard pada semua alur keluarnya (12 decision pada ketujuh diagram).
- ✔️ Setiap cabang kembali melalui merge atau bermuara ke activity final node dengan keadaan akhir yang jelas.
- ✔️ Fork berpasangan dengan join (satu pasang, pada Activity Pengembalian); proses paralel disatukan oleh join, bukan merge.
- ✔️ Setiap action berada pada swimlane yang aktornya sesuai dengan tabel; pusat setiap action berada di dalam lane induknya. Satu catatan: "Menerima pemberitahuan pengajuan tidak terpenuhi" berada pada swimlane Mahasiswa, sedangkan P05 menuliskannya sebagai respon Sistem (temuan 1 sampai 3 dan Bagian 3.3).
- ⚠️ Keterlacakan ke tabel P05: dari 63 baris keterlacakan (action, decision, fork, dan join), 43 berstatus Sama, 16 Sebagian, dan 4 Baru (Bagian 3 dan 4).
- ✔️ Include digambar sebagai action wajib (Periksa Ketersediaan, Periksa Kondisi Peralatan); extend digambar sebagai cabang bersyarat dengan condition [ya, memilih cetak].
- ✔️ Unsur proses baru (Periksa kelengkapan aksesori peralatan) diberi keterangan pada action dan tidak diklaim berasal dari P03, P04, atau P05.
- ✔️ Collaboration tidak digambar sebagai action maupun swimlane.
- ✔️ Kepala Laboratorium tidak muncul pada Activity Peminjaman dan Pengembalian; hanya pada Activity Lihat Laporan Peminjaman.
- ✔️ Ketujuh activity tersedia sebagai berkas v01 beserta PNG; LAB-UC04, LAB-UC12, LAB-UC08, LAB-UC09, dan LAB-UC10 tidak dibuatkan activity tersendiri.
- ⚠️ Nama aktor memakai Petugas Laboratorium dan Kepala Laboratorium sesuai jobsheet P04, tetapi berkas `P04_2406085_LAB_usecase_v01.drawio` masih memakai "Petugas Laboran" dan "Kepala Laboran" (pekerjaan P04 v02).
- ✔️ Nomor versi berkas sumber dan ekspor sama (v01). Kesesuaian visual PNG LAB terhadap sumber belum dibandingkan satu per satu.
