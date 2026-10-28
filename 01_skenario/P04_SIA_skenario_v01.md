Tugas ini berbeda dari tugas pertemuan sebelumnya. Tugas Pertemuan 2
adalah jadwal kuliah dan tugas Pertemuan 3 adalah pengajuan KRS. Tugas
Pertemuan 4 adalah layanan hasil studi, dengan teknik generalization dan
collaboration yang sama seperti studi kasus, tetapi diterapkan pada skenario
baru tanpa contoh jawaban.
Skenario tugas berikut fiktif untuk praktikum dan berbeda dari tugas
Pertemuan 2 (jadwal kuliah) dan Pertemuan 3 (pengajuan KRS).
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang
dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang
diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu
Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin
Akademik mengelola data mahasiswa: menambah data mahasiswa baru,
mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case
utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh
collaboration yang bersesuaian.

<!-- Batas dan asumsi -->
• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02
(Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap
mempunyai identitas berbeda.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal
semester, batas KRS, masa ujian, dan sejenisnya); jangan
menyamakannya dengan jadwal kuliah pada Pertemuan 2.
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai
yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan
tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan.
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data
akademik aktif. Ketentuan ini fiktif untuk latihan.
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari
Pertemuan 3. Pembayaran dan perancangan basis data berada di luar
tugas ini.

<!-- ====================== LANGKAH 2: AKTOR ====================== -->
## Aktor umum dan aktor khusus

| Aktor | Kedudukan | Tujuan terhadap Sistem |
|---|---|---|
| Civitas Akademika | Umum (general), baru pada Pertemuan 4 | Peran umum bagi warga akademik. Mewariskan fungsinya (melihat kalender akademik) kepada Mahasiswa dan Dosen. |
| Mahasiswa | Khusus dari Civitas Akademika, tetap dari Pertemuan 3 | Melihat kalender akademik (diwarisi dari Civitas Akademika), ditambah asosiasi khususnya sendiri: melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan KRS, dan melihat KHS. |
| Dosen | Khusus dari Civitas Akademika, baru pada Pertemuan 4 | Melihat kalender akademik (diwarisi dari Civitas Akademika), ditambah asosiasi khususnya sendiri: menginput nilai mata kuliah yang diampunya. |
| Admin Akademik | Tetap dari Pertemuan 3 | Mengelola jadwal kuliah dan mengelola data mahasiswa (tambah, ubah, hapus). |
| Dosen Wali | Tetap dari Pertemuan 3 | Memproses keputusan (setuju/tolak) pengajuan KRS. |

Kelima aktor digambar pada diagram kumulatif dan berada di luar batas sistem. Aktor yang baru adalah Civitas Akademika dan Dosen. Mahasiswa, Admin Akademik, dan Dosen Wali tetap dari Pertemuan 3.

Catatan konsistensi terhadap Pertemuan 3: pada skenario P03 tujuan Admin Akademik sempat tertulis "memvalidasi KRS". Pada model ini validasi KRS dijalankan oleh sistem sebagai perilaku yang disertakan `SIA-UC03` (SIA-R04: "Sistem memvalidasi KRS sebagai bagian pengajuan"), sehingga Admin Akademik tidak diasosiasikan dengan `SIA-UC04`. Diagram P03 memang tidak memuat garis tersebut.

<!-- ====================== LANGKAH 2: KATALOG ====================== -->
## Katalog use case gabungan

| ID | Nama Use Case | Aktor Terkait | Sumber Kebutuhan | Tanda | Peran dalam Model |
|---|---|---|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | SIA-R01 | Tetap | Dari Pertemuan 2/3; fungsi Mahasiswa. Dosen tidak memakai fungsi ini, sehingga asosiasi tetap langsung dari Mahasiswa. |
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | Tetap | Dari Pertemuan 2/3; fungsi utama Admin Akademik. |
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03, SIA-R04 | Tetap | Dari Pertemuan 3; menyertakan SIA-UC04; dasar bagi «extend» SIA-UC05. |
| SIA-UC04 | Validasi KRS | (dijalankan sistem) | SIA-R04 | Tetap | Dari Pertemuan 3; perilaku yang disertakan SIA-UC03. |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | SIA-R05 | Tetap | Dari Pertemuan 3; tambahan bersyarat pada SIA-UC03 melalui «extend». |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 | Tetap | Dari Pertemuan 3; fungsi utama Dosen Wali. |
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika (Mahasiswa, Dosen) | SIA-R07 | Baru | Fungsi aktor umum Civitas Akademika. |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08 | Baru | Fungsi utama Dosen; direalisasikan oleh SIA-CO01. |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09 | Baru | Fungsi utama Mahasiswa; direalisasikan oleh SIA-CO02. |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | SIA-R10, SIA-R11 | Baru | Use case UMUM bagi SIA-UC11, SIA-UC12, dan SIA-UC13. |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik (melalui SIA-UC10) | SIA-R11 | Baru | Use case KHUSUS dari SIA-UC10. |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik (melalui SIA-UC10) | SIA-R11 | Baru | Use case KHUSUS dari SIA-UC10. |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik (melalui SIA-UC10) | SIA-R11 | Baru | Use case KHUSUS dari SIA-UC10. |

