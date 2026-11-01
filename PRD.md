PRODUCT REQUIREMENTS DOCUMENT (PRD)

COGNIS

Document Version: 1.0
Product Version: MVP v1
Status: Proposed Baseline
Document Owner: Founder
Product Category: Autonomous Learning System
Primary Language: Indonesian
Primary Timezone: Asia/Jakarta

---

1. Product Overview

1.1 Product Name

Cognis

1.2 Product Vision

Cognis adalah Autonomous Learning System (ALS) yang dirancang untuk membangun dan mengembangkan pengetahuan khusus dalam bidang ekonomi, bisnis, geopolitik, keuangan, dan pasar finansial melalui proses penelitian, validasi sumber, evaluasi bukti, penyimpanan pengetahuan, serta evaluasi hasil pembelajaran secara terstruktur.

Cognis tidak dirancang sekadar sebagai chatbot yang menjawab pertanyaan. Tujuan utamanya adalah membangun sistem pembelajaran berkelanjutan yang mampu:

1. Melakukan penelitian berdasarkan topik dan kurikulum.
2. Mengidentifikasi serta memvalidasi sumber informasi.
3. Mengevaluasi kualitas bukti dan kekuatan kesimpulan.
4. Menyimpan hasil pembelajaran beserta asal-usul informasinya.
5. Menghasilkan laporan pembelajaran yang dapat diperiksa manusia.
6. Menyediakan fondasi teknis untuk pengembangan kemampuan pada tahap berikutnya.

Pengembangan kemampuan Cognis harus didasarkan pada bukti, pengujian, dan hasil evaluasi, bukan klaim bahwa sistem telah menjadi lebih pintar.

1.3 Product Philosophy

Cognis dibangun berdasarkan prinsip berikut:

Evidence over Claims

Setiap kesimpulan harus memiliki dasar informasi yang bisa ditelusuri. Sistem tidak boleh mengarang sumber, data, maupun tingkat kepastian.

Learning over Information Collection

Mengumpulkan banyak artikel bukan berarti belajar. Cognis harus mampu mengidentifikasi temuan, hubungan antar-informasi, perbedaan pendapat, serta keterbatasan bukti.

Traceability over Black-Box Decisions

Setiap hasil pembelajaran harus dapat ditelusuri ke proses penelitian, sumber, dan evaluasi yang menghasilkannya.

Controlled Autonomy

Otomatisasi diperbolehkan dalam batas yang sudah ditentukan. Perubahan permanen terhadap kemampuan dan perilaku inti sistem tidak boleh dilakukan secara sepihak oleh AI.

Measured Improvement

Peningkatan kemampuan harus dibuktikan melalui evaluasi yang dapat diulang dan dibandingkan.

---

2. Problem Statement

Sistem AI pada umumnya dapat menghasilkan jawaban dan melakukan penelitian, tetapi memiliki sejumlah kelemahan ketika digunakan sebagai sistem pembelajaran jangka panjang:

1. Informasi yang dikumpulkan dapat bercampur antara fakta, opini, asumsi, dan spekulasi.
2. Kualitas sumber tidak selalu dievaluasi secara konsisten.
3. Kesimpulan dapat kehilangan konteks dan asal-usul bukti.
4. Informasi lama dapat digunakan tanpa mempertimbangkan perubahan kondisi.
5. Riwayat penelitian belum tentu membentuk basis pengetahuan yang terstruktur.
6. Klaim peningkatan kemampuan AI sering tidak disertai pengujian yang memadai.
7. Perubahan sistem secara otomatis berpotensi menghasilkan perilaku yang tidak diinginkan.

Cognis berupaya menyelesaikan masalah tersebut dengan membangun satu pipeline pembelajaran yang konsisten, dapat diulang, dan dapat diaudit.

---

3. Product Goals

3.1 Primary Goals

MVP v1 harus membuktikan lima kemampuan utama:

G1. Automated Research

Cognis mampu menjalankan penelitian berdasarkan topik pembelajaran yang telah ditentukan tanpa harus menerima instruksi manual pada setiap tahap.

G2. Source Validation

Cognis mampu memeriksa kelayakan sumber dan mencatat informasi yang dibutuhkan untuk menilai kredibilitas serta relevansinya.

G3. Evidence Evaluation

Cognis mampu mengidentifikasi klaim, menghubungkannya dengan bukti, membedakan fakta dan interpretasi, serta mencatat ketidakpastian.

G4. Knowledge Persistence

Cognis mampu menyimpan hasil pembelajaran secara terstruktur dengan metadata, riwayat, dan referensi sumber yang dapat ditelusuri.

G5. Learning Reporting

Cognis mampu menghasilkan laporan pembelajaran yang menjelaskan apa yang diteliti, apa yang ditemukan, seberapa kuat buktinya, dan apa yang masih belum diketahui.

