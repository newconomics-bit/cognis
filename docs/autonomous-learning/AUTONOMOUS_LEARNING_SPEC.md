Autonomous Learning System Specification

Project: Cognis AI
Document: Autonomous Learning System Specification
Version: 1.0
Status: Proposed
Language: Bahasa Indonesia
Parent Documents: "AGENTS.md", "PRD.md", "docs/architecture/SYSTEM_ARCHITECTURE.md"

---

1. Tujuan

Dokumen ini mendefinisikan cara kerja Autonomous Learning System (ALS) pada Cognis AI.

ALS merupakan sistem pembelajaran terstruktur yang memungkinkan Cognis untuk:

1. Menerima tujuan dan arahan pembelajaran dari pengguna.
2. Mengidentifikasi kompetensi yang perlu dikembangkan.
3. Melakukan riset dan mengumpulkan sumber informasi.
4. Mengevaluasi kualitas dan relevansi informasi.
5. Menyusun pengetahuan baru secara terstruktur.
6. Menguji peningkatan kemampuan melalui evaluasi dan benchmark.
7. Mengidentifikasi kelemahan serta mengusulkan perbaikan.
8. Meminta persetujuan pengguna sebelum menerapkan perubahan permanen yang memengaruhi sistem.
9. Memverifikasi hasil perubahan dan melakukan rollback apabila terjadi regresi.

ALS tidak boleh menyamakan aktivitas membaca, menyimpan informasi, dan peningkatan kecerdasan. Peningkatan kemampuan harus dibuktikan melalui hasil evaluasi.

2. Prinsip Dasar

2.1 Evidence-Based Learning

Setiap pengetahuan baru harus didukung oleh sumber atau bukti yang dapat diperiksa.

Sistem wajib membedakan:

- Fakta terverifikasi.
- Klaim dari sumber tertentu.
- Interpretasi atau analisis.
- Asumsi.
- Hipotesis.
- Prediksi.
- Informasi yang belum dapat diverifikasi.

Sistem dilarang mengubah hipotesis menjadi fakta hanya karena hipotesis tersebut muncul berulang kali.

2.2 Competency-Based Learning

Pembelajaran harus diarahkan pada penguasaan kompetensi, bukan sekadar penyelesaian materi.

Setiap aktivitas pembelajaran harus memiliki hubungan dengan satu atau lebih kompetensi dalam "COMPETENCY_CURRICULUM.md".

2.3 Measurable Improvement

Setiap klaim peningkatan kemampuan harus memiliki hasil evaluasi yang bisa dibandingkan.

Sistem harus membedakan:

- Knowledge acquisition: pengetahuan baru berhasil diperoleh.
- Skill development: kemampuan menjalankan tugas meningkat.
- Performance improvement: hasil benchmark meningkat.
- Operational improvement: sistem menjadi lebih efisien, stabil, atau akurat.

Keempat hal tersebut tidak boleh dianggap sebagai ukuran yang sama.

2.4 Human-Governed Evolution

ALS boleh melakukan riset, analisis, eksperimen yang aman, dan menyusun proposal perubahan secara otomatis.

Namun, perubahan permanen yang memengaruhi perilaku, konfigurasi penting, kebijakan, arsitektur, kode produksi, atau parameter model harus melalui persetujuan pengguna sesuai mekanisme governance.

2.5 Reproducibility

Setiap proses pembelajaran harus memiliki catatan yang cukup untuk ditelusuri dan diulang.

Catatan minimal mencakup:

- Tujuan pembelajaran.
- Waktu pelaksanaan.
- Versi model dan konfigurasi.
- Sumber informasi.
- Metode yang digunakan.
- Hasil evaluasi.
- Kesimpulan.
- Status persetujuan.
- Perubahan yang diterapkan, jika ada.

---

3. Batasan Autonomous Learning

ALS memiliki tiga tingkat aktivitas.

Level 1: Autonomous Research

Sistem boleh melakukan aktivitas berikut tanpa persetujuan untuk setiap langkah:

