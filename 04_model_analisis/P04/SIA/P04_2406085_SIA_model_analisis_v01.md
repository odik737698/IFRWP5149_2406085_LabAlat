<!-- Spesifikasi hubungan diagram kumulatif SIA (18 hubungan). Sumber: P04_2406085_SIA_usecase_v01.drawio -->
| No. | Sumber | Hubungan | Tujuan | Status |
|---|---|---|---|---|
| 1 | Civitas Akademika | Association | SIA-UC07 Lihat Kalender Akademik | Baru (diwariskan ke Mahasiswa dan Dosen) |
| 2 | Mahasiswa | Association | SIA-UC01 Lihat Jadwal Kuliah | Tetap dari Pertemuan 3 |
| 3 | Mahasiswa | Association | SIA-UC03 Ajukan KRS | Tetap dari Pertemuan 3 |
| 4 | Mahasiswa | Association (khusus) | SIA-UC05 Unduh Bukti Pengajuan KRS | Tetap menurut model analisis P03; dilengkapi pada diagram |
| 5 | Mahasiswa | Association (khusus) | SIA-UC09 Lihat KHS | Baru |
| 6 | Dosen | Association (khusus) | SIA-UC08 Input Nilai Mata Kuliah | Baru |
| 7 | Admin Akademik | Association | SIA-UC02 Kelola Jadwal Kuliah | Tetap dari Pertemuan 3 |
| 8 | Admin Akademik | Association | SIA-UC10 Kelola Data Mahasiswa | Baru |
| 9 | Dosen Wali | Association | SIA-UC06 Proses Keputusan KRS | Tetap dari Pertemuan 3 |
| 10 | Mahasiswa | Generalization → | Civitas Akademika | Baru |
| 11 | Dosen | Generalization → | Civitas Akademika | Baru |
| 12 | SIA-UC03 Ajukan KRS | «include» | SIA-UC04 Validasi KRS | Tetap dari Pertemuan 3 |
| 13 | SIA-UC05 Unduh Bukti Pengajuan KRS | «extend» | SIA-UC03 Ajukan KRS | Tetap dari Pertemuan 3; condition [mahasiswa memilih unduh]; extension point Bukti pengajuan tersedia |
| 14 | SIA-UC11 Tambah Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa | Baru |
| 15 | SIA-UC12 Ubah Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa | Baru |
| 16 | SIA-UC13 Hapus Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa | Baru |
| 17 | SIA-CO01 (collaboration) Input Nilai Mata Kuliah | Realization → | SIA-UC08 Input Nilai Mata Kuliah | Baru |
| 18 | SIA-CO02 (collaboration) Lihat KHS | Realization → | SIA-UC09 Lihat KHS | Baru |

