COGNIS ACADEMY

Learning Schedule and Academic Operations

Document ID: CA-ACA-004
Version: 1.0.0
Status: Initial Specification
Project: Cognis AI
Subsystem: Cognis Academy
Timezone: Asia/Jakarta (WIB)
Language: Bahasa Indonesia

---

1. Purpose

Dokumen ini mengatur jadwal dan aktivitas pembelajaran otomatis Cognis AI selama menjalani pendidikan di Cognis Academy.

Cognis harus dapat memulai aktivitas pembelajaran berdasarkan kurikulum dan jadwal yang telah ditentukan tanpa harus menunggu Founder memberikan materi atau instruksi setiap pagi.

Sistem harus mampu:

- Menentukan materi yang perlu dipelajari.
- Menyusun prioritas pembelajaran.
- Melakukan penelitian dan pengumpulan sumber.
- Mempelajari materi.
- Mengerjakan latihan.
- Melakukan evaluasi.
- Mengulang kompetensi yang masih lemah.
- Menyusun laporan perkembangan.
- Mengirim laporan kepada Founder.
- Mengelola pekerjaan yang belum selesai melalui antrean dan checkpoint.

Founder bertindak sebagai validator perkembangan akademik dan pengambil keputusan kelulusan fakultas.

Prinsip utama: Cognis menjalankan pembelajaran secara mandiri, sedangkan Founder mengawasi dan memvalidasi hasilnya.

2. Scheduling Principles

2.1 Autonomous Daily Learning

Cognis harus memulai aktivitas belajar secara otomatis berdasarkan jadwal.

Sistem tidak boleh bergantung pada pesan harian Founder agar dapat memulai pembelajaran.

Founder dapat memberikan instruksi tambahan, tetapi instruksi tersebut bukan prasyarat untuk aktivitas belajar rutin.

2.2 Active Faculty Restriction

Pembelajaran resmi harus mengikuti fakultas yang sedang aktif.

Cognis tidak boleh memulai kurikulum resmi fakultas berikutnya sebelum memperoleh persetujuan Founder.

Sistem masih diperbolehkan menggunakan pengetahuan dari fakultas terdahulu untuk memperkuat pembelajaran saat ini.

2.3 Competency-Driven Scheduling

Jadwal harus ditentukan berdasarkan kebutuhan kompetensi, bukan hanya urutan materi.

Academic Planner harus mempertimbangkan:

- Kompetensi yang belum dipelajari.
- Kompetensi yang sedang dipelajari.
- Kompetensi yang belum mencapai standar.
- Hasil evaluasi terbaru.
- Prasyarat kompetensi.
- Prioritas kurikulum.
- Ketersediaan sumber belajar.

2.4 Adaptive Scheduling

Jadwal harus dapat berubah berdasarkan hasil evaluasi.

Jika Cognis mengalami kelemahan pada kompetensi tertentu, sistem harus meningkatkan prioritas latihan atau remedial pada kompetensi tersebut.

Jika suatu kompetensi telah dikuasai dengan bukti memadai, sistem dapat mengurangi frekuensi latihan dasar dan memprioritaskan kompetensi lain.

2.5 Resource-Aware Scheduling

Sistem harus mempertimbangkan biaya dan kapasitas komputasi.

Aktivitas pembelajaran tidak harus berjalan terus-menerus selama 12 jam.

Scheduler harus membagi pekerjaan menjadi tugas yang dapat dijalankan, dihentikan sementara, dilanjutkan, atau dijadwalkan ulang.

2.6 Human-Validated Progression

Jadwal tidak memiliki kewenangan untuk menyetujui kelulusan.

Penyelesaian semua aktivitas harian, mingguan, atau bulanan tidak dapat membuka fakultas berikutnya secara otomatis.

3. Daily Operating Schedule

Jadwal berikut merupakan konfigurasi awal Cognis Academy.

Seluruh waktu menggunakan WIB dan dapat disesuaikan melalui konfigurasi sistem tanpa mengubah kebijakan akademik.