3.2 Secondary Goals

MVP juga diharapkan menyediakan fondasi untuk:

- Pelacakan riwayat pembelajaran.
- Pelacakan versi model dan konfigurasi prompt.
- Evaluasi performa pipeline.
- Pengembangan kurikulum berbasis kompetensi.
- Pengembangan mekanisme evaluasi kemampuan pada versi berikutnya.

Fitur sekunder tidak boleh menghambat penyelesaian pipeline utama.

---

4. Non-Goals

Fitur berikut secara eksplisit bukan bagian dari MVP v1:

1. Self-modification terhadap prompt inti, policy, arsitektur, atau aturan sistem.
2. AI menyetujui perubahan permanen yang diusulkannya sendiri.
3. Automatic Founder Approval Workflow.
4. Automatic Competency Aggregation.
5. Automatic Faculty Promotion atau kenaikan tingkat pembelajaran.
6. Model training atau fine-tuning secara otomatis.
7. Pengembangan model foundation sendiri dari awal.
8. Sistem multi-agent kompleks yang belum terbukti dibutuhkan oleh pipeline.
9. Sistem percakapan umum seperti chatbot konsumen.
10. Integrasi Telegram sebagai persyaratan wajib MVP.
11. Sistem multi-region, autoscaling kompleks, dan high availability tingkat enterprise.
12. Sistem model-regression monitoring tingkat lanjut.

Fitur tersebut dapat dipertimbangkan pada versi berikutnya berdasarkan kebutuhan dan hasil evaluasi MVP.

---

5. Target Domain

Cognis memiliki lima domain pengetahuan utama.

5.1 Economics

Mencakup:

- Makroekonomi.
- Mikroekonomi.
- Kebijakan moneter dan fiskal.
- Inflasi dan suku bunga.
- Pertumbuhan ekonomi.
- Perdagangan internasional.
- Struktur dan perkembangan ekonomi Indonesia.
- Teori dan pemikiran ekonomi.

5.2 Business

Mencakup:

- Strategi bisnis.
- Model bisnis.
- Operasional perusahaan.
- Manajemen dan organisasi.
- Ekonomi industri.
- Persaingan pasar.
- Kewirausahaan.
- Analisis perusahaan.

5.3 Geopolitics

Mencakup:

- Hubungan internasional.
- Konflik dan keamanan global.
- Kepentingan strategis negara.
- Energi dan sumber daya.
- Perdagangan dan rantai pasok global.
- Kebijakan luar negeri.
- Risiko geopolitik.

5.4 Finance

Mencakup:

- Sistem keuangan.
- Perbankan.
- Pasar modal.
- Manajemen risiko.
- Instrumen keuangan.
- Keuangan perusahaan.
- Kebijakan dan regulasi keuangan.
- Sistem pembayaran.

5.5 Financial Markets

Mencakup:

- Pasar saham.
- Pasar obligasi.
- Forex.
- Komoditas.
- Emas.
- Cryptocurrency.
- Analisis fundamental.
- Analisis teknikal.
- Struktur pasar dan likuiditas.
- Psikologi serta perilaku pelaku pasar.

Kelima domain tersebut menjadi batas utama pengetahuan Cognis pada MVP. Pengembangan domain baru harus melalui keputusan pengembangan produk, bukan penambahan otomatis oleh AI.

---

6. Target User

6.1 Primary User

Founder atau operator yang bertanggung jawab menentukan arah pembelajaran, memantau hasil, serta mengevaluasi kualitas sistem.

6.2 User Needs

Pengguna membutuhkan sistem yang:

- Dapat menjalankan penelitian secara terjadwal.
- Tidak sekadar mengumpulkan informasi.
- Menghasilkan kesimpulan dengan bukti yang jelas.
- Menampilkan sumber informasi yang digunakan.
- Menjelaskan keterbatasan penelitian.
- Menyimpan hasil pembelajaran untuk ditinjau kembali.
- Memiliki riwayat proses yang dapat diperiksa.
- Tidak mengubah perilaku inti sistem tanpa kendali manusia.

MVP difokuskan pada kebutuhan operator utama. Dukungan banyak pengguna bukan persyaratan yang harus diselesaikan sebelum pipeline pembelajaran dapat dibuktikan.

---

7. Core Product Workflow

7.1 Main Learning Pipeline

Pipeline utama Cognis:

Scheduler → Research → Source Validation → Evidence Evaluation → Knowledge Storage → Learning Report

Setiap tahapan harus menghasilkan keluaran yang dapat digunakan oleh tahap selanjutnya.

7.2 Stage 1: Scheduler

Scheduler bertanggung jawab memulai proses pembelajaran.

