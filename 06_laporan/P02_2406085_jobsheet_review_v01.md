| No. | Temuan | Perbaikan yang Diperlukan | Alasan |
|---:|---|---|---|
| 1. | Aktor **Mahasiswa** berada di dalam batas sistem. | Aktor **Mahasiswa** harus berada di luar batas sistem. | Karena aktor merupakan pihak atau entitas yang berinteraksi dengan sistem, bukan bagian dari sistem itu sendiri. |
| 2. | Node **Lihat Jadwal Kuliah** menggunakan bentuk persegi. | Node **Lihat Jadwal Kuliah** seharusnya menggunakan bentuk lingkaran/elips sesuai dengan notasi yang digunakan pada diagram. | Karena pada notasi UML, **Entry Point** direpresentasikan menggunakan simbol lingkaran/elips, bukan persegi. |
| 3. | Aktor **Mahasiswa** dihubungkan dengan **Kelola Jadwal Kuliah**. | Aktor **Mahasiswa** dihubungkan dengan **Lihat Jadwal Kuliah**, sedangkan aktor **Admin Akademik** dihubungkan dengan **Kelola Jadwal Kuliah**. | Karena Mahasiswa memiliki hak untuk melihat jadwal kuliah, sedangkan pengelolaan jadwal kuliah merupakan tanggung jawab Admin Akademik. |
| 4. | Identitas diagram keliru. | Identitas diagram diganti menjadi **Sistem Informasi Akademik**. | Karena kasus yang diuji merupakan sistem informasi akademik, bukan sistem informasi laboratorium. |
//