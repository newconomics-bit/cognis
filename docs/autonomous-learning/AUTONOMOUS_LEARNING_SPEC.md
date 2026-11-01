AUTONOMOUS LEARNING SPECIFICATION

COGNIS

Document Version: 1.0
Product Version: MVP v1
Status: Proposed Specification Baseline
Document Owner: Founder
System: Autonomous Learning System (ALS)
Primary Language: Indonesian
Primary Timezone: Asia/Jakarta

---

1. Purpose

Dokumen ini mendefinisikan mekanisme pembelajaran Cognis sebagai Autonomous Learning System (ALS).

Tujuannya adalah memastikan bahwa Cognis tidak hanya menjalankan penelitian dan mengumpulkan informasi, tetapi juga mampu mengubah hasil penelitian menjadi pengetahuan terstruktur yang memiliki sumber, bukti, konteks, dan riwayat.

Dokumen ini mengatur:

1. Definisi pembelajaran dalam sistem Cognis.
2. Alur pembelajaran otomatis.
3. Penentuan topik dan tujuan pembelajaran.
4. Pengumpulan serta evaluasi informasi.
5. Pembentukan dan penyimpanan pengetahuan.
6. Pengelolaan riwayat pengetahuan.
7. Evaluasi kualitas pembelajaran.
8. Batas otonomi sistem.
9. Arah pengembangan ALS menuju peningkatan kemampuan yang terukur.

Implementasi MVP harus mengikuti batas produk pada "PRD.md" dan arsitektur pada "SYSTEM_ARCHITECTURE.md".

---

2. ALS Vision

Cognis dirancang untuk menjadi sistem AI khusus yang terus memperluas dan meningkatkan kemampuan analisisnya dalam bidang:

- Economics.
- Business.
- Geopolitics.
- Finance.
- Financial Markets.

Cognis harus dapat menjalankan siklus pembelajaran secara sistematis:

Research → Validate → Evaluate → Store → Report → Assess

Dalam pengembangan jangka panjang, sistem diharapkan mampu:

- Mengidentifikasi kesenjangan pengetahuan.
- Menemukan kelemahan dalam hasil analisis.
- Menentukan kebutuhan pembelajaran berikutnya.
- Mengusulkan perbaikan berdasarkan bukti.
- Menguji perubahan kemampuan.
- Mempertahankan perubahan yang terbukti berhasil.
- Membatalkan perubahan yang menghasilkan regresi.

Namun, kemampuan mengubah sistem secara permanen bukan bagian dari MVP v1.

MVP berfokus pada pembuktian proses pengumpulan dan pengelolaan pengetahuan yang dapat dipercaya.

---

3. Definition of Learning

Istilah learning harus digunakan secara tepat agar sistem tidak membuat klaim peningkatan kemampuan yang keliru.

Cognis membedakan empat bentuk pembelajaran.

3.1 Information Acquisition

Proses memperoleh informasi baru melalui penelitian.

Contoh:

- Meneliti kebijakan moneter terbaru.
- Mempelajari perkembangan industri semikonduktor.
- Mengumpulkan informasi tentang pasar energi.
- Membandingkan kebijakan ekonomi beberapa negara.

Hasil:

Informasi dan materi penelitian yang telah dikumpulkan.

3.2 Persistent Knowledge Acquisition

Proses mengubah hasil penelitian menjadi catatan pengetahuan yang terstruktur dan tersimpan secara persisten.

Contoh:

- Menyimpan hubungan antara suku bunga dan biaya pinjaman.
- Menyimpan temuan tentang perubahan kebijakan perdagangan.
- Menyimpan analisis terhadap struktur pasar komoditas.
- Menyimpan perbedaan pandangan beberapa sumber terhadap suatu peristiwa.

Hasil:

Knowledge Records yang memiliki provenance dan dapat ditemukan kembali.

3.3 Capability Improvement

Proses meningkatkan kemampuan sistem dalam menyelesaikan tugas tertentu.

Contoh:

- Meningkatkan ketepatan analisis makroekonomi.
- Meningkatkan kemampuan membedakan korelasi dan kausalitas.
- Mengurangi kesalahan membaca data pasar.
- Meningkatkan kualitas analisis risiko.

Hasil:

Peningkatan performa yang dibuktikan melalui evaluasi dan benchmark yang konsisten.

Capability Improvement belum menjadi proses otomatis pada MVP v1.

3.4 Model Training or Parameter Modification

Proses mengubah parameter model melalui training, fine-tuning, atau metode optimasi lainnya.

Proses ini berbeda dari penyimpanan pengetahuan.

Menambah Knowledge Records tidak berarti parameter model berubah.

Model yang menerima konteks dari knowledge retrieval juga tidak otomatis mengalami training.

Model training atau parameter modification tidak termasuk dalam MVP v1.

3.5 Learning Claims

Cognis harus menggunakan istilah berikut secara konsisten:

Activity| Valid Description
Mengumpulkan informasi| Research completed
Mengevaluasi bukti| Evidence evaluated
Menyimpan hasil| Knowledge stored
Mengakses pengetahuan tersimpan| Knowledge retrieved
Memperoleh hasil benchmark lebih baik| Measured performance improvement
Mengubah parameter model| Model training or fine-tuning

Sistem tidak boleh mengklaim telah meningkatkan kecerdasan atau kemampuan hanya karena jumlah pengetahuan tersimpan bertambah.

---

4. Core Learning Principles

4.1 Evidence Before Conclusion