Functional Requirements:

- FR-SCH-001: Sistem harus mendukung pemicu pembelajaran secara terjadwal.
- FR-SCH-002: Sistem harus mendukung pemicu pembelajaran secara manual untuk kebutuhan pengujian dan operasional.
- FR-SCH-003: Sistem harus menggunakan konfigurasi waktu yang jelas, termasuk timezone.
- FR-SCH-004: Sistem harus mencatat waktu rencana, waktu mulai, dan waktu selesai setiap job.
- FR-SCH-005: Sistem harus mencegah eksekusi ganda untuk job yang sama ketika terjadi pengulangan pemicu.
- FR-SCH-006: Sistem harus mencatat kegagalan pemicu atau kegagalan pembuatan job.

Expected Output:

- Job ID.
- Topik pembelajaran.
- Domain pembelajaran.
- Waktu eksekusi.
- Status job.
- Konfigurasi pembelajaran yang digunakan.

7.3 Stage 2: Research

Research bertanggung jawab mengumpulkan informasi yang relevan terhadap topik pembelajaran.

Functional Requirements:

- FR-RES-001: Sistem harus mampu melakukan pencarian informasi berdasarkan topik.
- FR-RES-002: Sistem harus mampu mengumpulkan materi dari sumber eksternal yang didukung.
- FR-RES-003: Sistem harus menyimpan metadata setiap materi yang ditemukan.
- FR-RES-004: Sistem harus mengutamakan sumber primer dan sumber yang relevan.
- FR-RES-005: Sistem harus membedakan informasi faktual, opini, interpretasi, dan dugaan.
- FR-RES-006: Sistem harus mencatat waktu penelitian dilakukan.
- FR-RES-007: Sistem harus mencatat kegagalan pencarian atau pengambilan materi.
- FR-RES-008: Sistem tidak boleh menganggap banyaknya materi sebagai ukuran keberhasilan pembelajaran.

Expected Output:

- Research ID.
- Topik penelitian.
- Daftar sumber yang ditemukan.
- Metadata sumber.
- Ringkasan awal informasi.
- Waktu penelitian.
- Status penelitian.

7.4 Stage 3: Source Validation

Source Validation bertanggung jawab mengevaluasi kelayakan sumber penelitian.

Functional Requirements:

- FR-SRC-001: Sistem harus memeriksa apakah sumber dapat diakses.
- FR-SRC-002: Sistem harus mencatat identitas dan URL sumber apabila tersedia.
- FR-SRC-003: Sistem harus mencatat penerbit atau organisasi yang menerbitkan sumber apabila tersedia.
- FR-SRC-004: Sistem harus mencatat tanggal publikasi dan tanggal pembaruan apabila tersedia.
- FR-SRC-005: Sistem harus mengevaluasi relevansi sumber terhadap topik.
- FR-SRC-006: Sistem harus mengevaluasi otoritas dan transparansi sumber.
- FR-SRC-007: Sistem harus mengidentifikasi sumber yang tidak memiliki informasi memadai.
- FR-SRC-008: Sistem harus mencatat alasan ketika sumber dinilai lemah atau tidak layak digunakan.
- FR-SRC-009: Sistem tidak boleh mengarang metadata sumber yang tidak ditemukan.

Dimensi evaluasi sumber minimal mencakup:

1. Authority: kredibilitas penerbit atau penulis.
2. Relevance: keterkaitan dengan topik.
3. Recency: kebaruan informasi sesuai karakter topik.
4. Transparency: kejelasan data, metode, dan referensi.
5. Accessibility: kemampuan sistem mengakses dan memeriksa materi.

Sumber yang gagal divalidasi tidak boleh diam-diam diperlakukan sebagai sumber terpercaya.

Expected Output:

- Source ID.
- Metadata sumber.
- Hasil validasi.
- Alasan penilaian.
- Keterbatasan sumber.
- Status kelayakan sumber.

7.5 Stage 4: Evidence Evaluation

Evidence Evaluation bertanggung jawab mengevaluasi kekuatan bukti dan kesimpulan.

Functional Requirements:

- FR-EVD-001: Sistem harus mengidentifikasi klaim utama dari materi penelitian.
- FR-EVD-002: Sistem harus menghubungkan klaim dengan sumber yang mendukungnya.
- FR-EVD-003: Sistem harus membedakan bukti langsung dan interpretasi.
- FR-EVD-004: Sistem harus mengidentifikasi bukti yang bertentangan.
- FR-EVD-005: Sistem harus menandai klaim yang tidak memiliki dukungan memadai.
- FR-EVD-006: Sistem harus menjelaskan keterbatasan bukti.
- FR-EVD-007: Sistem harus membedakan fakta, inferensi, hipotesis, dan spekulasi.
- FR-EVD-008: Sistem tidak boleh menyajikan kesimpulan yang lemah seolah-olah telah terbukti.
- FR-EVD-009: Sistem harus menyimpan dasar evaluasi agar dapat diperiksa kembali.