Penyesuaian nama dari Pertemuan 3 (mengikuti katalog gabungan pada jobsheet Pertemuan 4; ID tidak berubah):

| ID | Nama pada diagram/katalog P03 | Nama pada P04 |
|---|---|---|
| SIA-UC03 | "Pengajuan KRS" (diagram), "Ajukan KRS" (katalog) | Ajukan KRS |
| SIA-UC05 | Cetak bukti pengajuan | Unduh Bukti Pengajuan KRS |
| SIA-UC06 | Proses keputusan pengajuan | Proses Keputusan KRS |

<!-- ====================== LANGKAH 3: GENERALIZATION AKTOR ====================== -->
## Keputusan generalization aktor

- **Mahasiswa adalah bentuk khusus dari Civitas Akademika, dan Dosen adalah bentuk khusus dari Civitas Akademika.** Alasan: keduanya berbagi fungsi yang sama persis, yaitu melihat kalender akademik (SIA-R07).
- **Asosiasi ke SIA-UC07 digambar satu kali, dari Civitas Akademika.** Tidak ada garis yang sama dari Mahasiswa maupun dari Dosen; keduanya mewarisinya.
- **Asosiasi khusus tetap digambar langsung dari aktor khusus.** Mahasiswa: SIA-UC01, SIA-UC03, SIA-UC05, SIA-UC09. Dosen: SIA-UC08. Fungsi-fungsi ini tidak dimiliki aktor khusus lain dan tidak diwariskan ke Civitas Akademika.
- **Arah panah:** ujung segitiga kosong menempel pada Civitas Akademika. Karena Civitas Akademika digambar di tengah, panah Mahasiswa mengarah ke bawah dan panah Dosen mengarah ke atas; keduanya berakhir pada Civitas Akademika.
- **Tidak ada garis P03 yang dipindahkan.** Berbeda dengan kasus LAB, `SIA-UC01` dan `SIA-UC03` hanya dipakai Mahasiswa, sehingga tidak memenuhi syarat dipindahkan ke aktor umum.

Uji tiga pertanyaan keputusan generalization aktor:

| Pertanyaan | Jawaban |
|---|---|
| Apakah dua peran memakai fungsi yang sama persis? | Ya: keduanya melihat kalender akademik. |
| Apakah kesamaan itu bertahan selama sistem berkembang? | Ya: kalender akademik adalah agenda resmi institusi bagi seluruh civitas, bukan kebetulan satu skenario. |
| Apakah nama peran umum membuat diagram lebih jelas? | Ya: satu garis dari Civitas Akademika menggantikan dua garis yang sama. |

Catatan: karena fungsi yang dibagi baru satu, keuntungan generalization terbatas. Dipertahankan karena SIA-R07 menyebut peran "Civitas Akademika" secara eksplisit dan tugas mensyaratkan hierarki aktor. Bila di kemudian hari Dosen dan Mahasiswa tidak lagi berbagi fungsi, hierarki ini perlu ditinjau.

<!-- ====================== LANGKAH 4: GENERALIZATION USE CASE ====================== -->
## Keputusan generalization use case

- **SIA-UC11, SIA-UC12, dan SIA-UC13 adalah bentuk khusus dari SIA-UC10 Kelola Data Mahasiswa.** Alasan: ketiganya sama-sama menghasilkan data mahasiswa yang terkelola (SIA-R11). Perilaku umum yang diwarisi: tujuan mengelola data mahasiswa, aktor Admin Akademik, dan perilaku dasar pengelolaan.
- Admin Akademik cukup diasosiasikan dengan use case umum `SIA-UC10`; tidak digambar garis ke tiga use case khusus.
- `SIA-UC10` tetap bermakna sebagai konsep pengelolaan; ketiga use case khusus tidak sekadar mengganti namanya.