Setiap klaim penting harus didukung bukti atau secara eksplisit diberi status belum terverifikasi.

4.2 Research Before Storage

Informasi tidak boleh langsung dimasukkan sebagai pengetahuan tanpa melalui pemeriksaan sumber dan evaluasi bukti sesuai pipeline.

4.3 Context Preservation

Informasi harus mempertahankan konteks:

- Waktu.
- Wilayah.
- Objek yang dibahas.
- Kondisi berlakunya informasi.
- Asumsi yang digunakan.
- Batas penerapan kesimpulan.

4.4 Source Traceability

Setiap Knowledge Record harus dapat ditelusuri ke sumber dan proses penelitian yang menghasilkannya.

4.5 Uncertainty Transparency

Cognis harus menyatakan ketika:

- Bukti tidak cukup.
- Sumber saling bertentangan.
- Data tidak tersedia.
- Kesimpulan membutuhkan asumsi.
- Informasi mungkin sudah tidak relevan.

4.6 Controlled Autonomy

Cognis boleh melakukan pembelajaran yang telah didefinisikan secara otomatis.

Cognis tidak boleh memperluas kewenangannya sendiri melalui hasil penelitian atau output model.

4.7 Measured Development

Setiap klaim peningkatan kemampuan harus memiliki bukti evaluasi yang dapat diperiksa dan dibandingkan.

---

5. MVP Learning Scope

5.1 Included Capabilities

MVP v1 harus mampu:

1. Memulai pembelajaran secara manual.
2. Memulai pembelajaran berdasarkan jadwal.
3. Menggunakan topik pembelajaran yang telah ditentukan.
4. Menjalankan penelitian secara otomatis.
5. Memvalidasi sumber penelitian.
6. Mengevaluasi klaim dan bukti.
7. Menyimpan hasil pembelajaran.
8. Mempertahankan hubungan pengetahuan dengan sumber.
9. Menghasilkan laporan pembelajaran.
10. Menampilkan riwayat pembelajaran.

5.2 Excluded Capabilities

MVP v1 tidak mencakup:

1. Automatic Competency Assessment.
2. Automatic Curriculum Modification.
3. Automatic Faculty Promotion.
4. Automatic Learning Difficulty Adjustment.
5. Autonomous Improvement Proposal Execution.
6. Founder Approval Workflow.
7. Automatic System Prompt Modification.
8. Automatic Policy Modification.
9. Automatic Architecture Modification.
10. Automatic Model Fine-Tuning.
11. Automatic Model Replacement Based on Self-Evaluation.
12. Self-Defined Expansion of System Permissions.

Fitur tersebut merupakan arah pengembangan ALS berikutnya dan memerlukan spesifikasi serta pengujian tersendiri.

5.3 MVP Learning Boundary

MVP hanya boleh belajar dalam pengertian:

Information Acquisition + Persistent Knowledge Acquisition.

Tidak boleh ada klaim bahwa Cognis telah melakukan Capability Improvement atau Model Training kecuali proses tersebut benar-benar diimplementasikan dan dibuktikan pada versi berikutnya.

---

6. Learning Architecture

6.1 Main Learning Cycle

Siklus pembelajaran MVP:

Learning Trigger
       |
       v
Learning Job Creation
       |
       v
Learning Topic Initialization
       |
       v
Research Planning
       |
       v
Research Execution
       |
       v
Source Validation
       |
       v
Evidence Evaluation
       |
       v
Knowledge Synthesis
       |
       v
Knowledge Storage
       |
       v
Learning Report
       |
       v
Learning Cycle Completed

Tahap Knowledge Synthesis merupakan aktivitas pengolahan hasil evaluasi sebelum penyimpanan. Tahap ini berada dalam tanggung jawab pipeline dan tidak menambahkan klaim tanpa dasar.

Alur tersebut mengikuti enam tahap utama yang ditetapkan dalam PRD dan Architecture.

6.2 Learning Cycle Identity

Setiap siklus pembelajaran harus memiliki:

- Learning Cycle ID.
- Job ID.
- Domain.
- Topic.
- Learning Objective.
- Trigger Type.
- Scheduled Time jika tersedia.
- Actual Start Time.
- Completion Time.
- Configuration Reference.
- Final Status.

Satu Learning Cycle menghasilkan satu Job atau memiliki hubungan yang eksplisit dengan Job yang menjalankannya.

6.3 Learning Cycle Isolation

Setiap siklus harus memiliki konteks dan identitas yang jelas.

Hasil penelitian dari satu job tidak boleh secara tidak sengaja dicampur dengan hasil job lain.

Penggabungan informasi dari beberapa siklus hanya diperbolehkan melalui mekanisme sintesis atau relasi pengetahuan yang eksplisit.

---

7. Learning Topic Management

7.1 Topic Sources

MVP mendukung dua sumber topik:

Manual Topic

Topik dimasukkan secara langsung oleh Founder atau operator.

Scheduled Topic

Topik diperoleh dari jadwal pembelajaran yang telah dikonfigurasi sebelumnya.

7.2 Topic Definition

Setiap topik pembelajaran idealnya memiliki:

- Topic ID.
- Topic Name.
- Domain.
- Description.
- Learning Objective.
- Scope.
- Temporal Context.
- Research Constraints.
- Expected Output.

Tidak semua field harus wajib untuk setiap topik, tetapi sistem harus memiliki validasi yang memadai agar penelitian tidak berjalan dengan konteks yang ambigu.

7.3 Topic Boundaries

Topik harus memiliki batas penelitian yang cukup jelas.