- Menerima tugas pembelajaran yang telah diberikan.
- Menyusun rencana riset.
- Mengumpulkan sumber.
- Membaca dan meringkas informasi.
- Membandingkan berbagai perspektif.
- Mengidentifikasi kontradiksi.
- Menyusun catatan pengetahuan.
- Melakukan pemeriksaan kualitas sumber.
- Menghasilkan laporan pembelajaran.
- Menjalankan evaluasi dalam lingkungan yang aman.

Hasil pada level ini belum otomatis menjadi perubahan permanen pada sistem.

Level 2: Controlled Experimentation

Sistem boleh melakukan eksperimen yang memiliki batasan jelas pada lingkungan terisolasi.

Contoh:

- Membandingkan beberapa prompt.
- Menguji konfigurasi model.
- Menguji metode retrieval.
- Menguji strategi analisis.
- Membandingkan pendekatan penyelesaian tugas.
- Menguji pipeline pembelajaran pada dataset evaluasi.

Eksperimen tidak boleh mengubah lingkungan produksi secara langsung.

Eksperimen harus memiliki batasan biaya, waktu, data, serta ruang lingkup.

Level 3: Approved System Evolution

Perubahan permanen hanya boleh diterapkan setelah memperoleh persetujuan pengguna.

Contoh:

- Menambahkan pengetahuan ke basis pengetahuan permanen.
- Mengubah kurikulum kompetensi.
- Mengubah konfigurasi utama.
- Mengubah system prompt inti.
- Mengubah alur kerja agent.
- Memperbarui kode produksi.
- Mengubah kebijakan operasional.
- Melakukan fine-tuning atau pembaruan bobot model.

Persetujuan harus mengacu pada proposal perubahan yang spesifik. Persetujuan terhadap satu proposal tidak otomatis menjadi izin untuk perubahan lain.

---

4. Learning Lifecycle

Setiap siklus pembelajaran mengikuti tahapan berikut:

1. Objective Definition
2. Competency Mapping
3. Learning Planning
4. Research and Evidence Collection
5. Information Validation
6. Knowledge Synthesis
7. Knowledge Structuring
8. Competency Evaluation
9. Learning Report
10. Improvement Proposal
11. Human Approval
12. Controlled Implementation
13. Post-Implementation Evaluation
14. Rollback or Finalization

4.1 Objective Definition

Sistem menentukan tujuan pembelajaran berdasarkan instruksi pengguna atau tugas yang telah disetujui.

Setiap tujuan harus spesifik dan dapat dievaluasi.

Contoh tujuan yang baik:

"Mempelajari hubungan kebijakan suku bunga Federal Reserve terhadap pergerakan DXY, US Treasury yield, dan harga emas."

Contoh tujuan yang buruk:

"Belajar ekonomi lebih dalam."

Tujuan yang terlalu luas harus dipecah menjadi beberapa subtujuan.

4.2 Competency Mapping

Sistem menghubungkan tujuan pembelajaran dengan kompetensi dalam kurikulum.

Contoh:

Tujuan| Kompetensi
Menganalisis kebijakan moneter| Monetary Economics
Memahami pergerakan yield| Fixed Income Fundamentals
Menganalisis harga emas| Financial Market Analysis
Menghubungkan beberapa variabel| Causal Reasoning
Membuat kesimpulan| Evidence-Based Reasoning

Jika kompetensi belum tersedia, sistem boleh mengusulkan kompetensi baru. Penambahan permanen mengikuti persetujuan pengguna.

4.3 Learning Planning

Sistem menyusun rencana pembelajaran yang berisi:

- Pertanyaan utama.
- Subpertanyaan.
- Sumber yang dibutuhkan.
- Metode riset.
- Target hasil.
- Kompetensi terkait.
- Kriteria keberhasilan.
- Estimasi biaya API.
- Estimasi durasi.
- Risiko dan keterbatasan.

