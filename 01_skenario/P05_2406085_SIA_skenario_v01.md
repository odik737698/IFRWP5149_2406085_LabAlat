# Lembar Skenario Pertemuan 5: Tugas SIA (Layanan Hasil Studi)

Tanggal: 28-10-2026 | NIM: 2406085 | Versi: v01
Kasus: Sistem Informasi Akademik, melanjutkan kasus SIA Pertemuan 4
Dokumen tabel (draw.io, satu halaman per tabel): `04_model_analisis/P05/SIA/P05_2406085_SIA_skenario_v01.drawio`
Isi tabel yang sama ada pada bagian 5 di bawah.

## 1. Acuan

- Diagram acuan: diagram SIA Pertemuan 4 (`04_model_analisis/P04/SIA/P04_2406085_SIA_usecase_v01.drawio`): 5 aktor, 13 use case, 2 collaboration, 18 hubungan. Diagram tidak diubah. Tidak ada use case, aktor, atau kebutuhan baru; acuan kebutuhan SIA-R07 sampai SIA-R12.
- Hierarki yang diterapkan: generalization aktor (Mahasiswa dan Dosen ke Civitas Akademika) pada SIA-UC07, dan generalization use case (SIA-UC11, SIA-UC12, SIA-UC13 ke SIA-UC10).
- Collaboration SIA-CO01 disebut pada keterangan tabel SIA-UC08 dan SIA-CO02 pada keterangan tabel SIA-UC09, tanpa langkah kegiatan sendiri.

Indeks tugas (Tabel 5.14):

| ID | Nama use case | Aktor | Catatan pemetaan |
|---|---|---|---|
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | Satu tabel atas nama Civitas Akademika; berlaku untuk Mahasiswa dan Dosen |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | Prasyarat dosen pengampu; alternatif nilai di luar rentang yang sah ditolak; direalisasikan SIA-CO01 |
| SIA-UC09 | Lihat KHS | Mahasiswa | Hanya nilai yang sudah dipublikasikan yang ditampilkan; direalisasikan SIA-CO02 |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | Skenario umum; langkah bersama dirujuk UC11, UC12, UC13 |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik | Khusus dari UC10; data mahasiswa baru tersimpan |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik | Khusus dari UC10; data mahasiswa berubah |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik | Khusus dari UC10; data mahasiswa terhapus; syarat tanpa data akademik aktif |

## 2. Checklist hasil pemeriksaan (7 tabel)

Pemeriksaan otomatis dilakukan dengan membaca ulang berkas .drawio hasil.

- ✔️ Seluruh field terisi pada 7 tabel.
- ✔️ Langkah berurutan, satu aksi per langkah, penomoran berlanjut dari Skenario Normal ke Skenario Alternative tanpa pengulangan nomor.
- ✔️ Kolom Kegiatan berisi aksi aktor dan kolom Respon sistem berisi tanggapan sistem. Mengikuti gaya Tabel 5.1, baris syarat cabang alternatif ditulis pada kolom Kegiatan.
- ✔️ Data dan status disebut eksplisit (ditinjau manual): status Belum dipublikasikan dan Dipublikasikan, mata kuliah, semester, nilai, serta data akademik aktif.
- ✔️ Generalization aktor: SIA-UC07 ditulis satu kali atas nama Civitas Akademika dengan catatan berlaku untuk Mahasiswa dan Dosen; tidak ada tabel ganda.
- ✔️ Generalization use case: SIA-UC10 memuat perilaku bersama; SIA-UC11, SIA-UC12, SIA-UC13 memuat perilaku pembeda dan merujuk ke Tabel skenario SIA-UC10.
- ✔️ Collaboration disebut pada keterangan tabel SIA-UC08 dan SIA-UC09 tanpa langkah kegiatan sendiri.
- ✔️ Setiap tabel mempunyai Skenario Alternative dan Skenario Akhir.
- ✔️ Nama, ID, dan aktor sama dengan diagram SIA Pertemuan 4.
- ✔️ Berkas diagram P04 tidak diubah; dokumen disimpan dengan nama dan versi yang benar.
- Relasi include dan extend tidak berlaku pada ketujuh tabel ini (SIA-UC03 dan SIA-UC05 tidak termasuk tujuh use case tugas).

