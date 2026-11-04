# Lembar Skenario Pertemuan 6: Tugas SIA (Input Nilai sampai Lihat KHS)

Tanggal: 04-11-2026 | NIM: 2406085 | Versi: v01
Kasus: Sistem Informasi Akademik, melanjutkan kasus SIA Pertemuan 5
Diagram: `04_model_analisis/P06/SIA/P06_2406085_SIA_activity_v02.drawio` (dasar: `P06_2406085_SIA_activity_v01.drawio`)

## 1. Acuan

- Sumber langkah: tabel skenario SIA Pertemuan 5, yaitu Tabel 5.16 SIA-UC08 Input Nilai Mata Kuliah dan Tabel 5.17 SIA-UC09 Lihat KHS (`P05_2406085_SIA_skenario_v01.md`). Diagram SIA Pertemuan 4 hanya menjadi acuan nama aktor dan tidak diubah.
- Ketentuan tugas (jobsheet Pertemuan 6, Bagian C.3): empat swimlane (Dosen, Sistem, Admin Akademik, Mahasiswa); satu decision kelengkapan nilai dengan guard [lengkap] dan [belum lengkap]; satu pasang fork dan join setelah nilai disahkan; satu initial node dan satu activity final node.
- Beberapa unsur pada tugas ini ditetapkan oleh jobsheet dan tidak ada pada tabel P05. Unsur tersebut ditandai **Baru** pada skenario dan diberi bingkai putus-putus oranye pada diagram v02. Unsur ini tidak diklaim berasal dari Pertemuan 5.

## 2. Skenario proses Input Nilai sampai Lihat KHS

| Nama proses | Input Nilai Mata Kuliah sampai Lihat KHS |
|---|---|
| Aktor | Dosen, Admin Akademik, Mahasiswa (Sistem sebagai swimlane respon) |
| Tujuan | Nilai yang dimasukkan dosen disahkan, diterbitkan sebagai KHS, dan dapat dilihat mahasiswa |
| Deskripsi | Dosen memasukkan nilai mata kuliah, Sistem menyimpannya dan memeriksa kelengkapan, Admin Akademik mengesahkan, Sistem menerbitkan KHS dan mengirim pemberitahuan secara paralel, lalu Mahasiswa melihat KHS |

| **Kegiatan** | **Respon sistem** |
|---|---|
| **Skenario Normal** | |
| 1. Dosen memasukkan nilai mata kuliah |  |
|  | 2. Sistem menyimpan nilai |
|  | 3. Sistem memeriksa kelengkapan nilai |
| 4. Admin Akademik memeriksa dan mengesahkan nilai |  |
|  | 5. Sistem menyiapkan publikasi hasil studi |
|  | 6. Sistem menerbitkan KHS pada portal akademik (paralel dengan langkah 7) |
|  | 7. Sistem mengirim pemberitahuan hasil studi kepada mahasiswa (paralel dengan langkah 6) |
| 8. Mahasiswa melihat KHS |  |
| **Skenario Alternative** | |
| 9. Nilai belum lengkap (cabang dari langkah 3; guard [belum lengkap]) |  |
| 10. Dosen melengkapi nilai mata kuliah yang belum lengkap, lalu alur kembali ke langkah 4 |  |
| Skenario Akhir | Proses selesai jika Mahasiswa melihat KHS setelah langkah 6 dan 7 sama-sama selesai (join). Nilai yang belum lengkap tidak diteruskan ke pengesahan sampai dilengkapi. |

Keterangan: langkah 6 dan 7 adalah dua proses paralel yang disatukan oleh join sebelum langkah 8; merge tidak dipakai untuk menyatukannya.

## 3. Keterlacakan action ke sumber

| Action / unsur pada diagram | Swimlane | Langkah sumber | Status |
|---|---|---|---|
| Memasukkan nilai mata kuliah | Dosen | SIA-UC08 langkah 6 dan 7 (mengisi nilai, memilih simpan) | Sama |
| Menyimpan nilai | Sistem | SIA-UC08 langkah 9 (status Belum dipublikasikan) | Sama |
| Decision Nilai sudah lengkap? [lengkap] / [belum lengkap] | Sistem | Tidak ada. Terkait sebagian dengan SIA-UC08 langkah 15 sampai 18 (nilai di luar rentang yang sah), tetapi yang diperiksa di sini kelengkapan, bukan keabsahan | Baru; menyangkut pertanyaan terbuka no. 5 |
| Melengkapi nilai mata kuliah yang belum lengkap | Dosen | Tidak ada. Serupa dengan SIA-UC08 langkah 18 (meminta dosen mengoreksi isian) | Baru |
| Merge setelah cabang kelengkapan | Sistem | Tidak berlaku (unsur notasi) | Sama dengan aturan jobsheet |
| Memeriksa dan mengesahkan nilai | Admin Akademik | Tidak ada. SIA-UC08 berakhir pada status Belum dipublikasikan | Baru; menyangkut pertanyaan terbuka no. 1 |
| Menyiapkan publikasi hasil studi | Sistem | Tidak ada | Baru |
| Fork dan join | Sistem | Tidak ada | Baru (ditetapkan jobsheet) |
| Menerbitkan KHS pada portal akademik | Sistem | Tidak ada. Terkait dengan status Dipublikasikan yang diandaikan oleh SIA-UC09 langkah 4 | Baru |
| Mengirim pemberitahuan hasil studi kepada mahasiswa | Sistem | Tidak ada | Baru |
| Melihat KHS | Mahasiswa | SIA-UC09 langkah 1 sampai 5 (digabung menjadi satu action) | Sebagian: langkah pilih semester dan guard KHS belum tersedia tidak digambar |