Waktu| Aktivitas| Tujuan
06.00–06.15| Daily Planning| Menentukan target dan prioritas harian.
06.15–07.15| Core Learning Session| Mempelajari materi utama.
07.15–08.00| Knowledge Consolidation| Membuat catatan dan menghubungkan konsep.
08.00–09.00| Practical Exercises| Mengerjakan latihan penerapan.
09.00–10.30| Research Session| Meneliti sumber dan memperdalam materi.
10.30–11.00| Evidence Review| Memeriksa sumber dan kualitas bukti.
11.00–12.00| Applied Learning| Menerapkan materi dalam studi kasus.
12.00–13.00| Review and Recall| Menguji kembali materi sebelumnya.
13.00–14.00| Cross-Subject Integration| Menghubungkan materi dalam fakultas aktif.
14.00–15.00| Weakness Remediation| Memperbaiki kompetensi yang belum memadai.
15.00–16.00| Assessment Session| Menjalankan evaluasi pembelajaran harian.
16.00–17.00| Performance Analysis| Menganalisis hasil dan menyusun tindak lanjut.
17.00–18.00| Report Preparation| Menyusun laporan akademik harian.
18.00| Founder Daily Report| Mengirim laporan kepada Founder melalui Telegram.

Jadwal di atas adalah jendela operasional, bukan kewajiban memanggil model AI setiap menit.

Scheduler dapat menggabungkan, membagi, atau melewatkan sesi tertentu berdasarkan prioritas, ketersediaan sumber, dan anggaran komputasi.

Jika satu pekerjaan memerlukan waktu lebih lama, sistem dapat melanjutkannya melalui antrean tanpa harus mengganggu seluruh jadwal.

4. Daily Learning Workflow

4.1 Daily Planning

Pada awal hari, Academic Planner melakukan pemeriksaan terhadap:

- Fakultas aktif.
- Status mata pelajaran.
- Target kompetensi.
- Hasil evaluasi sebelumnya.
- Remedial yang belum selesai.
- Pekerjaan tertunda.
- Ketersediaan model dan sumber.
- Batas biaya dan token.

Academic Planner kemudian membuat Daily Learning Plan.

Rencana tersebut minimal memuat:

1. Kompetensi utama hari ini.
2. Materi yang akan dipelajari.
3. Sumber yang diperlukan.
4. Latihan yang harus dikerjakan.
5. Target evaluasi.
6. Estimasi penggunaan sumber daya.
7. Target laporan harian.

Daily Learning Plan harus disimpan sebelum pekerjaan utama dimulai.

4.2 Core Learning Session

Cognis mempelajari materi yang telah dipilih.

Aktivitas meliputi:

- Membaca sumber.
- Memahami konsep.
- Membandingkan penjelasan.
- Mengidentifikasi asumsi.
- Menyusun pertanyaan.
- Mencatat informasi penting.

Hasil sesi harus berupa catatan belajar yang dapat ditelusuri ke sumbernya.

4.3 Knowledge Consolidation

Setelah pembelajaran inti, Cognis harus mengonsolidasikan pengetahuan.

Aktivitas:

- Membuat ringkasan.
- Menjelaskan konsep menggunakan bahasanya sendiri.
- Mengidentifikasi hubungan antaride.
- Mencatat keterbatasan pemahaman.
- Menghubungkan konsep baru dengan pengetahuan sebelumnya.

Ringkasan tidak otomatis dianggap sebagai pengetahuan terverifikasi.

4.4 Practical Exercises

Cognis mengerjakan latihan yang berkaitan dengan materi.

Latihan harus menguji pemahaman dan penerapan.

Sistem harus menghindari penggunaan soal yang sama secara terus-menerus karena dapat menghasilkan hafalan tanpa penguasaan konsep.

4.5 Research Session

Cognis melakukan penelitian untuk memperdalam materi.

Aktivitas penelitian meliputi:

- Mencari sumber yang relevan.
- Membandingkan sumber.
- Memeriksa kredibilitas.
- Mengidentifikasi perbedaan pendapat.
- Mencatat bukti pendukung.
- Menyatakan ketidakpastian.

Sumber baru harus dicatat beserta tanggal akses apabila informasi berpotensi berubah.

4.6 Evidence Review

Sistem memeriksa kualitas sumber dan bukti.

Pemeriksaan mencakup:

- Identitas sumber.
- Relevansi.
- Kredibilitas.
- Kebaruan informasi.
- Konsistensi antar-sumber.
- Kemungkinan bias.
- Keterbatasan data.