## 3. Lembar penelusuran

| Tabel | Use case | Relasi yang ditelusur | Hasil pencocokan |
|---|---|---|---|
| 5.15 | SIA-UC07 Lihat Kalender Akademik | Asosiasi Civitas Akademika ke SIA-UC07 (baris Aktor); generalization Mahasiswa dan Dosen ke Civitas Akademika (catatan berlaku) | Cocok |
| 5.16 | SIA-UC08 Input Nilai Mata Kuliah | Asosiasi khusus Dosen ke SIA-UC08 (baris Aktor); realization SIA-CO01 ke SIA-UC08 (keterangan); prasyarat dosen pengampu dan cabang nilai di luar rentang sesuai aturan tugas | Cocok |
| 5.17 | SIA-UC09 Lihat KHS | Asosiasi Mahasiswa ke SIA-UC09 (baris Aktor); realization SIA-CO02 ke SIA-UC09 (keterangan); aturan hanya nilai terpublikasi | Cocok |
| 5.18 | SIA-UC10 Kelola Data Mahasiswa | Asosiasi Admin Akademik ke SIA-UC10; generalization SIA-UC11, SIA-UC12, SIA-UC13 ke SIA-UC10 | Cocok |
| 5.19 | SIA-UC11 Tambah Data Mahasiswa | Generalization SIA-UC11 ke SIA-UC10; asosiasi Admin Akademik hanya ke SIA-UC10 | Cocok |
| 5.20 | SIA-UC12 Ubah Data Mahasiswa | Generalization SIA-UC12 ke SIA-UC10 | Cocok |
| 5.21 | SIA-UC13 Hapus Data Mahasiswa | Generalization SIA-UC13 ke SIA-UC10; aturan hapus hanya untuk mahasiswa tanpa data akademik aktif | Cocok |

## 4. Padanan dengan use case description Pertemuan 4

Tabel skenario harus konsisten dengan use case description. Nomor langkah berbeda karena skenario memisahkan satu aksi per langkah; perilakunya sama.

| Use case | Langkah pada description P04 | Langkah pada skenario P05 |
|---|---|---|
| SIA-UC08 | 1 memilih fungsi | 1 sampai 2 |
| SIA-UC08 | 2 memilih mata kuliah, pemeriksaan pengampu | 3 sampai 5 |
| SIA-UC08 | 3 mengisi nilai | 6 |
| SIA-UC08 | 4 memilih simpan, pemeriksaan rentang | 7 sampai 8 |
| SIA-UC08 | 5 menyimpan, status Belum dipublikasikan | 9 |
| SIA-UC08 | 6 konfirmasi | 10 sampai 11 |
| SIA-UC08 | A1 bukan pengampu (langkah 2) | 12 sampai 14, cabang dari langkah 4 |
| SIA-UC08 | A2 nilai di luar rentang (langkah 4) | 15 sampai 18, cabang dari langkah 8 |
| SIA-UC09 | 1 memilih fungsi dan semester | 1 sampai 3 |
| SIA-UC09 | 2 mengambil nilai Dipublikasikan | 4 |
| SIA-UC09 | 3 menampilkan KHS | 5 |
| SIA-UC09 | A1 belum ada nilai dipublikasikan (langkah 2) | 6 sampai 8, cabang dari langkah 4 |

Hasil uji tiga situasi pada berkas kebutuhan P04 tetap berlaku: Situasi B ditelusur ke SIA-UC08 cabang langkah 12 sampai 14, dan Situasi C ditelusur ke SIA-UC13 cabang langkah 7 sampai 9.

## 5. Tujuh tabel skenario

### Tabel 5.15 Skenario Use Case SIA-UC07 Lihat Kalender Akademik