| Use Case Khusus | Perilaku pembeda (satu kalimat) |
|---|---|
| SIA-UC11 Tambah Data Mahasiswa | Menghasilkan data mahasiswa baru yang tersimpan. |
| SIA-UC12 Ubah Data Mahasiswa | Menghasilkan data mahasiswa yang berubah. |
| SIA-UC13 Hapus Data Mahasiswa | Menghasilkan data mahasiswa yang terhapus, hanya untuk mahasiswa yang tidak memiliki data akademik aktif; jika memiliki, penghapusan ditolak dan data tetap. |

<!-- ====================== LANGKAH 5: COLLABORATION ====================== -->
## Collaboration dan realization

| ID | Nama Collaboration (sama dengan nama use case) | Use Case yang Direalisasikan | Kebutuhan |
|---|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08: Input Nilai Mata Kuliah | SIA-R12 |
| SIA-CO02 | Lihat KHS | SIA-UC09: Lihat KHS | SIA-R12 |

Alasan: kedua use case tersebut adalah use case utama layanan hasil studi pada potongan model ini, sehingga realisasinya ditunjukkan secara eksplisit. Collaboration untuk use case lain tidak digambar pada pertemuan ini. Collaboration tidak dihubungkan ke aktor dan tidak diberi ID use case. ID collaboration dicatat pada katalog ini dan pada ID sel di berkas sumber draw.io; label elips hanya memuat nama, sesuai aturan nama sama persis.

<!-- ====================== PERBANDINGAN P03 DAN P04 ====================== -->
## Perbandingan diagram Pertemuan 3 dan Pertemuan 4 (SIA)

| Kelompok | Isi |
|---|---|
| Tetap sama dari Pertemuan 3 | Aktor Mahasiswa, Admin Akademik, Dosen Wali; use case SIA-UC01 sampai SIA-UC06; relasi «include» SIA-UC03 ke SIA-UC04; relasi «extend» SIA-UC05 ke SIA-UC03 dengan condition [mahasiswa memilih unduh] dan extension point Bukti pengajuan tersedia; asosiasi Mahasiswa ke SIA-UC01 dan SIA-UC03; Admin Akademik ke SIA-UC02; Dosen Wali ke SIA-UC06. |
| Berubah karena generalization aktor | Tidak ada. Tidak ada asosiasi P03 yang dipindahkan ke Civitas Akademika karena tidak ada fungsi P03 yang dipakai bersama Dosen. |
| Dilengkapi/disesuaikan pada salinan P04 | (1) Nama pada diagram disamakan dengan katalog: "Pengajuan KRS" menjadi Ajukan KRS, "Cetak bukti pengajuan" menjadi Unduh Bukti Pengajuan KRS, "Proses keputusan pengajuan" menjadi Proses Keputusan KRS. (2) Asosiasi Mahasiswa ke SIA-UC05 ditambahkan karena tercatat pada model analisis P03 tetapi belum tergambar pada diagram P03. (3) Condition dan extension point «extend» dicantumkan sebagai catatan pada diagram. Berkas P03 asli tidak diubah. |
| Ditambah pada Pertemuan 4 | Aktor Civitas Akademika dan Dosen; dua generalization aktor; SIA-UC07, SIA-UC08, SIA-UC09; SIA-UC10 beserta SIA-UC11, SIA-UC12, SIA-UC13 dan tiga generalization use case; collaboration SIA-CO01 dan SIA-CO02 beserta dua relasi realization; asosiasi Civitas Akademika ke SIA-UC07, Mahasiswa ke SIA-UC09, Dosen ke SIA-UC08, Admin Akademik ke SIA-UC10. |

<!-- ====================== LANGKAH 6: USE CASE DESCRIPTION ====================== -->
## Use case description: SIA-UC08 Input Nilai Mata Kuliah