Setiap kesimpulan penting minimal memiliki:

- Pernyataan klaim.
- Referensi bukti.
- Hubungan antara bukti dan klaim.
- Penilaian kekuatan dukungan.
- Bukti yang bertentangan apabila ditemukan.
- Keterbatasan dan ketidakpastian.

Penilaian keyakinan model tidak boleh dianggap sebagai bukti kebenaran dengan sendirinya.

Expected Output:

- Claim ID.
- Pernyataan klaim.
- Referensi bukti.
- Hasil evaluasi.
- Tingkat dukungan bukti.
- Kontradiksi.
- Ketidakpastian.
- Kesimpulan evaluasi.

7.6 Stage 5: Knowledge Storage

Knowledge Storage bertanggung jawab menyimpan hasil penelitian dan evaluasi.

Functional Requirements:

- FR-KNO-001: Sistem harus menyimpan hasil penelitian yang telah diproses.
- FR-KNO-002: Sistem harus menyimpan hubungan antara pengetahuan dan sumber asalnya.
- FR-KNO-003: Sistem harus menyimpan hasil evaluasi bukti.
- FR-KNO-004: Sistem harus menyimpan metadata waktu dan identitas job.
- FR-KNO-005: Sistem harus menghindari duplikasi data yang tidak diperlukan.
- FR-KNO-006: Sistem harus mempertahankan riwayat perubahan data.
- FR-KNO-007: Sistem harus mampu menandai informasi yang sudah kedaluwarsa atau berpotensi tidak relevan.
- FR-KNO-008: Sistem tidak boleh menghapus informasi lama secara otomatis hanya karena ditemukan informasi baru.
- FR-KNO-009: Sistem harus memungkinkan penelusuran dari hasil pembelajaran kembali ke sumber aslinya.

Pengetahuan yang disimpan pada MVP merupakan basis pengetahuan referensial yang memiliki provenance.

Penyimpanan pengetahuan tidak berarti model telah dilatih ulang, prompt inti telah berubah, atau policy sistem telah dimodifikasi.

Expected Output:

- Knowledge ID.
- Isi pengetahuan.
- Domain dan topik.
- Referensi klaim.
- Referensi sumber.
- Metadata penelitian.
- Waktu penyimpanan.
- Informasi versi atau riwayat.

7.7 Stage 6: Learning Report

Learning Report bertanggung jawab menghasilkan laporan akhir dari satu proses pembelajaran.

Functional Requirements:

- FR-RPT-001: Sistem harus menghasilkan laporan setelah pipeline selesai.
- FR-RPT-002: Laporan harus menjelaskan topik dan tujuan pembelajaran.
- FR-RPT-003: Laporan harus menjelaskan sumber yang digunakan.
- FR-RPT-004: Laporan harus menjelaskan temuan utama.
- FR-RPT-005: Laporan harus membedakan fakta, interpretasi, dan hipotesis.
- FR-RPT-006: Laporan harus menjelaskan kekuatan dan keterbatasan bukti.
- FR-RPT-007: Laporan harus mencantumkan pertentangan informasi apabila ditemukan.
- FR-RPT-008: Laporan harus menjelaskan bagian yang belum dapat disimpulkan.
- FR-RPT-009: Laporan harus menyimpan identitas job dan waktu proses.
- FR-RPT-010: Laporan harus menggunakan bahasa Indonesia sebagai bahasa utama.
- FR-RPT-011: Laporan harus dapat diakses kembali setelah proses selesai.

Minimum Report Structure:

1. Identitas pembelajaran.
2. Topik dan tujuan penelitian.
3. Ringkasan eksekutif.
4. Temuan utama.
5. Bukti dan sumber pendukung.
6. Perbedaan informasi atau kontradiksi.
7. Analisis dan interpretasi.
8. Keterbatasan penelitian.
9. Kesimpulan.
10. Pertanyaan atau kebutuhan penelitian lanjutan.

Expected Output:

- Report ID.
- Job ID.
- Ringkasan pembelajaran.
- Temuan.
- Referensi sumber.
- Hasil evaluasi.
- Kesimpulan.
- Keterbatasan.
- Waktu pembuatan laporan.

---

8. Job Lifecycle Requirements

Setiap proses pembelajaran harus memiliki identitas job yang unik dan status yang dapat dilacak.

8.1 Job Observability

Sistem setidaknya harus dapat membedakan kondisi berikut:

- Queued: job menunggu eksekusi.
- Running: job sedang diproses.
- Completed: seluruh pipeline berhasil diselesaikan.
- Failed: job gagal dan tidak dapat menyelesaikan proses.
- Cancelled: job dihentikan secara eksplisit.

Status teknis tambahan dapat ditentukan dalam Technical Design, tetapi tidak boleh mencampurkan status eksekusi dengan keputusan persetujuan manusia.

8.2 Job History

Setiap job harus mencatat:

- Job ID.
- Pemicu job.
- Topik dan domain.
- Waktu pembuatan.
- Waktu mulai.
- Waktu selesai.
- Status akhir.
- Tahap terakhir yang berhasil.
- Ringkasan kegagalan jika ada.
- Versi model dan konfigurasi yang digunakan.

8.3 Failure Handling

Jika sebuah tahap gagal:

1. Sistem harus mencatat tahap yang gagal.
2. Sistem harus mencatat alasan kegagalan jika dapat diketahui.
3. Sistem harus mempertahankan hasil tahap sebelumnya yang sudah tersimpan dengan aman.
4. Sistem harus mengikuti kebijakan retry yang ditentukan oleh konfigurasi teknis.
5. Sistem tidak boleh menandai job sebagai Completed apabila pipeline belum selesai.

Kegagalan satu job tidak boleh merusak riwayat job lain.

---

9. Product Interface Requirements

MVP membutuhkan akses operasional yang memungkinkan Founder memeriksa proses dan hasil pembelajaran.

Minimum interface capabilities:

1. Melihat daftar job pembelajaran.
2. Melihat status job.
3. Menjalankan pembelajaran secara manual.
4. Melihat detail satu job.
5. Membaca laporan pembelajaran.
6. Menelusuri sumber yang digunakan.
7. Melihat informasi kegagalan.
8. Mengakses riwayat pembelajaran.

Antarmuka boleh menggunakan web interface, API, atau mekanisme operasional yang sudah tersedia pada proyek.

Namun, seluruh kemampuan inti harus dapat diakses dan diverifikasi tanpa mengandalkan klaim yang hanya muncul dalam log model.

Integrasi Telegram bukan persyaratan wajib MVP v1.

---

10. Language and Output Standards

10.1 Primary Language

Bahasa Indonesia menjadi bahasa utama untuk seluruh laporan dan penjelasan yang ditampilkan kepada pengguna.

Istilah teknis bahasa Inggris boleh digunakan apabila lebih tepat, tetapi harus dijelaskan ketika diperlukan.

10.2 Writing Standards

Hasil pembelajaran harus:

- Jelas dan terstruktur.
- Tidak bertele-tele.
- Tidak menggunakan klaim tanpa dasar.
- Tidak menyamakan korelasi dengan sebab-akibat.
- Tidak menghilangkan informasi yang bertentangan.
- Tidak membuat angka atau sumber fiktif.
- Tidak menyembunyikan ketidakpastian.
- Tidak menggunakan bahasa yang memberikan kesan pasti ketika bukti masih lemah.

10.3 Analytical Standards

Untuk topik ekonomi, bisnis, geopolitik, keuangan, dan pasar finansial, Cognis harus mempertimbangkan konteks waktu dan kondisi ketika informasi tersebut berlaku.

Data historis tidak boleh diperlakukan sebagai kondisi terkini.

Prediksi harus dipisahkan dari fakta dan harus menyebutkan asumsi yang digunakan.

---

11. Governance and Autonomy Boundaries

11.1 Permitted Autonomy

Pada MVP, Cognis diperbolehkan secara otomatis:

- Menjalankan job terjadwal.
- Melakukan penelitian.
- Mengumpulkan materi.
- Mengevaluasi sumber.
- Mengevaluasi bukti.
- Menyimpan hasil pembelajaran sebagai pengetahuan referensial.
- Menghasilkan laporan.
- Mencatat kegagalan dan hasil evaluasi.

11.2 Restricted Actions

Pada MVP, Cognis tidak diperbolehkan secara otomatis:

- Mengubah system prompt permanen.
- Mengubah policy atau security rules.
- Mengubah arsitektur sistem.
- Mengubah konfigurasi inti secara permanen.
- Mengubah kurikulum utama secara permanen.
- Mengubah standar evaluasi secara permanen.
- Mengaktifkan kemampuan baru tanpa proses pengembangan.
- Menghapus aturan governance.
- Mengklaim dirinya meningkat kemampuannya tanpa evaluasi.

11.3 Future Governance Model

Mekanisme pengajuan perubahan oleh AI, persetujuan Founder, penerapan perubahan, pengujian, dan rollback merupakan bagian dari arah pengembangan ALS berikutnya.

Fitur tersebut tidak menjadi ketergantungan MVP v1.