| Nama use case | SIA-UC07 Lihat Kalender Akademik |
|---|---|
| Aktor | Civitas Akademika (berlaku untuk Mahasiswa dan Dosen) |
| Tujuan | Civitas Akademika dapat mengetahui agenda resmi institusi melalui kalender akademik |
| Deskripsi | Civitas Akademika membuka fungsi kalender akademik dan melihat agenda resmi institusi, misalnya awal semester, batas KRS, dan masa ujian. Skenario ditulis satu kali atas nama aktor umum dan berlaku untuk Mahasiswa dan Dosen |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Civitas Akademika membuka fungsi Lihat Kalender Akademik |  |
|  | 2. Sistem menampilkan daftar agenda kalender akademik |
| **Skenario Alternative** | |
| 3. Belum ada agenda kalender akademik yang dapat ditampilkan (cabang dari langkah 2) |  |
|  | 4. Sistem menampilkan pesan belum ada agenda kalender akademik |
| Skenario Akhir | Use case selesai jika daftar agenda kalender akademik ditampilkan; jika belum ada agenda, use case selesai dengan pesan tersebut. |

Keterangan tabel: aktor umum Civitas Akademika berlaku untuk Mahasiswa dan Dosen (generalization aktor). Catatan aktor khusus: tidak ada perbedaan perilaku antara Mahasiswa dan Dosen pada use case ini, sehingga tidak dibuat tabel terpisah. Asosiasi Civitas Akademika ke SIA-UC07 digambar satu kali pada diagram. Dasar langkah: kebutuhan SIA-R07.

### Tabel 5.16 Skenario Use Case SIA-UC08 Input Nilai Mata Kuliah

| Nama use case | SIA-UC08 Input Nilai Mata Kuliah |
|---|---|
| Aktor | Dosen |
| Tujuan | Nilai mata kuliah mahasiswa peserta tercatat oleh dosen pengampu |
| Deskripsi | Dosen memilih mata kuliah yang diampunya, mengisi nilai setiap mahasiswa peserta, dan menyimpan nilai. Prasyarat: dosen adalah pengampu mata kuliah yang dipilih dan masa perkuliahan mata kuliah tersebut telah berakhir |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Dosen membuka fungsi Input Nilai Mata Kuliah |  |
|  | 2. Sistem menampilkan daftar mata kuliah yang diampu dosen tersebut |
| 3. Dosen memilih mata kuliah yang akan dinilai |  |
|  | 4. Sistem memeriksa bahwa dosen adalah pengampu mata kuliah terpilih |
|  | 5. Sistem menampilkan daftar mahasiswa peserta beserta isian nilai |
| 6. Dosen mengisi nilai setiap mahasiswa peserta |  |
| 7. Dosen memilih simpan |  |
|  | 8. Sistem memeriksa bahwa setiap nilai berada dalam rentang yang sah |
|  | 9. Sistem menyimpan nilai dengan status Belum dipublikasikan |
| 10. Dosen melihat konfirmasi penyimpanan |  |
|  | 11. Sistem menampilkan ringkasan nilai yang tersimpan |
| **Skenario Alternative** | |
| 12. Dosen bukan pengampu mata kuliah yang dipilih (cabang dari langkah 4) |  |
|  | 13. Sistem menolak akses ke isian nilai mata kuliah tersebut |
|  | 14. Sistem memberi tahu bahwa dosen bukan pengampu mata kuliah tersebut |
| 15. Nilai di luar rentang yang sah (cabang dari langkah 8) |  |
|  | 16. Sistem menolak penyimpanan |
|  | 17. Sistem menandai isian nilai yang tidak sah |
|  | 18. Sistem meminta dosen mengoreksi isian nilai |
| Skenario Akhir | Use case selesai jika nilai tersimpan dengan status Belum dipublikasikan; jika dosen bukan pengampu atau nilai di luar rentang yang sah, tidak ada nilai yang tersimpan dan data nilai tidak berubah. |