Contoh topik yang terlalu luas:

"Pelajari ekonomi dunia."

Contoh topik yang lebih operasional:

"Analisis hubungan perubahan suku bunga The Federal Reserve dengan arus modal ke negara berkembang selama periode tertentu."

Research planning boleh memecah topik menjadi beberapa pertanyaan penelitian yang lebih kecil selama tetap berada dalam ruang lingkup tujuan awal.

7.4 Topic Expansion

Pada MVP, sistem tidak boleh mengubah tujuan utama pembelajaran secara otomatis.

Sistem boleh menemukan pertanyaan turunan yang relevan untuk membantu penelitian, tetapi pertanyaan tersebut harus tetap terhubung dengan tujuan pembelajaran awal.

Perluasan kurikulum secara permanen berada di luar ruang lingkup MVP.

---

8. Research Planning

8.1 Purpose

Research Planning mengubah topik pembelajaran menjadi rencana penelitian yang dapat dijalankan.

8.2 Planning Requirements

Sistem harus dapat mengidentifikasi:

- Tujuan penelitian.
- Pertanyaan utama.
- Sub-questions jika diperlukan.
- Jenis informasi yang diperlukan.
- Konteks waktu.
- Batas wilayah atau objek.
- Kebutuhan sumber primer.
- Kebutuhan perbandingan sumber.
- Batas penggunaan resource.

8.3 Research Plan Output

Output minimum:

- Research Plan ID.
- Learning Cycle ID.
- Primary Question.
- Supporting Questions.
- Research Scope.
- Time Context.
- Retrieval Strategy.
- Expected Evidence Types.

8.4 Planning Constraints

Research planning tidak boleh:

- Mengubah domain utama secara sepihak.
- Menghapus tujuan pembelajaran.
- Memperluas ruang lingkup tanpa batas.
- Menjadikan asumsi model sebagai fakta.
- Menganggap sumber tertentu valid sebelum diperiksa.

Rencana penelitian dapat disesuaikan selama proses apabila ditemukan kendala, tetapi perubahan harus tercatat.

---

9. Research Execution

9.1 Research Objectives

Research bertujuan memperoleh informasi relevan yang cukup untuk menjawab pertanyaan penelitian.

Keberhasilan tidak ditentukan oleh jumlah artikel yang dikumpulkan.

9.2 Research Source Priority

Urutan prioritas sumber secara umum:

1. Dokumen primer dan publikasi resmi.
2. Data dan laporan lembaga yang kredibel.
3. Penelitian akademik dan publikasi ilmiah.
4. Laporan industri dengan metodologi yang jelas.
5. Media berita yang memiliki standar editorial.
6. Analisis atau opini pakar.
7. Sumber lain yang relevan tetapi memiliki keterbatasan.

Urutan tersebut bukan aturan mutlak.

Jenis sumber yang paling tepat bergantung pada topik dan jenis klaim yang diteliti.

Contoh:

- Untuk kebijakan moneter, dokumen bank sentral menjadi sumber utama.
- Untuk laporan keuangan, laporan resmi perusahaan menjadi sumber primer.
- Untuk data perdagangan, statistik resmi lebih relevan daripada opini media.
- Untuk analisis sentimen, sumber komunitas dapat menjadi data observasi tetapi tidak otomatis mewakili seluruh populasi.

9.3 Research Diversity

Untuk klaim penting, sistem harus mengupayakan pemeriksaan dari lebih dari satu sumber independen apabila sumber pembanding tersedia.

Dua artikel yang mengutip satu laporan yang sama tidak otomatis dihitung sebagai dua bukti independen.

9.4 Research Completion

Penelitian dapat dinyatakan selesai apabila:

- Pertanyaan utama telah ditangani.
- Materi relevan telah dikumpulkan atau ketidaktersediaannya dicatat.
- Sumber telah memiliki identitas.
- Keterbatasan retrieval telah dicatat.
- Hasil penelitian siap diteruskan ke validasi sumber.

Research completion tidak berarti pertanyaan penelitian pasti telah terjawab.

---

10. Source Validation

10.1 Validation Dimensions

Setiap sumber dievaluasi berdasarkan dimensi berikut:

Authority

Kredibilitas penerbit, organisasi, penulis, atau institusi.

Relevance

Keterkaitan isi sumber dengan pertanyaan penelitian.

Recency

Kesesuaian waktu publikasi atau pembaruan dengan karakter informasi.

Transparency

Kejelasan data, metode, referensi, dan kepentingan yang mungkin memengaruhi isi.

Accessibility

Kemampuan sistem memeriksa materi dan metadata yang diperlukan.

10.2 Contextual Validation

Sistem harus mempertimbangkan karakter bidang penelitian.

Informasi ekonomi dan pasar finansial sering memiliki sensitivitas waktu yang tinggi.

Sebaliknya, konsep teori ekonomi tertentu mungkin tetap relevan meskipun sumbernya lebih lama.

Sistem tidak boleh menerapkan satu aturan recency yang sama untuk seluruh jenis pengetahuan.

10.3 Source Limitations

Sistem harus mencatat keterbatasan seperti:

- Tidak tersedia tanggal publikasi.
- Penulis tidak diketahui.
- Metodologi tidak dijelaskan.
- Data tidak dapat diperiksa.
- Sumber merupakan opini.
- Informasi telah diperbarui.
- Konten hanya tersedia sebagian.
- Sumber tidak dapat diakses.

10.4 Validation Output

Setiap sumber harus memiliki:

- Validation Result.
- Validation Dimensions.
- Limitations.
- Validation Reason.
- Validation Timestamp.

Hasil validasi harus membedakan antara sumber yang dapat digunakan, sumber yang perlu pembatasan, dan sumber yang tidak layak menjadi dasar kesimpulan.

10.5 No Fabricated Validation

Metadata yang tidak tersedia harus ditandai tidak tersedia.

Sistem tidak boleh mengisi kekosongan metadata menggunakan tebakan model.

---

11. Evidence Evaluation

11.1 Claim Identification

Sistem harus mengidentifikasi klaim penting yang ditemukan dalam sumber.

Klaim harus memiliki konteks yang cukup agar tidak kehilangan makna ketika dipisahkan dari dokumen asal.

11.2 Claim Classification

Klaim minimal dapat dikategorikan sebagai:

- Descriptive Claim.
- Quantitative Claim.
- Causal Claim.
- Comparative Claim.
- Predictive Claim.
- Interpretive Claim.
- Normative Claim.

Klasifikasi menentukan cara evaluasi yang sesuai.

Sebagai contoh:

Klaim kausal membutuhkan dasar yang lebih kuat daripada sekadar dua variabel bergerak bersamaan.

Prediksi harus menyertakan asumsi dan kondisi yang dapat memengaruhi hasil.

11.3 Evidence Assessment Dimensions

Bukti dievaluasi berdasarkan:

Directness

Seberapa langsung bukti mendukung klaim.

Source Quality

Kualitas dan keterbatasan sumber asal.

Independence

Apakah bukti berasal dari sumber yang independen atau hanya mengulang sumber yang sama.

Consistency

Apakah bukti sejalan dengan bukti lain yang tersedia.

Recency

Apakah bukti masih sesuai dengan konteks waktu penelitian.

Methodological Strength

Apakah metode pengumpulan dan analisis data memadai untuk jenis klaim.

Contradiction

Apakah terdapat bukti yang bertentangan.

11.4 Evidence Strength Classification

MVP menggunakan klasifikasi kualitatif:

Classification| Meaning
Strong Support| Bukti relevan dan cukup kuat mendukung klaim
Moderate Support| Bukti mendukung klaim tetapi memiliki keterbatasan
Weak Support| Dukungan bukti terbatas atau tidak langsung
Insufficient Evidence| Bukti belum cukup untuk menilai klaim
Conflicting Evidence| Terdapat bukti penting yang bertentangan

Klasifikasi tersebut bukan probabilitas statistik dan tidak boleh disajikan sebagai persentase keyakinan tanpa metode kuantitatif yang tervalidasi.

11.5 Contradictory Evidence

Ketika sumber berbeda menghasilkan kesimpulan yang bertentangan, Cognis harus:

1. Mengidentifikasi klaim yang berbeda.
2. Mengidentifikasi sumber terkait.
3. Membandingkan waktu data.
4. Membandingkan metode penelitian.
5. Membandingkan konteks dan asumsi.
6. Menjelaskan kemungkinan penyebab perbedaan.
7. Menyatakan apabila konflik belum dapat diselesaikan.

Sistem tidak boleh memilih satu kesimpulan hanya karena lebih mudah diringkas.

11.6 Uncertainty Recording

Setiap evaluasi penting harus dapat mencatat:

- Missing Data.
- Conflicting Information.
- Unverified Assumptions.
- Methodological Limitations.
- Temporal Limitations.
- Alternative Explanations.

11.7 Evaluation Output

Output minimum:

- Claim ID.
- Claim Statement.
- Claim Type.
- Supporting Evidence.
- Contradicting Evidence.
- Evidence Strength.
- Assessment Reason.
- Uncertainty.
- Limitations.
- Evaluation Timestamp.

---

12. Knowledge Synthesis

12.1 Purpose

Knowledge Synthesis menyusun hasil penelitian dan evaluasi menjadi bentuk pengetahuan yang koheren.

Sintesis harus mempertahankan perbedaan antara:

- Fakta yang didukung bukti.
- Interpretasi.
- Hubungan antar-konsep.
- Hipotesis.
- Prediksi.
- Kesimpulan sementara.

12.2 Synthesis Requirements

Sistem harus:

- Menggabungkan informasi relevan tanpa menghilangkan sumber.
- Mengidentifikasi temuan yang konsisten.
- Menandai pertentangan.
- Mengidentifikasi hubungan antar-klaim.
- Mempertahankan konteks waktu.
- Menyatakan asumsi.
- Menyatakan batas penerapan pengetahuan.

12.3 Knowledge Granularity

Knowledge Record sebaiknya menyimpan satu unit pengetahuan yang dapat dipahami dan ditelusuri.

Hindari dua ekstrem:

- Menyimpan seluruh artikel sebagai satu catatan tanpa struktur.
- Memecah informasi menjadi terlalu banyak potongan kecil hingga kehilangan konteks.

Unit pengetahuan dapat berupa satu konsep, fakta, hubungan, temuan, atau interpretasi yang memiliki konteks yang jelas.

12.4 No Unsupported Synthesis

Sistem tidak boleh menghasilkan hubungan sebab-akibat atau pola baru hanya karena beberapa informasi muncul dalam penelitian yang sama.

Setiap hubungan yang disimpulkan harus memiliki dasar dan diberi label sesuai kekuatan dukungannya.

---

13. Knowledge Storage

13.1 Knowledge Record Requirements

Setiap Knowledge Record minimal mencakup:

- Knowledge ID.
- Learning Cycle ID.
- Domain.
- Topic.
- Knowledge Type.
- Content.
- Related Claims.
- Related Evidence.
- Source References.
- Temporal Context.
- Evidence Assessment Reference.
- Created At.
- Updated At.
- Record Version.
- Storage State.

13.2 Knowledge Types

Knowledge Type dapat mencakup:

- Concept.
- Fact.
- Relationship.
- Finding.
- Interpretation.
- Hypothesis.
- Prediction.

Klasifikasi harus menunjukkan karakter informasi, bukan tingkat kebenarannya.

Sebagai contoh, sebuah Fact tetap memerlukan sumber dan bukti pendukung.

13.3 Storage States

MVP menggunakan empat status penyimpanan:

State| Meaning
Active| Record tersedia dalam basis pengetahuan
Superseded| Record memiliki versi atau informasi lebih baru yang menggantikannya
Archived| Record dipertahankan untuk riwayat tetapi tidak menjadi pilihan utama retrieval
Quarantined| Record dibatasi penggunaannya karena masalah integritas, provenance, atau kualitas data

Status tersebut menjelaskan kondisi penyimpanan, bukan kebenaran informasi.

13.4 Storage State Rules

- Record baru dapat disimpan sebagai Active apabila memenuhi validasi penyimpanan.
- Record yang memiliki masalah integritas dapat ditempatkan dalam Quarantined.
- Informasi yang digantikan oleh versi lebih baru dapat ditandai Superseded.
- Record lama yang tidak lagi diperlukan dalam hasil retrieval utama dapat diarsipkan.
- Perubahan status harus mempertahankan riwayat.
- Record tidak boleh dihapus hanya karena ditemukan informasi yang berbeda.

13.5 Knowledge Quality Separation

Kondisi penyimpanan harus dipisahkan dari kualitas bukti.

Contoh:

Sebuah Knowledge Record dapat berstatus Active dengan klasifikasi evidence Weak Support.

Artinya record tersimpan dan dapat diperiksa, tetapi bukti yang mendukung isinya masih lemah.

Sistem tidak boleh mengartikan Active sebagai Verified Truth.

13.6 Knowledge Retrieval

MVP harus memungkinkan pencarian kembali Knowledge Records melalui identitas, domain, topik, dan metadata yang tersedia.

Jika pengetahuan digunakan sebagai konteks untuk proses AI berikutnya, sistem harus mempertahankan referensi sumber dan status evaluasinya.

Sistem tidak perlu memasukkan seluruh basis pengetahuan ke setiap prompt.

Hanya pengetahuan yang relevan dengan tugas yang seharusnya dipertimbangkan untuk digunakan.

13.7 Duplicate and Conflicting Knowledge

Apabila informasi baru mirip dengan informasi yang sudah tersimpan, sistem harus membandingkan identitas, konteks, waktu, dan sumber sebelum membuat record baru atau menghubungkannya dengan record yang ada.

Kemiripan teks tidak otomatis berarti kedua informasi identik.

Apabila dua Knowledge Records berbeda, sistem harus mempertahankan keduanya jika perbedaannya bermakna.

---

14. Learning Report

14.1 Purpose

Learning Report menjelaskan apa yang dipelajari Cognis melalui satu siklus pembelajaran.

Laporan harus menjadi representasi yang dapat diaudit atas hasil pipeline.

14.2 Required Report Structure

Setiap laporan minimal memuat:

1. Learning Cycle Identity.
2. Topic and Learning Objective.
3. Research Scope.
4. Executive Summary.
5. Key Findings.
6. Source Validation Results.
7. Evidence Assessment.
8. Supporting and Contradicting Evidence.
9. Knowledge Records Created.
10. Uncertainty and Limitations.
11. Conclusions.
12. Unresolved Questions.
13. Model and Configuration Metadata yang relevan.

14.3 Report Language

Bahasa Indonesia menjadi bahasa utama.

Istilah asing dapat digunakan jika lebih akurat, tetapi penjelasan harus tetap mudah dipahami.

14.4 Report Integrity

Laporan harus dihasilkan dari hasil penelitian dan evaluasi yang tersimpan.

Sistem tidak boleh menambahkan sumber, angka, atau klaim yang tidak terdapat dalam data proses tanpa menandainya sebagai informasi tambahan yang belum diverifikasi.

14.5 Report Status

Laporan hanya boleh dinyatakan selesai setelah berhasil disimpan dan dapat diakses kembali.

Kegagalan pembuatan atau penyimpanan laporan harus tercatat sebagai kegagalan tahap pipeline.

---

15. Learning Quality Evaluation

15.1 Purpose

Kualitas pembelajaran harus dievaluasi berdasarkan hasil dan integritas proses.

Keberhasilan tidak boleh dinilai hanya melalui panjang laporan, jumlah sumber, atau penilaian model terhadap output-nya sendiri.

15.2 MVP Evaluation Dimensions

Research Coverage

Apakah pertanyaan penelitian telah ditangani secara memadai?

Source Quality

Apakah sumber yang digunakan sesuai dengan karakter penelitian?

Claim Traceability

Apakah klaim penting dapat ditelusuri ke sumber dan bukti?

Evidence Quality

Apakah kesimpulan memiliki dukungan yang memadai?

Contradiction Handling

Apakah informasi yang bertentangan telah dicatat dan dijelaskan?

Knowledge Integrity

Apakah pengetahuan tersimpan dengan metadata dan provenance yang benar?

Report Quality