Cognis tidak boleh menganggap suatu klaim benar hanya karena ditemukan pada banyak situs yang mengutip sumber asli yang sama.

4.7 Applied Learning

Cognis menerapkan materi melalui studi kasus.

Kasus dapat berupa:

- Persoalan teoretis.
- Contoh praktis.
- Data historis.
- Simulasi.
- Permasalahan nyata yang dapat didukung sumber.

Untuk informasi yang berubah cepat, sistem harus menggunakan sumber terkini ketika melakukan analisis.

4.8 Review and Recall

Cognis mengulang materi yang telah dipelajari sebelumnya.

Metode yang dapat digunakan:

- Active Recall.
- Spaced Repetition.
- Concept Mapping.
- Practice Retrieval.
- Interleaved Practice.

Tujuannya mempertahankan pengetahuan agar tidak hanya dipahami sesaat.

4.9 Cross-Subject Integration

Cognis menghubungkan kompetensi dari beberapa mata pelajaran dalam fakultas yang sedang aktif.

Contoh di Fakultas 1:

- Logika digunakan dalam evaluasi argumen.
- Probabilitas digunakan dalam analisis ketidakpastian.
- Kausalitas digunakan dalam penelitian.
- Systems Thinking digunakan dalam pemahaman hubungan antarvariabel.

Integrasi dengan pengetahuan fakultas terdahulu diperbolehkan.

Namun, materi resmi fakultas yang masih terkunci tidak boleh dijadikan kurikulum utama.

4.10 Weakness Remediation

Sistem mengidentifikasi kelemahan berdasarkan hasil latihan dan evaluasi.

Prioritas remedial harus diberikan pada:

- Kompetensi prasyarat.
- Kesalahan fundamental.
- Kegagalan berulang.
- Kompetensi yang dibutuhkan untuk materi berikutnya.
- Kelemahan yang berpotensi memengaruhi banyak mata pelajaran.

4.11 Assessment Session

Cognis mengikuti evaluasi harian.

Evaluasi dapat berbentuk:

- Pertanyaan pemahaman.
- Pengujian logika.
- Pemecahan masalah.
- Penerapan konsep.
- Verifikasi klaim.
- Studi kasus singkat.

Evaluasi harian bersifat formatif dan tidak menggantikan ujian fakultas.

4.12 Performance Analysis

Cognis menganalisis hasil pembelajaran hari itu.

Sistem harus menjawab:

- Apa yang berhasil dipelajari?
- Kompetensi apa yang berkembang?
- Apa yang masih lemah?
- Apakah sumber yang digunakan memadai?
- Apakah metode pembelajaran efektif?
- Apa prioritas untuk hari berikutnya?

Hasil analisis digunakan oleh Academic Planner untuk memperbarui rencana berikutnya.

4.13 Report Preparation

Sistem menyusun laporan harian sebelum dikirim kepada Founder.

Laporan harus mencerminkan pekerjaan yang benar-benar dilakukan.

Pekerjaan yang gagal, tertunda, atau belum terverifikasi harus disebutkan secara transparan.

5. Daily Telegram Reporting

Telegram menjadi antarmuka utama untuk menyampaikan perkembangan Cognis kepada Founder.

Laporan harian dijadwalkan pada pukul 18.00 WIB.

5.1 Daily Report Contents

Laporan minimal memuat:

A. Academic Status

- Fakultas aktif.
- Mata pelajaran aktif.
- Status pembelajaran.
- Hari atau sesi pembelajaran.

B. Daily Learning Summary

- Materi yang dipelajari.
- Sumber yang digunakan.
- Konsep utama yang dipahami.
- Aktivitas penelitian.

C. Competency Development

- Kompetensi yang dilatih.
- Perkembangan yang terukur.
- Kompetensi yang masih lemah.

D. Assessment Results

- Latihan yang diselesaikan.
- Hasil evaluasi.
- Kesalahan yang ditemukan.
- Perbandingan dengan evaluasi sebelumnya jika dapat dilakukan secara valid.

E. Research Findings

- Temuan utama.
- Bukti pendukung.
- Perbedaan pendapat.
- Keterbatasan informasi.

F. Problems and Limitations

- Sumber gagal diakses.
- Evaluasi gagal.
- Model tidak tersedia.
- Batas biaya tercapai.
- Pekerjaan tertunda.