Sistem harus memprioritaskan sumber yang kredibel dan relevan.

4.4 Research and Evidence Collection

Sistem mengumpulkan informasi dari sumber yang tersedia.

Prioritas sumber bergantung pada konteks, tetapi secara umum mencakup:

1. Publikasi akademik dan jurnal ilmiah.
2. Data dan publikasi institusi resmi.
3. Laporan perusahaan dan organisasi.
4. Buku dan referensi profesional.
5. Media berita bereputasi.
6. Analisis industri dan penelitian independen.
7. Diskusi komunitas sebagai sumber pengalaman atau opini, bukan otomatis fakta.

Sistem harus memperhatikan tanggal publikasi, periode data, konteks, dan kemungkinan konflik kepentingan.

Untuk informasi yang berubah cepat, sistem wajib memperhatikan kebaruan data.

4.5 Information Validation

Sebelum informasi masuk ke tahap sintesis, sistem harus mengevaluasi:

- Kredibilitas sumber.
- Relevansi terhadap tujuan.
- Kejelasan metodologi.
- Konsistensi informasi.
- Kecocokan periode data.
- Potensi bias.
- Ketersediaan bukti pendukung.
- Tingkat ketidakpastian.

Klaim penting sebaiknya diperiksa melalui lebih dari satu sumber independen apabila memungkinkan.

Sumber yang saling mengutip tidak boleh dianggap sebagai bukti independen.

Jika sumber bertentangan, sistem harus mencatat pertentangan tersebut dan tidak memaksakan satu kesimpulan tanpa dasar.

4.6 Knowledge Synthesis

Sistem menyusun informasi menjadi pemahaman yang koheren.

Hasil sintesis harus mencakup:

- Konsep utama.
- Hubungan antarvariabel.
- Mekanisme atau proses.
- Bukti pendukung.
- Perbedaan perspektif.
- Kontradiksi.
- Keterbatasan.
- Kesimpulan.
- Pertanyaan lanjutan.

Sistem harus menghindari ringkasan yang hanya menggabungkan potongan informasi tanpa menjelaskan hubungan sebab-akibat.

4.7 Knowledge Structuring

Pengetahuan hasil pembelajaran harus disusun dalam format terstruktur.

Setiap catatan pengetahuan minimal memiliki:

- Unique ID.
- Judul.
- Domain.
- Subdomain.
- Kompetensi terkait.
- Ringkasan.
- Isi utama.
- Jenis klaim.
- Sumber referensi.
- Tanggal pengumpulan.
- Tanggal pembaruan.
- Tingkat keyakinan.
- Keterbatasan.
- Status verifikasi.
- Versi catatan.

Sistem juga harus mendeteksi kemungkinan duplikasi dan konflik dengan pengetahuan yang sudah ada.

Pengetahuan baru tidak boleh menimpa catatan sebelumnya tanpa proses pembaruan yang dapat ditelusuri.

---

5. Knowledge Promotion Policy

ALS harus membedakan pengetahuan sementara dan pengetahuan permanen.

5.1 Temporary Research Notes

Catatan sementara berisi hasil pengumpulan informasi yang belum selesai divalidasi.

Catatan ini tidak boleh diperlakukan sebagai pengetahuan terverifikasi.

5.2 Candidate Knowledge

Pengetahuan yang telah melalui proses validasi dan sintesis dapat diajukan sebagai Candidate Knowledge.

Candidate Knowledge dapat digunakan dalam eksperimen atau evaluasi terbatas, dengan statusnya tetap terlihat.

5.3 Approved Knowledge

Pengetahuan menjadi Approved Knowledge setelah melewati proses governance dan persetujuan yang sesuai.

Status ini tidak berarti informasi tersebut selalu benar. Informasi tetap dapat diperbarui ketika ditemukan bukti baru.

5.4 Archived Knowledge

Pengetahuan yang sudah tidak relevan, kedaluwarsa, atau terbukti keliru harus dapat diarsipkan.