Apakah laporan menggambarkan hasil penelitian dengan akurat?

15.3 Human Review

MVP harus memungkinkan Founder atau operator memeriksa laporan dan hasil penelitian.

Pemeriksaan manusia dapat digunakan untuk:

- Menilai ketepatan kesimpulan.
- Mengidentifikasi kesalahan evaluasi.
- Menemukan sumber yang kurang tepat.
- Menilai kegunaan pengetahuan tersimpan.
- Memberikan catatan untuk perbaikan implementasi.

Human review pada MVP tidak menjadi approval workflow untuk perubahan sistem permanen.

15.4 Baseline Establishment

Metrik kualitas yang memerlukan penilaian atau benchmark harus memiliki baseline.

Sistem tidak boleh menggunakan nilai target yang belum diuji seolah-olah sudah terbukti.

Baseline dapat dibangun dari kumpulan tugas evaluasi awal dan hasil pemeriksaan manusia.

15.5 Learning Evaluation Record

Hasil evaluasi harus dapat mencatat:

- Learning Cycle ID.
- Evaluator Type.
- Evaluation Criteria.
- Evaluation Result.
- Findings.
- Identified Weaknesses.
- Evaluation Timestamp.

---

16. Learning Failure Handling

16.1 Failure Categories

Kegagalan pembelajaran dapat dikategorikan sebagai:

Trigger Failure

Gagal membuat atau memulai job.

Research Failure

Gagal memperoleh informasi yang diperlukan.

Source Validation Failure

Gagal memeriksa sumber atau metadata.

Evidence Evaluation Failure

Gagal mengevaluasi klaim dan bukti.

Knowledge Storage Failure

Gagal menyimpan hasil pembelajaran.

Report Generation Failure

Gagal menghasilkan atau menyimpan laporan.

Resource Failure

Batas resource, rate limit, atau biaya tidak memungkinkan proses dilanjutkan.

16.2 Failure Requirements

Setiap kegagalan harus:

- Dicatat.
- Terhubung dengan Job ID.
- Terhubung dengan Stage Run ID jika relevan.
- Memiliki kategori error.
- Menyimpan informasi yang cukup untuk diagnosis.
- Tidak menampilkan secret.
- Mempertahankan data tahap sebelumnya yang telah tersimpan dengan benar.

16.3 Partial Learning Results

Jika pipeline gagal setelah sebagian tahap berhasil, sistem boleh mempertahankan hasil sementara yang valid.

Namun, sistem tidak boleh menyajikan hasil parsial sebagai laporan pembelajaran final yang telah selesai.

16.4 Retry

Retry harus mengikuti kebijakan dari "SYSTEM_ARCHITECTURE.md".

Retry tidak boleh menghasilkan Knowledge Records duplikat yang tidak terkendali.

Setiap attempt harus dapat dibedakan dalam riwayat eksekusi.

---

17. Learning Governance

17.1 Permitted Automatic Actions

Pada MVP, sistem boleh secara otomatis:

- Menjalankan pembelajaran berdasarkan jadwal.
- Menentukan pertanyaan turunan dalam batas topik.
- Mengumpulkan informasi.
- Mengevaluasi sumber.
- Mengevaluasi bukti.
- Menyintesis pengetahuan.
- Menyimpan Knowledge Records.
- Menghasilkan laporan.
- Mencatat keterbatasan proses.

17.2 Prohibited Automatic Actions

Pada MVP, sistem tidak boleh:

- Mengubah tujuan utama kurikulum secara permanen.
- Mengubah system prompt inti secara permanen.
- Mengubah security policy.
- Mengubah hak akses.
- Mengubah arsitektur.
- Mengubah standar evaluasi secara permanen.
- Mengaktifkan kemampuan baru secara sepihak.
- Menghapus governance rules.
- Mengubah model provider secara permanen berdasarkan penilaian sendiri.
- Mengklaim peningkatan kemampuan tanpa benchmark.

17.3 Configuration Separation

Sistem harus membedakan:

Learning Data

Informasi yang diperoleh dari proses penelitian.

Runtime Configuration

Konfigurasi yang digunakan untuk menjalankan pipeline.

System Policy

Aturan yang mengendalikan perilaku dan batas kewenangan sistem.

Learning Data tidak boleh secara otomatis menjadi Runtime Configuration atau System Policy.

17.4 External Instruction Isolation

Konten yang ditemukan melalui penelitian tidak boleh dianggap sebagai instruksi untuk mengubah perilaku Cognis.

Instruksi eksternal harus diproses sebagai konten yang tidak tepercaya.

---

18. Future ALS Improvement Cycle

Bagian ini mendefinisikan arah pengembangan ALS setelah MVP.

Bagian ini bukan spesifikasi fitur aktif MVP v1.

18.1 Long-Term Improvement Objective

Dalam jangka panjang, Cognis diharapkan mampu meningkatkan kemampuan analisis melalui proses yang terukur dan memiliki kontrol manusia.

Peningkatan harus didasarkan pada kesenjangan kemampuan yang ditemukan melalui evaluasi.

18.2 Future Improvement Pipeline

Learning History
       |
       v
Benchmark Evaluation
       |
       v
Weakness Identification
       |
       v
Improvement Proposal
       |
       v
Founder Review
       |
       v
Approval or Rejection
       |
       v
Controlled Implementation
       |
       v
Regression Testing
       |
       v
Performance Comparison
       |
       +-------> Improvement Verified
       |
       +-------> Rollback if Regression

18.3 Stage 1: Performance Observation