Hasil: dari 11 baris, 2 berstatus Sama, 1 Sebagian, dan 7 Baru (satu baris notasi merge tidak dihitung). Karena sebagian besar unsur sesudah penyimpanan nilai ditetapkan jobsheet, diagram ini tidak seluruhnya tertelusur ke P05, dan hal itu dicatat secara terbuka.

## 4. Hal yang sengaja tidak digambar

Perilaku berikut ada pada tabel P05 tetapi di luar cakupan ketentuan tugas P06:

- SIA-UC08 langkah 4 sampai 5 dan cabang langkah 12 sampai 14: pemeriksaan dosen pengampu dan penolakan akses bagi dosen non-pengampu.
- SIA-UC08 cabang langkah 15 sampai 18: nilai di luar rentang yang sah.
- SIA-UC09 langkah 2 sampai 3 (memilih semester) dan cabang langkah 6 sampai 8 (KHS semester belum tersedia).

## 5. Asumsi dan pertanyaan terbuka

| No. | Hal | Dampak pada diagram |
|---|---|---|
| 1 | Pertanyaan terbuka no. 1 (siapa dan kapan nilai dipublikasikan) dijawab oleh jobsheet P06 hanya untuk latihan: Admin Akademik mengesahkan, lalu Sistem menerbitkan KHS | Action Memeriksa dan mengesahkan nilai serta Menerbitkan KHS pada portal akademik. Perlu dikonfirmasi bila aturan ini akan dipakai di luar latihan |
| 2 | Pertanyaan terbuka no. 5 (draf atau penyimpanan harus lengkap) | Decision Nilai sudah lengkap? mengasumsikan nilai tersimpan lebih dulu lalu diperiksa kelengkapannya |
| 3 | Pertanyaan terbuka no. 2 (publikasi per semester atau per nilai) | Tidak dijawab; diagram tidak menyebut satuan publikasi |
| 4 | Setelah Melengkapi nilai, alur langsung kembali ke pengesahan (sesuai Langkah 3 jobsheet) tanpa penyimpanan ulang oleh Sistem | Dapat ditinjau bila penyimpanan ulang dianggap perlu |
| 5 | Pemberitahuan hasil studi tidak dijelaskan medianya (surel, notifikasi portal) | Action ditulis sama dengan jobsheet tanpa menambah aturan |

## 6. Checklist hasil pemeriksaan

- ✔️ Satu initial node (swimlane Dosen) dan satu activity final node (swimlane Mahasiswa); tidak ada action yang terputus.
- ✔️ Empat swimlane sesuai ketentuan: Dosen, Sistem, Admin Akademik, Mahasiswa.
- ✔️ Decision Nilai sudah lengkap? memiliki guard [lengkap] dan [belum lengkap]; cabang [belum lengkap] kembali ke Dosen lalu bergabung melalui merge sebelum pengesahan.
- ✔️ Satu pasang fork dan join setelah nilai disahkan; keduanya digambar paralel dan disatukan oleh join sebelum Mahasiswa melihat KHS.
- ✔️ Setiap action berada pada swimlane aktor yang melakukannya; respon sistem berada pada swimlane Sistem.
- ⚠️ Keterlacakan ke tabel P05: hanya sebagian (Bagian 3); unsur Baru ditandai pada diagram v02.
- ✔️ Collaboration tidak digambar; berkas P04 dan dokumen P05 tidak diubah.
- ✔️ Berkas sumber dan ekspor v02 memiliki nomor versi yang sama; v01 dipertahankan sebagai dasar.

## 7. Riwayat revisi

| Versi | Perubahan |
|---|---|
| v01 | Diagram dan PNG awal. Seluruh unsur sesuai ketentuan tugas, tetapi unsur yang tidak berasal dari P05 belum ditandai |
| v02 | Menambahkan bingkai putus-putus oranye pada enam unsur Baru (decision kelengkapan, Melengkapi nilai, Memeriksa dan mengesahkan nilai, Menyiapkan publikasi, Menerbitkan KHS, Mengirim pemberitahuan) dan kotak keterangan. Alur, guard, dan nama action tidak berubah |