Catatan lama tetap dipertahankan untuk audit dan penelusuran perubahan.

---

6. Continuous Evaluation

ALS tidak boleh menilai keberhasilannya hanya berdasarkan jumlah materi yang dibaca atau catatan yang disimpan.

Evaluasi harus mengukur kemampuan menyelesaikan tugas.

6.1 Evaluation Methods

Metode evaluasi dapat mencakup:

- Knowledge recall.
- Conceptual understanding.
- Problem solving.
- Quantitative reasoning.
- Causal analysis.
- Evidence assessment.
- Research quality.
- Decision-making.
- Cross-domain reasoning.
- Practical task execution.

6.2 Baseline Evaluation

Sebelum program pembelajaran dimulai, sistem harus membuat baseline untuk kompetensi yang relevan.

Baseline menjadi titik pembanding untuk evaluasi berikutnya.

6.3 Post-Learning Evaluation

Setelah pembelajaran, sistem menjalankan evaluasi menggunakan tugas yang sesuai dengan kompetensi target.

Evaluasi sebaiknya menggunakan kasus yang tidak identik dengan contoh yang dipakai selama pembelajaran.

6.4 Holdout Evaluation

Sistem harus menyediakan pertanyaan atau kasus evaluasi yang tidak digunakan sebagai bahan pembelajaran langsung.

Tujuannya untuk mengukur apakah kemampuan benar-benar meningkat, bukan hanya menghafal jawaban.

6.5 Regression Evaluation

Sebelum dan sesudah perubahan sistem, evaluasi harus memeriksa apakah kemampuan lain mengalami penurunan.

Peningkatan satu kompetensi tidak boleh dibayar dengan kerusakan kemampuan yang sebelumnya sudah baik tanpa alasan dan persetujuan yang jelas.

---

7. Improvement Proposal Engine

Setelah evaluasi, ALS menganalisis kelemahan yang ditemukan.

Contoh kategori kelemahan:

- Kurangnya pengetahuan dasar.
- Kesalahan penalaran.
- Pemahaman konsep yang dangkal.
- Ketergantungan pada satu sumber.
- Kesalahan interpretasi data.
- Ketidakmampuan menghubungkan beberapa domain.
- Kualitas riset yang buruk.
- Penggunaan model yang tidak sesuai.
- Retrieval yang tidak relevan.
- Prompt atau workflow yang tidak efektif.

Sistem kemudian menyusun Improvement Proposal.

7.1 Proposal Structure

Setiap proposal wajib berisi:

1. Proposal ID.
2. Judul perubahan.
3. Masalah yang ditemukan.
4. Bukti yang mendukung temuan.
5. Akar masalah yang diduga.
6. Solusi yang diusulkan.
7. Komponen yang terdampak.
8. Estimasi biaya.
9. Risiko.
10. Rencana pengujian.
11. Kriteria keberhasilan.
12. Rencana rollback.
13. Dampak jika proposal ditolak.

Proposal harus menjelaskan mengapa solusi tersebut lebih baik daripada kondisi saat ini.

7.2 Proposal Priority

Proposal dapat dikategorikan berdasarkan:

- Critical: berhubungan dengan keamanan, integritas data, atau kegagalan sistem serius.
- High: kelemahan yang berdampak besar terhadap kualitas hasil.
- Medium: peningkatan kualitas yang bermanfaat tetapi tidak mendesak.
- Low: optimasi kecil atau peningkatan kenyamanan.

Prioritas harus didukung alasan yang jelas, bukan sekadar penilaian subjektif model.

---

8. Human Approval and Governance

8.1 Approval Requirement

Setiap proposal perubahan permanen harus menunggu persetujuan pengguna.

Status proposal:

- Draft.
- Under Review.
- Approved.
- Rejected.
- Expired.
- Implementing.
- Testing.
- Completed.
- Rolled Back.
- Failed.

8.2 Approval Interface

Pengguna harus menerima ringkasan yang mudah dipahami melalui Telegram atau antarmuka Cognis.