Keterangan tabel: use case ini direalisasikan oleh collaboration SIA-CO01 Input Nilai Mata Kuliah. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. Asosiasi Dosen ke SIA-UC08 adalah asosiasi khusus milik Dosen (tidak diwariskan dari Civitas Akademika). Dasar langkah: kebutuhan SIA-R08. Rentang nilai yang sah belum ditetapkan pada tugas ini (pertanyaan terbuka no. 3).

### Tabel 5.17 Skenario Use Case SIA-UC09 Lihat KHS

| Nama use case | SIA-UC09 Lihat KHS |
|---|---|
| Aktor | Mahasiswa |
| Tujuan | Mahasiswa dapat melihat Kartu Hasil Studi untuk semester yang nilainya sudah dipublikasikan |
| Deskripsi | Mahasiswa memilih semester dan melihat KHS yang hanya memuat nilai yang sudah dipublikasikan |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Mahasiswa membuka fungsi Lihat KHS |  |
|  | 2. Sistem menampilkan daftar semester |
| 3. Mahasiswa memilih semester |  |
|  | 4. Sistem mengambil nilai semester tersebut yang berstatus Dipublikasikan |
|  | 5. Sistem menampilkan KHS semester terpilih yang hanya memuat nilai yang sudah dipublikasikan |
| **Skenario Alternative** | |
| 6. Semester terpilih belum memiliki nilai yang dipublikasikan (cabang dari langkah 4) |  |
|  | 7. Sistem menyatakan KHS semester tersebut belum tersedia |
|  | 8. Sistem tidak menampilkan nilai apa pun |
| Skenario Akhir | Use case selesai jika KHS semester terpilih ditampilkan dengan nilai yang sudah dipublikasikan; jika semester belum memiliki nilai yang dipublikasikan, tidak ada KHS atau nilai yang ditampilkan. |

Keterangan tabel: use case ini direalisasikan oleh collaboration SIA-CO02 Lihat KHS. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. Nilai yang belum dipublikasikan tidak pernah ditampilkan. Dasar langkah: kebutuhan SIA-R09. Tafsir publikasi per semester masih pertanyaan terbuka no. 2.

### Tabel 5.18 Skenario Use Case SIA-UC10 Kelola Data Mahasiswa

| Nama use case | SIA-UC10 Kelola Data Mahasiswa |
|---|---|
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa terkelola melalui satu fungsi pengelolaan bersama |
| Deskripsi | Admin Akademik membuka fungsi pengelolaan data mahasiswa, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya masing-masing |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Kelola Data Mahasiswa |  |
|  | 2. Sistem menampilkan daftar data mahasiswa |
| 3. Admin Akademik memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus |  |
|  | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih |
| 5. Admin Akademik mengisi atau mengonfirmasi data mahasiswa |  |
|  | 6. Sistem memeriksa kelengkapan dan keabsahan data |
| 7. Admin Akademik menyimpan perubahan |  |
|  | 8. Sistem menyimpan perubahan data mahasiswa |
|  | 9. Sistem menampilkan konfirmasi penyimpanan |
| **Skenario Alternative** | |
| 10. Data tidak lengkap atau tidak sah (cabang dari langkah 6) |  |
|  | 11. Sistem menolak penyimpanan |
|  | 12. Sistem menampilkan pesan kesalahan data |
| Skenario Akhir | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

Keterangan tabel: use case UMUM bagi SIA-UC11, SIA-UC12, dan SIA-UC13. Tabel ini memuat perilaku bersama; ketiga tabel khusus hanya memuat perilaku pembeda dan merujuk ke tabel ini untuk langkah bersama. Admin Akademik hanya diasosiasikan dengan SIA-UC10 pada diagram.

### Tabel 5.19 Skenario Use Case SIA-UC11 Tambah Data Mahasiswa