G. Next Learning Plan

- Prioritas berikutnya.
- Materi yang akan dipelajari.
- Target remedial.
- Jadwal evaluasi.

H. Academic Progress

- Status fakultas.
- Apakah persyaratan internal sudah terpenuhi.
- Apakah Cognis sedang menunggu validasi Founder.

5.2 Honest Reporting

Laporan tidak boleh:

- Mengarang aktivitas yang tidak dilakukan.
- Mengklaim telah membaca sumber yang tidak diakses.
- Menyatakan kompetensi dikuasai tanpa bukti.
- Menyembunyikan kegagalan.
- Mengubah hasil evaluasi.
- Menampilkan estimasi sebagai fakta.

5.3 No Automatic Approval

Pengiriman laporan tidak berarti Founder menyetujui kelulusan.

Persetujuan fakultas tetap mengikuti "FACULTY_PROGRESSION_POLICY.md".

Founder boleh memberikan tanggapan pada laporan tanpa harus menyetujui kenaikan fakultas.

6. Weekly Academic Cycle

Selain aktivitas harian, Cognis harus menjalani siklus evaluasi mingguan.

Siklus mingguan merupakan pemeriksaan terhadap pembelajaran selama satu minggu, bukan kewajiban menyelesaikan satu mata pelajaran dalam tujuh hari.

6.1 Weekly Planning Review

Academic Planner mengevaluasi:

- Pencapaian target mingguan.
- Materi yang sudah diselesaikan.
- Materi yang tertunda.
- Perkembangan kompetensi.
- Pekerjaan remedial.
- Kebutuhan sumber baru.
- Efisiensi biaya.

6.2 Weekly Assessment

Cognis menjalani evaluasi gabungan terhadap materi minggu tersebut.

Pengujian mencakup:

- Pemahaman konsep.
- Penalaran.
- Penerapan.
- Evaluasi bukti.
- Retensi materi.

Sebagian soal harus berbeda dari latihan harian.

6.3 Weekly Knowledge Review

Cognis memeriksa kembali catatan pembelajaran.

Aktivitas:

- Mengidentifikasi kontradiksi.
- Memperbaiki catatan yang salah.
- Menandai informasi yang kedaluwarsa.
- Menggabungkan pengetahuan terkait.
- Mengidentifikasi pertanyaan yang belum terjawab.

6.4 Weekly Performance Report

Sistem menyusun laporan mingguan yang mencakup:

- Total sesi pembelajaran.
- Materi yang diselesaikan.
- Hasil evaluasi.
- Perkembangan kompetensi.
- Kesalahan berulang.
- Remedial.
- Penggunaan sumber daya.
- Prioritas minggu berikutnya.

7. Monthly Academic Review

Pada akhir setiap bulan, Cognis harus menjalani evaluasi perkembangan yang lebih luas.

Tujuannya bukan mempercepat kenaikan fakultas, melainkan mengetahui apakah kemampuan Cognis berkembang secara konsisten.

Review meliputi:

1. Perbandingan hasil evaluasi antarperiode.
2. Retensi kompetensi.
3. Perkembangan kemampuan penerapan.
4. Kualitas penelitian.
5. Konsistensi penalaran.
6. Kualitas sumber.
7. Frekuensi kesalahan.
8. Efektivitas metode pembelajaran.
9. Efisiensi penggunaan model.
10. Kebutuhan perubahan kurikulum.

Sistem menyusun Monthly Academic Report.

Perubahan kurikulum atau konfigurasi permanen harus mengikuti tata kelola ALS.

8. Adaptive Learning Prioritization

Academic Planner harus memilih materi berdasarkan kebutuhan akademik.

Prioritas awal:

Priority 1: Critical Weakness

Kompetensi fundamental yang masih lemah harus menjadi prioritas tertinggi.

Priority 2: Prerequisite Competency

Kompetensi yang menjadi dasar materi selanjutnya harus diselesaikan sebelum materi turunannya diprioritaskan.

Priority 3: Current Learning Objective

Materi inti sesuai target fakultas aktif.

Priority 4: Retention

Kompetensi yang sudah dipelajari perlu diuji kembali agar tetap dikuasai.

Priority 5: Enrichment

Materi pengayaan yang dapat memperluas pemahaman.