Ringkasan minimal mencakup:

- Apa yang ingin diubah.
- Mengapa perubahan dibutuhkan.
- Bukti atau hasil evaluasi.
- Manfaat yang diharapkan.
- Risiko.
- Estimasi biaya.
- Cara membatalkan perubahan.

Pengguna harus dapat menerima atau menolak proposal.

Persetujuan harus terikat pada Proposal ID dan versi proposal. Jika proposal berubah secara material, persetujuan lama tidak berlaku.

8.3 No Approval, No Permanent Change

Jika pengguna belum memberikan persetujuan:

- Proposal tetap menunggu.
- Perubahan tidak diterapkan.
- Sistem tidak boleh menganggap diam sebagai persetujuan.
- Sistem boleh melanjutkan riset lain yang tidak bergantung pada perubahan tersebut.

8.4 Sensitive Changes

Perubahan pada keamanan, autentikasi, otorisasi, pengelolaan rahasia, akses data, dan kebijakan keselamatan memerlukan pemeriksaan lebih ketat.

ALS tidak boleh menonaktifkan kontrol keamanan, memperluas hak akses, atau mengubah mekanisme persetujuan secara mandiri.

---

9. Controlled Implementation

Setelah proposal disetujui, sistem harus menerapkan perubahan melalui proses terkontrol.

Urutannya:

1. Verifikasi persetujuan.
2. Verifikasi versi proposal.
3. Membuat snapshot kondisi sebelum perubahan.
4. Memastikan backup tersedia jika diperlukan.
5. Menjalankan perubahan pada lingkungan yang sesuai.
6. Menjalankan automated tests.
7. Menjalankan benchmark terkait.
8. Membandingkan hasil sebelum dan sesudah.
9. Memeriksa dampak samping.
10. Menentukan apakah perubahan dapat diterima.
11. Menyimpan audit log.

Sistem tidak boleh langsung mengubah produksi hanya karena implementasi berhasil dijalankan tanpa error.

Perubahan kode harus melalui prosedur pengembangan, review, pengujian, dan deployment yang ditetapkan dalam governance proyek.

---

10. Rollback and Recovery

Setiap perubahan permanen harus memiliki rencana pemulihan.

Rollback diperlukan ketika:

- Automated tests gagal.
- Benchmark menunjukkan regresi yang melewati batas toleransi.
- Muncul kerusakan data.
- Keamanan sistem menurun.
- Biaya operasional meningkat secara tidak wajar.
- Hasil perubahan tidak sesuai kriteria keberhasilan.
- Sistem menjadi tidak stabil.

10.1 Rollback Procedure

1. Hentikan proses perubahan.
2. Catat kegagalan dan bukti terkait.
3. Kembalikan konfigurasi atau versi sebelumnya.
4. Pulihkan data dari backup apabila diperlukan.
5. Jalankan kembali pengujian.
6. Pastikan sistem kembali ke kondisi stabil.
7. Buat laporan insiden.
8. Tandai proposal sebagai Rolled Back atau Failed.

Rollback tidak boleh menghapus audit log atau menyembunyikan kegagalan.

10.2 Recovery Principle

Prioritas pemulihan:

1. Keamanan.
2. Integritas data.
3. Ketersediaan layanan.
4. Konsistensi pengetahuan.
5. Kinerja dan efisiensi.

---

11. Learning Job Management

Pembelajaran dapat berlangsung lama dan melibatkan banyak permintaan API.

Karena itu, ALS harus menggunakan sistem job management yang mendukung:

- Job queue.
- Background workers.
- Task status.
- Checkpointing.
- Retry dengan batas maksimal.
- Exponential backoff.
- Timeout.
- Rate limit handling.
- Cost tracking.
- Cancellation.
- Resume after failure.

11.1 Job Status

Status job minimal:

- Pending.
- Queued.
- Running.
- Paused.
- Waiting for Retry.
- Completed.
- Failed.
- Cancelled.