Pemisahan ini harus tetap dipertahankan agar sistem pembelajaran tidak memperoleh kewenangan mengubah aturan yang mengendalikan dirinya sendiri.

---

12. Model and Provider Requirements

MVP harus memiliki pengelolaan penggunaan model yang dapat ditelusuri.

Functional Requirements:

- FR-MOD-001: Sistem harus mencatat model yang digunakan untuk setiap job.
- FR-MOD-002: Sistem harus mencatat provider model.
- FR-MOD-003: Sistem harus mencatat versi atau identitas model apabila tersedia.
- FR-MOD-004: Sistem harus mencatat konfigurasi prompt atau versi prompt yang digunakan.
- FR-MOD-005: Sistem harus mencatat kegagalan pemanggilan model.
- FR-MOD-006: Sistem harus dapat membedakan hasil dari model atau konfigurasi yang berbeda.
- FR-MOD-007: Sistem tidak boleh menganggap perpindahan model sebagai peningkatan kemampuan otomatis.

Pilihan provider dan mekanisme integrasi teknis ditentukan dalam dokumen desain teknis.

---

13. Non-Functional Requirements

13.1 Reliability

- NFR-REL-001: Kegagalan satu job tidak boleh menghilangkan data job lain.
- NFR-REL-002: Proses yang gagal harus memiliki catatan kegagalan.
- NFR-REL-003: Sistem harus dapat melanjutkan operasional setelah kegagalan yang dapat dipulihkan.
- NFR-REL-004: Status job harus mencerminkan kondisi proses sebenarnya.

13.2 Data Integrity

- NFR-DAT-001: Setiap laporan harus terhubung dengan job asalnya.
- NFR-DAT-002: Setiap klaim penting dalam laporan harus dapat ditelusuri ke bukti atau diberi label belum terverifikasi.
- NFR-DAT-003: Identitas sumber harus dipertahankan.
- NFR-DAT-004: Sistem tidak boleh mengubah kegagalan validasi menjadi keberhasilan secara diam-diam.
- NFR-DAT-005: Perubahan data harus mempertahankan riwayat yang diperlukan untuk audit.

13.3 Security

- NFR-SEC-001: Kredensial dan API key tidak boleh disimpan dalam source code.
- NFR-SEC-002: Akses terhadap fungsi operasional harus dibatasi sesuai kebutuhan.
- NFR-SEC-003: Input eksternal harus diperlakukan sebagai data yang tidak tepercaya.
- NFR-SEC-004: Instruksi yang ditemukan dalam sumber penelitian tidak boleh otomatis diperlakukan sebagai instruksi sistem.
- NFR-SEC-005: Sistem harus melindungi data dan konfigurasi internal dari perubahan yang tidak berwenang.

13.4 Resource Efficiency

- NFR-RES-001: Proses penelitian harus memiliki batas penggunaan resource.
- NFR-RES-002: Pemanggilan model dan sumber eksternal harus memperhitungkan biaya serta batas penggunaan.
- NFR-RES-003: Kegagalan provider tidak boleh menyebabkan retry tanpa batas.
- NFR-RES-004: Sistem harus mencatat penggunaan resource yang relevan apabila tersedia.
- NFR-RES-005: Desain harus memungkinkan penggunaan model berbeda berdasarkan kebutuhan tugas.

13.5 Maintainability

- NFR-MNT-001: Komponen pipeline harus memiliki tanggung jawab yang jelas.
- NFR-MNT-002: Kegagalan setiap tahap harus dapat diidentifikasi.
- NFR-MNT-003: Perubahan pada satu tahap tidak boleh menimbulkan ketergantungan tersembunyi pada tahap lain.
- NFR-MNT-004: Implementasi harus dapat diuji secara terpisah dan secara end-to-end.

---

14. Acceptance Criteria

MVP v1 dinyatakan memenuhi tujuan produk apabila seluruh kriteria berikut berhasil diverifikasi.

14.1 Scheduler

- Job dapat dijalankan secara manual.
- Job dapat dipicu oleh jadwal yang telah dikonfigurasi.
- Setiap job memiliki identitas yang dapat dilacak.
- Pemicu berulang tidak menghasilkan eksekusi ganda untuk permintaan yang sama.

14.2 Research

- Sistem dapat meneliti topik yang telah ditentukan.
- Hasil penelitian memiliki identitas sumber.
- Kegagalan pengambilan materi tercatat.
- Materi yang ditemukan dapat diteruskan ke tahap validasi.

14.3 Source Validation

- Sumber dievaluasi berdasarkan dimensi yang ditentukan.
- Sumber yang lemah dapat diidentifikasi.
- Metadata yang tidak ditemukan tidak boleh dibuat-buat.
- Hasil validasi dapat diperiksa kembali.