| Elemen | Deskripsi |
|---|---|
| ID dan Nama | SIA-UC08: Input Nilai Mata Kuliah |
| Sumber Kebutuhan | SIA-R08 |
| Tujuan | Nilai mata kuliah mahasiswa peserta tercatat oleh dosen pengampu. |
| Aktor Utama | Dosen (pengampu mata kuliah) |
| Aktor Pendukung | Tidak ada |
| Pemicu | Dosen memilih fungsi input nilai mata kuliah dan menentukan mata kuliah yang akan dinilai. |
| Prasyarat | Dosen telah terautentikasi; dosen adalah pengampu mata kuliah yang dipilih; masa perkuliahan mata kuliah tersebut telah berakhir. |
| Pascakondisi Berhasil | Nilai mahasiswa peserta tersimpan untuk mata kuliah terpilih dengan status Belum dipublikasikan. |
| Pascakondisi Gagal | Tidak ada nilai baru yang tersimpan; data nilai tidak berubah. |
| Include | Tidak ada |
| Extend | Tidak ada |
| Generalization | Tidak ada (bukan use case umum maupun khusus) |
| Collaboration | SIA-CO01: Input Nilai Mata Kuliah |
| Aturan Bisnis / Asumsi | Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai yang diinput belum terpublikasi; KHS hanya menampilkan nilai yang sudah dipublikasikan (SIA-UC09). Penyimpanan bersifat utuh: bila ada nilai tidak sah, tidak ada nilai dari isian itu yang disimpan. |

**Alur utama**

| Langkah | Tindakan Dosen | Respons Sistem |
|---|---|---|
| 1 | Memilih fungsi Input Nilai Mata Kuliah. | Menampilkan daftar mata kuliah yang diampu dosen tersebut. |
| 2 | Memilih mata kuliah yang akan dinilai. | Memeriksa bahwa dosen adalah pengampu mata kuliah terpilih, lalu menampilkan daftar mahasiswa peserta beserta isian nilai. |
| 3 | Mengisi nilai setiap mahasiswa peserta. | Menampung isian nilai. |
| 4 | Memilih simpan. | Memeriksa bahwa setiap nilai berada dalam rentang yang sah. |
| 5 | Tidak ada tindakan. | Menyimpan nilai dengan status Belum dipublikasikan. |
| 6 | Melihat konfirmasi penyimpanan. | Menampilkan ringkasan nilai yang tersimpan. |

**Alur alternatif atau pengecualian**

- **A1: Dosen bukan pengampu mata kuliah (pada langkah 2):** sistem menolak, tidak menampilkan isian nilai, dan memberi tahu bahwa dosen bukan pengampu mata kuliah tersebut. Pascakondisi gagal berlaku; tidak ada nilai yang tersimpan.
- **A2: Nilai di luar rentang yang sah (pada langkah 4):** sistem menolak penyimpanan, menandai isian yang tidak sah, dan meminta dosen mengoreksinya. Nilai tidak disimpan sampai seluruh isian sah. Bila dosen keluar tanpa menyimpan, pascakondisi gagal berlaku.

## Use case description ringkas: SIA-UC09 Lihat KHS

| Elemen | Deskripsi |
|---|---|
| ID dan Nama | SIA-UC09: Lihat KHS |
| Sumber Kebutuhan | SIA-R09 |
| Tujuan | Mahasiswa melihat Kartu Hasil Studi untuk semester yang nilainya sudah dipublikasikan. |
| Aktor Utama | Mahasiswa |
| Pemicu | Mahasiswa memilih fungsi lihat KHS dan menentukan semester. |
| Prasyarat | Mahasiswa telah terautentikasi. |
| Alur Utama | (1) Mahasiswa memilih fungsi Lihat KHS dan semester. (2) Sistem mengambil nilai semester tersebut yang berstatus Dipublikasikan. (3) Sistem menampilkan KHS yang hanya memuat nilai yang sudah dipublikasikan. |
| Alur Alternatif | A1 (langkah 2): semester terpilih belum memiliki nilai yang dipublikasikan; sistem menyatakan KHS semester tersebut belum tersedia dan tidak menampilkan nilai apa pun. |
| Pascakondisi Berhasil | KHS semester terpilih ditampilkan dan hanya memuat nilai yang sudah dipublikasikan; tidak ada data berubah. |
| Pascakondisi Gagal | Tidak ada KHS yang ditampilkan; tidak ada data berubah. |
| Include / Extend / Generalization | Tidak ada |
| Collaboration | SIA-CO02: Lihat KHS |
| Aturan Bisnis / Asumsi | Nilai yang belum dipublikasikan tidak pernah ditampilkan pada KHS. |