Status job harus dapat diperiksa pengguna.

11.2 Checkpointing

Pekerjaan yang panjang harus dibagi menjadi beberapa tahap.

Setiap tahap harus menyimpan hasil sementara agar pekerjaan dapat dilanjutkan setelah gangguan.

Sistem tidak boleh mengulang seluruh proses dari awal jika checkpoint yang valid tersedia.

11.3 Retry Policy

Retry harus memiliki batas maksimal.

Sistem harus membedakan:

- Temporary failure.
- Rate limit.
- Provider outage.
- Invalid request.
- Authentication failure.
- Data validation failure.

Kesalahan permanen tidak boleh terus diulang sampai menghabiskan biaya API.

11.4 Resource Budget

Setiap job harus memiliki batas:

- Maximum API calls.
- Maximum token usage.
- Maximum estimated cost.
- Maximum execution time.
- Maximum retries.

Jika batas tercapai, job harus dihentikan atau menunggu persetujuan tambahan sesuai kebijakan.

---

12. Model Strategy and Model Evolution

ALS dapat menggunakan beberapa model untuk tugas yang berbeda.

Contoh peran:

- Research Model: riset dan sintesis informasi.
- Reasoning Model: analisis dan pemecahan masalah.
- Evaluation Model: evaluasi hasil.
- Lightweight Model: klasifikasi, ekstraksi, dan tugas sederhana.

Pemilihan model tidak boleh hanya berdasarkan reputasi atau ukuran model.

Sistem harus membandingkan kualitas hasil, latensi, biaya, dan reliabilitas.

12.1 Model Independence

ALS tidak boleh mengasumsikan bahwa semua model memiliki kemampuan atau keterbatasan yang sama.

Setiap model harus melalui evaluasi sesuai tugas yang akan diberikan.

12.2 Model Knowledge versus Model Weights

ALS harus membedakan tiga bentuk peningkatan:

1. External Knowledge: pengetahuan melalui database dan retrieval.
2. System Capability: peningkatan melalui workflow, tools, prompt, dan konfigurasi.
3. Model Weight Evolution: perubahan parameter model melalui fine-tuning atau pelatihan.

Menyimpan pengetahuan ke database tidak berarti bobot model berubah.

Fine-tuning atau training hanya boleh dilakukan melalui pipeline terpisah, dengan dataset, validasi, benchmark, persetujuan, dan mekanisme rollback yang jelas.

ALS tidak boleh mengklaim bahwa sistem telah melatih atau meningkatkan bobot model ketika yang dilakukan hanya memperbarui database atau prompt.

---

13. Daily Learning Workflow

Siklus harian dirancang untuk memberikan ritme pembelajaran yang konsisten tanpa memaksa semua pekerjaan selesai dalam satu sesi.

13.1 Morning Briefing

Target waktu: sekitar pukul 07.00 WIB.

Jika pengguna belum memberikan arahan harian, Cognis mengirim pesan untuk meminta brief.

Brief dapat berisi:

- Topik pembelajaran.
- Pertanyaan yang ingin dijawab.
- Peristiwa yang perlu diteliti.
- Kompetensi yang ingin dikembangkan.
- Tugas khusus.

Jika tidak ada brief, sistem tidak boleh mengarang prioritas pribadi pengguna. Sistem dapat menunggu arahan atau menjalankan agenda pembelajaran rutin yang sebelumnya telah disetujui.

13.2 Learning Session

Setelah brief diterima, sistem:

1. Membuat learning job.
2. Menentukan kompetensi terkait.
3. Menyusun rencana.
4. Menjalankan riset.
5. Memvalidasi sumber.
6. Menyusun pengetahuan.
7. Melakukan evaluasi.
8. Menyusun laporan.

Pekerjaan dapat dibagi menjadi beberapa job jika terlalu besar.

13.3 Evening Report

Target waktu: sekitar pukul 18.00 WIB.

Cognis mengirim laporan pembelajaran yang berisi:

- Topik yang dipelajari.
- Tujuan pembelajaran.
- Ringkasan temuan.
- Sumber utama.
- Bukti penting.
- Analisis.
- Hal yang belum diketahui.
- Kompetensi yang dilatih.
- Hasil evaluasi.
- Kelemahan yang ditemukan.
- Usulan pembelajaran berikutnya.
- Proposal perubahan jika diperlukan.

13.4 User Review

Pengguna dapat memeriksa laporan pada malam hari atau hari berikutnya.

Sistem harus dapat mempertahankan status laporan dan proposal yang menunggu tinjauan.

Laporan yang belum disetujui tidak boleh otomatis dianggap sebagai izin untuk perubahan permanen.

---

14. Security and Research Integrity

Semua data eksternal harus diperlakukan sebagai informasi yang belum dipercaya.

Dokumen, halaman web, kode, hasil pencarian, dan file yang dibaca tidak boleh dianggap sebagai instruksi yang berwenang mengubah aturan sistem.

ALS harus melindungi diri dari:

- Prompt injection.
- Manipulasi sumber.
- Data poisoning.
- Referensi palsu.
- Kutipan yang tidak sesuai.
- Kebocoran data pribadi.
- Akses tidak sah.
- Perubahan konfigurasi tanpa izin.

Instruksi sistem dan kebijakan governance memiliki prioritas lebih tinggi daripada instruksi yang ditemukan dalam sumber eksternal.

Sistem harus mencatat asal data dan menjaga keterlacakan sumber.

---

15. Observability and Audit Trail

Setiap siklus pembelajaran harus menghasilkan catatan operasional.

Informasi minimal:

- Learning Job ID.
- Pengguna pemilik job.
- Tujuan pembelajaran.
- Tahapan yang telah selesai.
- Model yang digunakan.
- Sumber yang diakses.
- Estimasi dan biaya aktual.
- Token usage jika tersedia.
- Hasil evaluasi.
- Proposal yang dihasilkan.
- Riwayat persetujuan.
- Perubahan yang diterapkan.
- Hasil pengujian.
- Status akhir.

Audit log harus dapat membedakan tindakan otomatis dan tindakan yang disetujui pengguna.

Data sensitif tidak boleh dicatat secara berlebihan.

---

16. Failure Handling

ALS harus tetap dapat mengelola pekerjaan ketika sebagian komponen gagal.

Contoh:

Kondisi| Tindakan
API provider gagal| Retry terbatas atau ganti provider sesuai kebijakan
Rate limit| Exponential backoff
Sumber tidak tersedia| Tandai sumber gagal dan cari alternatif
Data saling bertentangan| Catat konflik dan turunkan tingkat keyakinan
Evaluasi gagal| Jangan klaim peningkatan
Biaya melebihi batas| Pause atau hentikan job
Persetujuan belum diberikan| Tahan perubahan permanen
Implementasi gagal| Jalankan rollback
Worker berhenti| Lanjutkan dari checkpoint jika valid

Kegagalan harus menghasilkan status yang jelas, bukan diam-diam dianggap berhasil.

---

17. Key Performance Indicators

Kinerja ALS dievaluasi melalui beberapa kelompok metrik.

17.1 Learning Quality

- Accuracy.
- Evidence quality.
- Source reliability.
- Reasoning quality.
- Citation correctness.
- Knowledge consistency.

17.2 Competency Development

- Baseline score.
- Post-learning score.
- Holdout performance.
- Regression rate.
- Competency mastery progress.

17.3 Operational Efficiency

- Cost per learning job.
- Average completion time.
- API failure rate.
- Retry rate.
- Job recovery rate.
- Token efficiency.

17.4 Governance Quality

- Approval compliance.
- Unauthorized change count.
- Rollback success rate.
- Audit completeness.
- Proposal acceptance and rejection rate.

Target angka KPI ditetapkan setelah baseline sistem tersedia. Sistem tidak boleh membuat target keberhasilan palsu tanpa data awal yang memadai.