14.4 Evidence Evaluation

- Klaim utama dapat diidentifikasi.
- Klaim dapat dihubungkan dengan bukti.
- Informasi yang bertentangan dapat ditandai.
- Ketidakpastian dan keterbatasan bukti ditampilkan.
- Kesimpulan yang tidak memiliki dukungan memadai tidak disajikan sebagai fakta.

14.5 Knowledge Storage

- Hasil pembelajaran dapat disimpan.
- Hubungan antara pengetahuan, klaim, dan sumber dipertahankan.
- Pengetahuan dapat ditemukan kembali.
- Riwayat asal-usul data tidak hilang.

14.6 Learning Report

- Laporan dihasilkan dari job yang selesai.
- Laporan dapat dibaca dan diakses kembali.
- Laporan memiliki referensi sumber.
- Keterbatasan penelitian dinyatakan.
- Laporan tidak memuat sumber atau data yang direkayasa oleh model.

14.7 Governance

- Tidak ada perubahan permanen terhadap prompt inti, policy, atau arsitektur yang dilakukan secara otomatis.
- Sistem tidak dapat menyetujui perubahan permanen yang diusulkannya sendiri.
- Batas kewenangan otomatis dapat diverifikasi melalui pengujian.

14.8 End-to-End Verification

Sistem harus berhasil menyelesaikan satu siklus penuh:

Scheduler → Research → Source Validation → Evidence Evaluation → Knowledge Storage → Learning Report

Pengujian harus membuktikan bahwa:

1. Setiap tahap menerima input yang sesuai.
2. Setiap tahap menghasilkan output yang dapat diperiksa.
3. Identitas job dan hubungan antar-data tetap konsisten.
4. Kegagalan dapat dicatat tanpa merusak data sebelumnya.
5. Laporan akhir dapat ditelusuri ke sumber penelitian.

---

15. Success Metrics

Keberhasilan MVP tidak diukur dari seberapa pintar Cognis mengaku dirinya sendiri.

Pengukuran awal menggunakan metrik berikut.

15.1 Pipeline Completion Rate

Mengukur persentase job yang berhasil menyelesaikan seluruh pipeline.

Target pilot awal: minimal 8 dari 10 job pengujian berhasil diselesaikan.

15.2 Source Traceability

Mengukur persentase klaim penting dalam laporan yang memiliki referensi bukti atau label eksplisit bahwa klaim tersebut belum terverifikasi.

Target: 100% klaim penting memenuhi ketentuan tersebut.

15.3 Data Provenance Integrity

Mengukur kemampuan sistem mempertahankan hubungan antara job, penelitian, sumber, klaim, pengetahuan, dan laporan.

Target: seluruh objek pada pengujian end-to-end memiliki hubungan yang benar.

15.4 Failure Observability

Mengukur apakah kegagalan dapat diketahui melalui catatan job dan tahap yang gagal.

Target: seluruh skenario kegagalan yang diuji menghasilkan status dan catatan yang sesuai.

15.5 Report Quality

Kualitas laporan dievaluasi melalui pemeriksaan manusia berdasarkan:

- Relevansi terhadap topik.
- Ketepatan penggunaan sumber.
- Kekuatan bukti.
- Konsistensi kesimpulan.
- Transparansi ketidakpastian.
- Keterbacaan laporan.

Hasil evaluasi kualitas laporan harus dicatat untuk menentukan baseline peningkatan pada versi berikutnya.

15.6 Measurement Integrity

Tidak boleh ada klaim keberhasilan atau peningkatan performa yang tidak memiliki hasil pengujian pendukung.

Target angka untuk kualitas analisis dan akurasi kesimpulan harus ditetapkan setelah baseline pengujian tersedia.

---

16. MVP Development Priorities

Urutan prioritas implementasi:

P0 - Core Learning Pipeline

Seluruh komponen berikut wajib tersedia:

1. Scheduler.
2. Research.
3. Source Validation.
4. Evidence Evaluation.
5. Knowledge Storage.
6. Learning Report.
7. Job lifecycle dan observability.
8. End-to-end testing.

Tanpa seluruh komponen ini, MVP belum dianggap selesai.

P1 - Operational Reliability

Setelah pipeline utama berfungsi:

1. Peningkatan error handling.
2. Mekanisme retry yang terkontrol.
3. Penguatan data integrity.
4. Riwayat dan pencarian job.
5. Monitoring penggunaan resource.
6. Pengujian skenario kegagalan.

P2 - Future Expansion Foundation

Persiapan untuk versi selanjutnya:

1. Competency tracking.
2. Curriculum progression.
3. Learning quality benchmarks.
4. Candidate improvement proposals.
5. Founder approval workflow.
6. Controlled system improvement.
7. Rollback management.