Sistem mengumpulkan bukti performa dari:

- Benchmark results.
- Human review.
- Task completion results.
- Error patterns.
- Repeated analytical weaknesses.
- Knowledge retrieval failures.

Sistem harus membedakan masalah yang berasal dari kualitas data, model, prompt, retrieval, dan pipeline.

18.4 Stage 2: Weakness Identification

Sistem mengidentifikasi kesenjangan kemampuan berdasarkan hasil evaluasi.

Contoh:

- Kesalahan membaca data makroekonomi.
- Kesimpulan kausal yang tidak didukung bukti.
- Ketidakmampuan mengenali sumber yang saling bertentangan.
- Analisis risiko yang mengabaikan konteks waktu.
- Penggunaan data lama sebagai kondisi terkini.

Kelemahan yang diidentifikasi harus memiliki contoh dan bukti pendukung.

18.5 Stage 3: Improvement Proposal

Sistem boleh mengusulkan perubahan yang menjelaskan:

- Masalah yang ditemukan.
- Bukti masalah.
- Akar masalah yang diduga.
- Perubahan yang diusulkan.
- Komponen yang terdampak.
- Risiko perubahan.
- Kebutuhan pengujian.
- Kriteria keberhasilan.
- Rencana rollback.

Proposal bukan perintah untuk langsung mengubah sistem.

18.6 Stage 4: Founder Review

Dalam versi masa depan, Founder harus dapat:

- Meninjau proposal.
- Memeriksa bukti.
- Memeriksa dampak perubahan.
- Menyetujui proposal.
- Menolak proposal.
- Meminta revisi.

Persetujuan harus dicatat dan terkait dengan versi proposal yang tepat.

18.7 Stage 5: Controlled Implementation

Perubahan yang disetujui harus:

- Diterapkan dalam lingkungan yang terkendali.
- Memiliki versi.
- Memiliki perubahan yang dapat ditelusuri.
- Memiliki batas scope.
- Memiliki pengujian yang sesuai.
- Tidak mengubah komponen di luar otorisasi.

18.8 Stage 6: Regression Testing

Perubahan harus dibandingkan dengan baseline sebelum diterapkan.

Pengujian minimal mempertimbangkan:

- Functional correctness.
- Evidence quality.
- Analytical consistency.
- Security.
- Reliability.
- Resource usage.
- Regression on existing tasks.

Peningkatan satu metrik tidak boleh dianggap berhasil jika menyebabkan regresi serius pada aspek lain.

18.9 Stage 7: Rollback

Jika perubahan gagal memenuhi kriteria:

- Perubahan harus dapat dibatalkan.
- Versi sebelumnya harus dapat dipulihkan.
- Hasil pengujian harus disimpan.
- Penyebab kegagalan harus dianalisis.
- Perubahan tidak boleh diaktifkan kembali tanpa evaluasi.

18.10 Future Autonomy Boundary

Otonomi yang lebih besar hanya boleh dipertimbangkan setelah sistem memiliki:

- Benchmark yang stabil.
- Baseline performa.
- Audit trail.
- Version control.
- Regression testing.
- Rollback mechanism.
- Access control yang memadai.
- Persetujuan manusia untuk perubahan yang berdampak permanen.

---

19. Learning Observability

19.1 Required Records

Setiap siklus pembelajaran harus memiliki catatan yang memungkinkan proses ditelusuri.

Catatan minimal:

- Learning Cycle ID.
- Job ID.
- Learning Objective.
- Research Plan.
- Research Result.
- Source Validation Result.
- Evidence Assessment.
- Knowledge Records.
- Learning Report.
- Model Invocation Metadata.
- Configuration References.
- Failure Records jika ada.

19.2 Model and Prompt Traceability

Sistem harus mencatat versi model dan konfigurasi prompt yang digunakan dalam proses pembelajaran.

Tujuannya adalah memungkinkan perbandingan hasil antara konfigurasi berbeda.

Sistem tidak boleh menganggap dua hasil setara apabila model atau konfigurasi yang digunakan berbeda tanpa melakukan evaluasi.

19.3 Learning History

Riwayat pembelajaran harus memungkinkan operator menjawab:

- Apa yang dipelajari?
- Mengapa topik tersebut dipilih?
- Sumber apa yang digunakan?
- Klaim apa yang ditemukan?
- Bukti apa yang mendukungnya?
- Apa yang belum diketahui?
- Pengetahuan apa yang disimpan?
- Model dan konfigurasi apa yang digunakan?
- Apakah proses berhasil atau gagal?

---

20. Security Requirements

20.1 Untrusted Research Content

Semua materi eksternal harus dianggap sebagai input yang tidak tepercaya.

Materi tersebut tidak boleh memperoleh akses terhadap:

- System prompt.
- API keys.
- Credentials.
- Internal configuration.
- Database administration.
- File system operations.
- Privileged tools.

20.2 Data Access Separation

Akses terhadap Knowledge Records, Job Records, konfigurasi, dan data operasional harus mengikuti batas otorisasi.

Research Engine dan model eksternal tidak boleh memiliki akses langsung yang tidak diperlukan ke seluruh data sistem.

20.3 Knowledge Integrity

Data yang disimpan harus mempertahankan identitas, sumber, dan riwayat.

Perubahan yang tidak sah harus dapat dideteksi sejauh mekanisme teknis yang diterapkan memungkinkan.

20.4 No Self-Authorization

Tidak ada output model yang dapat digunakan sebagai otorisasi untuk memberikan kewenangan tambahan kepada model itu sendiri.