---

18. Minimum Acceptance Criteria

Implementasi awal ALS dianggap memenuhi fondasi spesifikasi ketika:

1. Pengguna dapat memberikan tujuan pembelajaran.
2. Sistem dapat memetakan tujuan ke kompetensi.
3. Sistem dapat membuat rencana pembelajaran.
4. Sistem dapat menjalankan learning job secara bertahap.
5. Sistem dapat menyimpan checkpoint.
6. Sistem dapat mengumpulkan dan mencatat sumber.
7. Sistem dapat membedakan fakta, asumsi, interpretasi, dan prediksi.
8. Sistem dapat menghasilkan Candidate Knowledge.
9. Sistem dapat melakukan evaluasi sebelum dan sesudah pembelajaran.
10. Sistem dapat membuat laporan dalam Bahasa Indonesia.
11. Sistem dapat mengidentifikasi kelemahan.
12. Sistem dapat menghasilkan Improvement Proposal.
13. Sistem dapat meminta persetujuan pengguna.
14. Sistem tidak menerapkan perubahan permanen tanpa persetujuan.
15. Sistem dapat menguji perubahan yang telah disetujui.
16. Sistem dapat melakukan rollback.
17. Sistem memiliki audit trail.
18. Sistem memiliki batas penggunaan API dan biaya.

Kriteria ini menjadi dasar pengujian sebelum ALS diperluas.

---

19. Implementation Phases

Phase 1: Learning Foundation

Fokus:

- Learning job management.
- Research workflow.
- Source tracking.
- Knowledge structuring.
- Candidate Knowledge.
- Learning report.

Belum melakukan perubahan otomatis pada sistem produksi.

Phase 2: Competency and Evaluation

Fokus:

- Competency mapping.
- Baseline evaluation.
- Benchmark execution.
- Holdout evaluation.
- Regression detection.
- Competency progress tracking.

Phase 3: Autonomous Improvement Proposal

Fokus:

- Weakness analysis.
- Root cause analysis.
- Improvement Proposal Engine.
- Approval workflow.
- Proposal history.

Phase 4: Controlled System Evolution

Fokus:

- Approved implementation.
- Versioning.
- Automated testing.
- Benchmark comparison.
- Rollback.
- Audit trail.

Phase 5: Model Evolution

Fokus:

- Dataset preparation.
- Dataset quality evaluation.
- Fine-tuning experiments.
- Model benchmarking.
- Model versioning.
- Deployment approval.
- Model rollback.

Tahap ini hanya dijalankan setelah fondasi pembelajaran, evaluasi, dan governance dapat diandalkan.

---

20. Open Design Decisions

Hal berikut masih harus dievaluasi sebelum implementasi:

1. Format standar knowledge record.
2. Pemilihan database dan strategi retrieval.
3. Teknologi job queue.
4. Strategi versioning knowledge.
5. Format benchmark dan scoring rubric.
6. Strategi evaluasi lintas model.
7. Batas biaya per job dan per hari.
8. Mekanisme approval melalui Telegram.
9. Strategi backup dan rollback.
10. Integrasi dataset untuk eksperimen fine-tuning.

Keputusan teknis harus dicatat dalam Architecture Decision Record (ADR) ketika sudah ditetapkan.

---

21. Final Design Principle

ALS dirancang untuk membuat Cognis semakin mampu melalui proses pembelajaran yang dapat diperiksa, diukur, dan dikendalikan.

Sistem harus mampu belajar secara mandiri, tetapi tidak boleh menganggap dirinya selalu benar.

Sistem harus mampu mengidentifikasi kelemahannya, tetapi tidak boleh mengubah aturan dan fondasi produksinya secara sepihak.

Sistem harus mampu mengusulkan evolusi, tetapi setiap perubahan permanen harus memiliki bukti, pengujian, persetujuan, dan mekanisme pemulihan.

Prinsip utamanya: Learn autonomously, evaluate objectively, evolve with approval.