P2 tidak boleh menjadi alasan untuk menunda penyelesaian P0.

---

17. Key Risks

17.1 Hallucinated Research

Risk: Model menghasilkan sumber, data, atau temuan yang tidak benar-benar ditemukan.

Mitigation: Validasi sumber, penyimpanan metadata, pemeriksaan referensi, dan pengujian traceability.

17.2 Weak Evidence Evaluation

Risk: Model menerima kesimpulan dari bukti yang tidak cukup atau tidak relevan.

Mitigation: Evaluasi hubungan klaim dan bukti, pencatatan kontradiksi, serta pemeriksaan manusia terhadap sampel laporan.

17.3 Outdated Information

Risk: Informasi lama digunakan untuk menjelaskan kondisi terkini.

Mitigation: Pencatatan tanggal informasi dan evaluasi recency sesuai karakter topik.

17.4 Excessive Automation

Risk: Sistem memperoleh kewenangan terlalu besar sebelum kualitas proses pembelajaran terbukti.

Mitigation: Memisahkan kemampuan penelitian otomatis dari perubahan permanen sistem.

17.5 Uncontrolled Resource Usage

Risk: Penelitian dan pemanggilan model menghasilkan biaya atau penggunaan resource yang tidak terkendali.

Mitigation: Batas resource, retry terbatas, pencatatan penggunaan, dan konfigurasi operasional.

17.6 False Learning Claims

Risk: Sistem mengklaim mengalami peningkatan kemampuan hanya karena memiliki lebih banyak data atau menghasilkan laporan lebih panjang.

Mitigation: Pengukuran berbasis benchmark dan perbandingan hasil evaluasi yang konsisten.

---

18. Dependencies and Open Decisions

Keputusan berikut harus diselesaikan dalam dokumen desain dan implementasi terkait, bukan diasumsikan telah ditentukan oleh PRD.

1. Provider dan mekanisme web research.
2. Provider model dan strategi penggunaan model.
3. Teknologi backend dan database.
4. Teknologi scheduler dan mekanisme job execution.
5. Mekanisme penyimpanan dokumen dan knowledge retrieval.
6. Mekanisme autentikasi serta otorisasi operasional.
7. Format metadata dan skema data.
8. Batas penggunaan resource dan biaya.
9. Metode evaluasi sumber dan bukti secara teknis.
10. Mekanisme backup dan recovery.

Keputusan teknis harus didokumentasikan pada dokumen yang menjadi tanggung jawabnya.

Apabila terdapat keputusan yang belum ditentukan, implementasi harus mencatatnya sebagai open decision dan tidak menyamarkannya sebagai keputusan final.

---

19. Definition of MVP Completion

MVP v1 dapat dinyatakan selesai apabila:

1. Seluruh tahapan core learning pipeline telah diimplementasikan.
2. Pipeline dapat dijalankan secara manual dan terjadwal.
3. Setiap tahapan memiliki input dan output yang dapat diverifikasi.
4. Sumber dan bukti dapat ditelusuri dari laporan.
5. Pengetahuan dapat disimpan dan ditemukan kembali.
6. Job lifecycle dan kegagalan dapat dipantau.
7. Pengujian unit, integrasi, dan end-to-end yang relevan telah dijalankan.
8. Tidak terdapat pelanggaran terhadap batas governance MVP.
9. Dokumentasi implementasi sesuai dengan kondisi sistem yang benar-benar berjalan.
10. Hasil pengujian dan keterbatasan MVP dilaporkan secara jujur.

Fitur yang belum masuk dalam ruang lingkup MVP tidak boleh digunakan sebagai alasan untuk mengklaim MVP telah gagal, selama seluruh acceptance criteria MVP telah terpenuhi.

Sebaliknya, dokumentasi yang lengkap tanpa implementasi dan pengujian yang berhasil tidak dapat dianggap sebagai penyelesaian MVP.

---

20. Final Product Principle

Cognis harus berkembang melalui proses pembelajaran yang dapat dibuktikan.

Sistem tidak dinilai berdasarkan banyaknya informasi yang dikumpulkan, panjangnya laporan, jumlah model yang digunakan, atau kompleksitas arsitekturnya.

Sistem dinilai berdasarkan kemampuannya untuk:

- Menemukan informasi yang relevan.
- Memvalidasi sumber.
- Menilai kekuatan bukti.
- Menghasilkan kesimpulan yang proporsional.
- Menyimpan pengetahuan dengan provenance.
- Menjelaskan keterbatasannya.
- Menghasilkan pembelajaran yang dapat diperiksa dan diuji kembali.

Prinsip utama Cognis: jangan mengklaim tahu apabila bukti belum cukup, dan jangan mengklaim berkembang apabila peningkatannya belum terukur.