Academic Planner harus menghindari mempelajari banyak materi secara dangkal hanya demi mengejar jumlah sesi.

Kedalaman penguasaan lebih penting daripada volume materi yang dibaca.

9. Workload and Resource Management

Scheduler harus mempertimbangkan anggaran komputasi dan penggunaan API.

9.1 Daily Resource Budget

Setiap hari sistem harus menetapkan:

- Batas biaya.
- Batas penggunaan token.
- Batas jumlah pemanggilan model.
- Batas waktu pekerjaan.
- Batas retry.
- Prioritas pekerjaan.

Nilai anggaran harus berada pada konfigurasi yang dapat diubah oleh Founder.

9.2 Model Allocation

Tidak semua pekerjaan membutuhkan model dengan kemampuan tertinggi.

Contoh alokasi:

Aktivitas| Model yang disarankan
Pengelompokan materi| Model kecil atau deterministik.
Ringkasan sumber| Model kecil atau menengah.
Penjelasan materi kompleks| Model yang lebih kuat.
Analisis kasus kompleks| Model yang lebih kuat.
Evaluasi jawaban| Evaluator terpisah.
Perhitungan statistik| Tool komputasi deterministik jika tersedia.
Validasi format dan status| Aturan program deterministik.

Model Gateway bertanggung jawab memilih model berdasarkan kebutuhan, kualitas, ketersediaan, dan biaya.

9.3 Task Queue

Pekerjaan harus dikelola melalui antrean.

Setiap pekerjaan minimal memiliki:

- Job ID.
- Task Type.
- Faculty ID.
- Subject ID.
- Priority.
- Status.
- Created At.
- Started At.
- Completed At.
- Retry Count.
- Resource Budget.
- Checkpoint Reference.
- Error Record.

9.4 Checkpointing

Pekerjaan yang berlangsung lama harus memiliki checkpoint.

Checkpoint digunakan untuk:

- Menyimpan progres.
- Melanjutkan pekerjaan.
- Menghindari pengulangan aktivitas.
- Mengurangi kehilangan hasil akibat timeout.
- Mengontrol biaya.

Sistem tidak boleh memulai ulang seluruh pekerjaan hanya karena satu tahap mengalami kegagalan.

9.5 Retry and Backoff

Jika suatu pekerjaan gagal:

1. Sistem mencatat kegagalan.
2. Sistem memeriksa kemungkinan penyebab.
3. Sistem mencoba kembali sesuai kebijakan retry.
4. Sistem menggunakan jeda bertahap jika diperlukan.
5. Jika batas retry tercapai, pekerjaan ditandai FAILED atau ON_HOLD.

Retry tidak boleh berjalan tanpa batas.

9.6 Resource Exhaustion

Jika anggaran harian habis:

- Pekerjaan prioritas rendah ditunda.
- Checkpoint pekerjaan disimpan.
- Pekerjaan kritis diproses sesuai kebijakan anggaran.
- Founder menerima informasi apabila keterbatasan mengganggu target pembelajaran.

Sistem tidak boleh diam-diam meningkatkan batas biaya atau menggunakan layanan berbayar di luar anggaran yang diizinkan.

10. Schedule Exception Handling

Jadwal harian dapat terganggu oleh beberapa kondisi.

10.1 Model Unavailable

Jika model AI tidak tersedia:

- Sistem mencatat gangguan.
- Pekerjaan yang dapat dialihkan menggunakan model alternatif sesuai kebijakan Model Gateway.
- Jika tidak ada alternatif yang sesuai, pekerjaan ditunda.
- Laporan mencantumkan keterbatasan.

10.2 Research Source Unavailable

Jika sumber tidak dapat diakses:

- Sistem mencoba sumber alternatif yang kredibel.
- Sistem mencatat kegagalan akses.
- Sistem tidak boleh mengarang isi sumber.
- Kesimpulan yang bergantung pada sumber tersebut harus diberi batasan.

10.3 Evaluation Failure

Jika proses evaluasi gagal:

- Hasil ditandai tidak valid atau belum lengkap.
- Sistem tidak boleh memberikan status kompeten berdasarkan hasil yang gagal.
- Pengujian dapat dijadwalkan ulang.

10.4 Interrupted Jobs

Jika proses berhenti akibat server restart, jaringan, atau gangguan lainnya:

- Sistem memulihkan pekerjaan dari checkpoint terakhir.
- Sistem memverifikasi konsistensi data.
- Sistem menghindari duplikasi hasil.
- Sistem melanjutkan pekerjaan sesuai prioritas.

10.5 Missed Schedule

Jika sesi terlewat:

- Sistem memeriksa apakah pekerjaan masih relevan.
- Sistem memprioritaskan ulang pekerjaan.
- Sistem menghindari menumpuk semua pekerjaan ke hari berikutnya.
- Sistem boleh mengurangi pekerjaan pengayaan untuk mempertahankan materi utama.

10.6 Founder Instruction

Founder dapat memberikan instruksi tambahan melalui Telegram.

Instruksi harus diklasifikasikan menjadi:

- Pertanyaan atau diskusi.
- Perintah belajar tambahan.
- Permintaan penelitian.
- Perubahan prioritas.
- Permintaan evaluasi.
- Keputusan akademik.
- Persetujuan perubahan sistem.

Sistem harus membedakan instruksi belajar biasa dengan keputusan yang memiliki konsekuensi terhadap status akademik atau sistem.

11. Faculty Transition Scheduling

Setelah Founder menyetujui kelulusan fakultas:

1. Sistem memvalidasi keputusan.
2. Status akademik diperbarui.
3. Fakultas berikutnya dibuka.
4. Academic Planner memeriksa prasyarat.
5. Kurikulum fakultas berikutnya dimuat.
6. Daily Learning Plan baru disusun.
7. Pembelajaran resmi fakultas berikutnya dimulai sesuai jadwal.

Materi fakultas sebelumnya tetap tersedia untuk:

- Review.
- Retention Assessment.
- Cross-Faculty Integration.
- Penelitian lintas disiplin.

Jika Founder belum menyetujui kenaikan fakultas, Cognis tetap melanjutkan aktivitas yang relevan di fakultas aktif.

Tidak ada jadwal yang dapat melewati proses persetujuan tersebut.

12. Schedule Configuration

Seluruh jadwal harus dapat diubah melalui konfigurasi.

Konfigurasi minimum:

Parameter| Deskripsi
TIMEZONE| Zona waktu operasional.
DAILY_START_TIME| Waktu memulai pembelajaran.
DAILY_REPORT_TIME| Waktu pengiriman laporan.
WEEKLY_REVIEW_DAY| Hari evaluasi mingguan.
MONTHLY_REVIEW_DAY| Jadwal evaluasi bulanan.
RESOURCE_BUDGET| Batas biaya operasional.
TOKEN_BUDGET| Batas penggunaan token.
MAX_CONCURRENT_JOBS| Batas pekerjaan paralel.
MAX_RETRIES| Batas percobaan ulang.
CHECKPOINT_INTERVAL| Frekuensi penyimpanan checkpoint.
ACTIVE_FACULTY_ID| Fakultas yang sedang aktif.

Perubahan konfigurasi tidak boleh mengubah status kelulusan atau hak akses Founder.

Semua perubahan penting harus dicatat dalam audit log.

13. Scheduler Architecture Responsibilities

Implementasi teknis harus memisahkan tanggung jawab berikut.

13.1 Academic Planner

Menentukan apa yang harus dipelajari.

13.2 Scheduler

Menentukan kapan pekerjaan dijalankan.

13.3 Task Queue

Mengelola antrean dan prioritas pekerjaan.

13.4 Learning Worker

Menjalankan pekerjaan pembelajaran.

13.5 Assessment Worker

Menjalankan evaluasi.

13.6 Report Worker

Menyusun dan mengirim laporan.

13.7 Progression Manager

Mengelola status fakultas dan memastikan perpindahan tingkat mengikuti persetujuan Founder.

Scheduler tidak boleh memiliki kewenangan untuk menetapkan kelulusan.

14. Daily Report Delivery Failure

Jika Telegram tidak dapat menerima laporan pada pukul 18.00 WIB:

1. Sistem menyimpan laporan yang telah dibuat.
2. Sistem mencatat status pengiriman.
3. Sistem mencoba mengirim ulang sesuai batas retry.
4. Jika pengiriman gagal, laporan tetap tersedia dalam penyimpanan.
5. Founder dapat menerima pemberitahuan setelah koneksi pulih.
6. Laporan tidak boleh dibuat ulang dengan isi berbeda tanpa alasan yang tercatat.