| Nama use case | SIA-UC11 Tambah Data Mahasiswa |
|---|---|
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa baru tersimpan sebagai bentuk khusus dari pengelolaan data mahasiswa |
| Deskripsi | Admin Akademik mengisi data mahasiswa baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik memilih bentuk pengelolaan tambah (langkah bersama SIA-UC10 langkah 1 sampai 3; lihat Tabel skenario SIA-UC10) |  |
|  | 2. Sistem menampilkan formulir data mahasiswa baru |
| 3. Admin Akademik mengisi data mahasiswa baru |  |
|  | 4. Sistem memeriksa kelengkapan data |
| 5. Admin Akademik menyimpan data |  |
|  | 6. Sistem menyimpan data mahasiswa baru |
|  | 7. Sistem menampilkan konfirmasi penyimpanan |
| **Skenario Alternative** | |
| 8. Data tidak lengkap (cabang dari langkah 4) |  |
|  | 9. Sistem menolak penyimpanan |
|  | 10. Sistem meminta Admin Akademik melengkapi data |
| Skenario Akhir | Use case selesai jika data mahasiswa baru tersimpan; jika data tidak lengkap, data tidak tersimpan. |

Keterangan tabel: use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa baru tersimpan. Langkah bersama mengikuti Tabel skenario SIA-UC10.

### Tabel 5.20 Skenario Use Case SIA-UC12 Ubah Data Mahasiswa

| Nama use case | SIA-UC12 Ubah Data Mahasiswa |
|---|---|
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa berubah sebagai bentuk khusus dari pengelolaan data mahasiswa |
| Deskripsi | Admin Akademik memilih data mahasiswa, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik memilih bentuk pengelolaan ubah (langkah bersama SIA-UC10 langkah 1 sampai 3; lihat Tabel skenario SIA-UC10) |  |
| 2. Admin Akademik memilih data mahasiswa yang akan diubah |  |
|  | 3. Sistem menampilkan data mahasiswa saat ini |
| 4. Admin Akademik mengubah data mahasiswa |  |
|  | 5. Sistem memeriksa perubahan data |
| 6. Admin Akademik menyimpan perubahan |  |
|  | 7. Sistem menyimpan data mahasiswa yang diubah |
|  | 8. Sistem menampilkan konfirmasi penyimpanan |
| **Skenario Alternative** | |
| 9. Data mahasiswa tidak ditemukan (cabang dari langkah 2) |  |
|  | 10. Sistem menampilkan pesan data mahasiswa tidak ditemukan |
| Skenario Akhir | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak ditemukan, perubahan tidak tersimpan. |

Keterangan tabel: use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa berubah. Langkah bersama mengikuti Tabel skenario SIA-UC10.

### Tabel 5.21 Skenario Use Case SIA-UC13 Hapus Data Mahasiswa

| Nama use case | SIA-UC13 Hapus Data Mahasiswa |
|---|---|
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa terhapus sebagai bentuk khusus dari pengelolaan data mahasiswa |
| Deskripsi | Admin Akademik memilih data mahasiswa, mengonfirmasi penghapusan, dan sistem menghapus data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik memilih bentuk pengelolaan hapus (langkah bersama SIA-UC10 langkah 1 sampai 3; lihat Tabel skenario SIA-UC10) |  |
| 2. Admin Akademik memilih data mahasiswa yang akan dihapus |  |
|  | 3. Sistem memeriksa mahasiswa tidak memiliki data akademik aktif |
| 4. Admin Akademik mengonfirmasi penghapusan |  |
|  | 5. Sistem menghapus data mahasiswa |
|  | 6. Sistem menampilkan konfirmasi penghapusan |
| **Skenario Alternative** | |
| 7. Mahasiswa memiliki data akademik aktif (cabang dari langkah 3) |  |
|  | 8. Sistem menolak penghapusan |
|  | 9. Sistem menampilkan pesan data mahasiswa masih memiliki data akademik aktif |
| Skenario Akhir | Use case selesai jika data mahasiswa terhapus; jika mahasiswa memiliki data akademik aktif, data tidak terhapus dan tidak ada perubahan yang tersimpan. |

Keterangan tabel: use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa terhapus, dengan syarat mahasiswa tidak memiliki data akademik aktif. Langkah bersama mengikuti Tabel skenario SIA-UC10. Definisi data akademik aktif masih pertanyaan terbuka no. 6.