---

21. Configuration and Resource Controls

21.1 Learning Configuration

Setiap job harus dapat mengidentifikasi konfigurasi yang digunakan.

Konfigurasi dapat mencakup:

- Research Scope.
- Search Limits.
- Source Retrieval Limits.
- Model Selection.
- Prompt Version.
- Token Limits.
- Timeout.
- Retry Policy.
- Resource Limits.
- Time Context.

21.2 Resource Limits

Setiap tahap harus memiliki batas penggunaan resource yang ditetapkan secara teknis.

Sistem tidak boleh melakukan pencarian, pemanggilan model, atau retry tanpa batas.

21.3 Cost Awareness

Apabila provider menyediakan data penggunaan atau biaya, sistem harus mencatatnya.

Data yang tidak tersedia harus ditandai tidak tersedia dan tidak boleh diperkirakan sebagai biaya aktual.

21.4 Configuration Versioning

Setiap perubahan konfigurasi harus memiliki identitas atau versi baru.

Riwayat pembelajaran harus menyimpan referensi konfigurasi yang benar-benar digunakan saat job berjalan.

---

22. MVP Acceptance Criteria

Mekanisme pembelajaran MVP v1 dinyatakan memenuhi spesifikasi apabila:

22.1 Learning Initialization

- Job dapat dimulai secara manual.
- Job dapat dimulai melalui Scheduler.
- Setiap job memiliki topik dan tujuan pembelajaran.
- Setiap job memiliki identitas yang dapat ditelusuri.

22.2 Research

- Sistem mampu mengubah topik menjadi rencana penelitian.
- Sistem mampu melakukan pencarian informasi.
- Sistem menyimpan identitas sumber.
- Sistem mencatat keterbatasan retrieval.

22.3 Source Validation

- Sistem mengevaluasi kelayakan sumber.
- Sistem menyimpan alasan evaluasi.
- Sistem tidak mengarang metadata.
- Sumber lemah dapat dibedakan dari sumber yang layak digunakan.

22.4 Evidence Evaluation

- Klaim utama dapat diidentifikasi.
- Bukti dapat dihubungkan dengan klaim.
- Bukti pendukung dan bertentangan dapat direpresentasikan.
- Ketidakpastian dapat dicatat.
- Kesimpulan mengikuti kekuatan bukti.

22.5 Knowledge Storage

- Knowledge Records disimpan secara persisten.
- Record memiliki provenance.
- Storage State terpisah dari Evidence Assessment.
- Riwayat perubahan dapat ditelusuri.
- Pengetahuan dapat ditemukan kembali.

22.6 Learning Report

- Laporan dihasilkan dari hasil pipeline.
- Laporan memiliki referensi sumber.
- Laporan menampilkan keterbatasan.
- Laporan dapat diakses kembali.
- Laporan tidak menyajikan klaim lemah sebagai fakta pasti.

22.7 Governance

- Sistem tidak mengubah prompt inti secara otomatis.
- Sistem tidak mengubah policy secara otomatis.
- Sistem tidak mengubah kurikulum inti secara permanen.
- Sistem tidak melakukan fine-tuning otomatis.
- Tidak ada self-approval untuk perubahan sistem.

22.8 End-to-End Learning

Satu siklus penuh harus berhasil dijalankan dan diuji:

Learning Trigger → Research → Source Validation → Evidence Evaluation → Knowledge Storage → Learning Report

Semua hubungan data dan provenance harus dapat diperiksa.

---

23. Future Development Roadmap

Phase 1: Reliable Knowledge Acquisition

Fokus:

- Research automation.
- Source validation.
- Evidence evaluation.
- Knowledge storage.
- Learning report.
- Job observability.

Status: MVP v1.

Phase 2: Competency-Based Learning

Potensi kemampuan:

- Competency Registry.
- Curriculum Mapping.
- Learning Objectives.
- Competency Assessment.
- Benchmark Management.
- Learning Progress Tracking.

Phase 3: Learning Gap Analysis

Potensi kemampuan:

- Weakness Detection.
- Performance Analysis.
- Repeated Error Detection.
- Learning Gap Identification.
- Improvement Proposal Generation.

Phase 4: Governed Self-Improvement

Potensi kemampuan:

- Founder Approval.
- Controlled Configuration Changes.
- Prompt Version Management.
- Regression Testing.
- Rollback Management.

Phase 5: Advanced Learning Systems

Potensi kemampuan:

- Specialized Learning Agents.
- Advanced Knowledge Retrieval.
- Model Evaluation and Routing.
- Controlled Fine-Tuning.
- Advanced Benchmark Systems.
- Selective Automation of Approved Improvements.

Roadmap merupakan arah pengembangan, bukan komitmen bahwa seluruh fitur sudah dirancang atau diimplementasikan.

---

24. Final Learning Principle

Cognis tidak boleh mengukur pembelajaran berdasarkan jumlah informasi yang dikumpulkan.

Pembelajaran harus menghasilkan pengetahuan yang:

- Relevan.
- Memiliki konteks.
- Memiliki sumber.
- Didukung bukti.
- Menyatakan keterbatasan.
- Dapat ditemukan kembali.
- Dapat dievaluasi.
- Dapat dikoreksi.

Peningkatan kemampuan harus dibuktikan melalui pengujian, bukan narasi yang dibuat oleh model itu sendiri.

Cognis must distinguish what it has collected, what it has verified, what it understands, and what it can actually do better.

Itulah fondasi ALS yang dapat dipercaya.