Status laporan harus dibedakan menjadi:

- GENERATED.
- QUEUED.
- SENT.
- DELIVERY_FAILED.
- RETRY_PENDING.

Sistem tidak boleh mengklaim laporan sudah diterima jika pengiriman belum berhasil dikonfirmasi.

15. Monitoring and Performance Metrics

Scheduler dan sistem akademik harus memantau:

Academic Metrics

- Learning Sessions Completed.
- Competencies Assessed.
- Competencies Mastered.
- Remedial Completion Rate.
- Assessment Score Trend.
- Knowledge Retention.
- Research Completion Rate.

Operational Metrics

- Job Success Rate.
- Job Failure Rate.
- Average Job Duration.
- Queue Length.
- Retry Count.
- Checkpoint Recovery Rate.
- Model Availability.

Cost Metrics

- Daily API Cost.
- Weekly API Cost.
- Token Usage.
- Cost per Learning Session.
- Cost per Assessment.
- Cost per Competency Improvement.

Metrik tersebut digunakan untuk mengevaluasi efektivitas pembelajaran sekaligus menjaga keberlanjutan operasional.

Jumlah materi yang selesai tidak boleh dijadikan satu-satunya indikator keberhasilan.

16. Acceptance Criteria

Implementasi Learning Schedule dianggap berhasil apabila:

1. Cognis dapat memulai pembelajaran secara otomatis.
2. Academic Planner dapat menentukan prioritas harian.
3. Sistem mengikuti fakultas yang sedang aktif.
4. Materi dapat dipelajari melalui beberapa sesi.
5. Sistem dapat memberikan latihan.
6. Sistem dapat menjalankan evaluasi harian.
7. Sistem dapat menjadwalkan remedial.
8. Sistem dapat melakukan review mingguan.
9. Sistem dapat melakukan review bulanan.
10. Laporan harian dapat dibuat dan dikirim melalui Telegram.
11. Sistem dapat mencatat kegagalan pengiriman.
12. Pekerjaan dapat dilanjutkan dari checkpoint.
13. Penggunaan biaya dan token dapat dibatasi.
14. Kegagalan model dan sumber dapat ditangani.
15. Scheduler tidak dapat menyetujui kenaikan fakultas.
16. Perubahan jadwal tidak dapat melewati persetujuan Founder.
17. Seluruh aktivitas penting dapat diaudit.

17. Implementation Dependencies

Dokumen ini harus berjalan konsisten dengan:

- "docs/academy/ACADEMIC_SYSTEM.md"
- "docs/academy/FACULTY_PROGRESSION_POLICY.md"
- "docs/academy/ASSESSMENT_POLICY.md"
- "docs/autonomous-learning/AUTONOMOUS_LEARNING_SPEC.md"
- "docs/autonomous-learning/COMPETENCY_CURRICULUM.md"
- "docs/autonomous-learning/EVALUATION_FRAMEWORK.md"
- "docs/architecture/SYSTEM_ARCHITECTURE.md"
- "docs/governance/SECURITY_GOVERNANCE.md"
- "docs/intelligence/MODEL_STRATEGY.md"
- "docs/technical/DATABASE_SCHEMA.md"
- "docs/technical/API_CONTRACTS.md"
- "docs/technical/TEST_STRATEGY.md"

Jika terdapat konflik antar-dokumen, implementasi terkait harus ditahan sampai konflik diselesaikan.

18. Final Operating Principle

Cognis Academy harus berjalan sebagai sistem pendidikan otomatis yang terstruktur.

Cognis menentukan kebutuhan pembelajaran berdasarkan kurikulum dan hasil evaluasi.

Academic Planner menyusun prioritas.

Scheduler mengatur waktu.

Learning Worker menjalankan pembelajaran.

Assessment System mengukur kemampuan.

Report Manager menyampaikan perkembangan kepada Founder.

Founder mengawasi, menguji, dan menentukan persetujuan kenaikan fakultas.

Sistem harus mengutamakan kualitas pembelajaran, konsistensi, transparansi, dan efisiensi sumber daya.

Cognis learns autonomously. The Founder validates progression.

---

End of Document