| Elemen                 | SIA-UC01 — Lihat jadwal kuliah                         |
| :--------------------- | ------------------------------------------------------ |
| Tujuan                 | Melihat jadwal kuliah sebelum mengajukan KRS           |
| Aktor utama            | Mahasiswa                                              |
| Sumber kebutuhan       | SIA-R01                                                |
| Pemicu                 | Mahasiswa memilih fungsi lihat jadwal kuliah           |
| Prasyarat              | Mahasiswa telah terautentikasi; jadwal kuliah tersedia |
| Pascakondisi berhasil  | Jadwal kuliah diperlihatkan                            |
| keputusan Pascakondisi | gagal Tidak dapat menampilkan jadwal kuliah            |
| Include                | -                                                      |
| Extension point        | -                                                      |
| Extend                 | -                                                      |

| Elemen                 | SIA-UC02 — Kelola jadwal kuliah                           |
| :--------------------- | --------------------------------------------------------- |
| Tujuan                 | Mengelola jadwal kuliah sebelum mahasiswa mengajukan KRS  |
| Aktor utama            | Admin akademik                                            |
| Sumber kebutuhan       | SIA-R02                                                   |
| Pemicu                 | Admin akademik memilih fungsi kelola jadwal kuliah        |
| Prasyarat              | Admin telah terautentikasi; kelola jadwal kuliah tersedia |
| Pascakondisi berhasil  | Pengelolaan jadwal kuliah dapat dilakukan                 |
| keputusan Pascakondisi | gagal Tidak dapat mengelola jadwal kuliah                 |
| Include                | -                                                         |
| Extension point        | -                                                         |
| Extend                 | -                                                         |

| Elemen                 | SIA-UC03 — Ajukan KRS                                  |
| :--------------------- | ------------------------------------------------------ |
| Tujuan                 | Menghasilkan pengajuan KRS yang tersimpan              |
| Aktor utama            | Mahasiswa                                              |
| Sumber kebutuhan       | SIA-R03 dan SIA-R04                                    |
| Pemicu                 | Mahasiswa memilih fungsi pengajuan krs                 |
| Prasyarat              | Mahasiswa telah terautentikasi; jadwal kuliah tersedia |
| Pascakondisi berhasil  | Pengajuan tersimpan dengan status menunggu validasi    |
| keputusan Pascakondisi | Tidak ada pengajuan baru yang berhasil tersimpan       |
| Include                | SIA-UC04 - Validasi KRS                                |
| Extension point        | Bukti pengajuan tersedia                               |
| Extend                 | SIA-UC05 jika [mahasiswa memilih cetak]                |

| Elemen                 | SIA-UC04 — Validasi KRS                                           |
| :--------------------- | ------------------------------------------------------            |
| Tujuan                 | memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal |
| Aktor utama            | Mahasiswa                                                         |
| Sumber kebutuhan       | SIA-R04                                                           |
| Pemicu                 | Mahasiswa memilih fungsi pengajuan krs                            |
| Prasyarat              | Mahasiswa telah terautentikasi; jadwal kuliah tersedia            |
| Pascakondisi berhasil  | Validasi berhasil, jadwal lengkap dengan prasyarat mata kuliah, dan benturan jadwal mata kuliah terverifikasi                                                                    |
| keputusan Pascakondisi | gagal Tidak dapat memvalidasi KRS yang diajukan                   |    
| Include                | SIA-UC03 - Ajukan KRS                                             |
| Extension point        | -                                                                 |
| Extend                 | -                                                                 |

| Elemen                 | SIA-UC05 — Cetak bukti pengajuan                              |
| :--------------------- | ------------------------------------------------------------- |
| Tujuan                 | Menghasilkan cetakan bukti pengjuan krs                       |
| Aktor utama            | Mahasiswa                                                     |
| Sumber kebutuhan       | SIA-R05                                                       |
| Pemicu                 | Mahasiswa memilih fungsi cetak bukti pengajuan                |
| Prasyarat              | KRS telah berhasil diajukan dan tervalidasi; KRS bisa dicetak |
| Pascakondisi berhasil  | KRS dicetak                                                   |
| keputusan Pascakondisi | gagal Tidak dapat mencetak krs                                |
| Include                | -                                                             |
| Extension point        | Bukti pengajuan tersedia                                      |
| Extend                 | SIA-UC03 jika [mahasiswa memilih cetak]                       |

| Elemen                 | SIA-UC06 — Proses keputusan pnegajuan                                  |
| :--------------------- | ---------------------------------------------------------------------- |
| Tujuan                 | Memberikan keputusan pada pengajuan krs                                |
| Aktor utama            | Dosen wali                                                             |
| Sumber kebutuhan       | SIA-R06                                                                |
| Pemicu                 | Dosen wali memilih fungsi proses keputusan pengajuan                   |
| Prasyarat              | Dosen wali telah terautentikasi; daftar pengajuan tersedia             |
| Pascakondisi berhasil  | Dapat melaksanakan pengambilan keputusan untuk pengajuan yang tersedia |
| keputusan Pascakondisi | gagal Tidak dapat melaksanakan pengambilan keputusan                   |
| Include                | -                                                                      |
| Extension point        | -                                                                      |
| Extend                 | -                                                                      |