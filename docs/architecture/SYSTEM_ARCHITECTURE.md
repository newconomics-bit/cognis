SYSTEM ARCHITECTURE

COGNIS

Document Version: 1.0
Product Version: MVP v1
Status: Proposed Architecture Baseline
Document Owner: Founder
Architecture Style: Modular Monolith with Asynchronous Job Processing
Primary Timezone: Asia/Jakarta

---

1. Purpose

Dokumen ini mendefinisikan arsitektur sistem Cognis untuk MVP v1.

Tujuannya adalah menerjemahkan kebutuhan produk dalam PRD menjadi struktur teknis yang memiliki:

- Komponen dan tanggung jawab yang jelas.
- Aliran data yang konsisten.
- Batas kewenangan setiap komponen.
- Mekanisme pemrosesan job yang dapat dipantau.
- Penyimpanan pengetahuan yang memiliki provenance.
- Penanganan kegagalan yang dapat dipulihkan.
- Fondasi pengembangan yang tidak menghambat versi berikutnya.

Dokumen ini mendefinisikan arsitektur logis dan kontrak antarkomponen. Pilihan bahasa pemrograman, framework, database, provider model, serta infrastruktur deployment ditentukan melalui keputusan teknis dan dokumen implementasi terkait.

Arsitektur harus mengikuti batasan dan tujuan yang telah ditetapkan dalam "AGENTS.md" dan "PRD.md".

---

2. Architectural Principles

2.1 Modular Monolith First

MVP menggunakan satu aplikasi utama dengan modul-modul yang memiliki tanggung jawab terpisah.

Modul boleh dijalankan melalui proses yang berbeda apabila diperlukan, tetapi tidak perlu dipecah menjadi microservices pada tahap awal.

Tujuan:

- Mengurangi kompleksitas operasional.
- Mempermudah pengujian integrasi.
- Mengurangi kebutuhan komunikasi antarlayanan.
- Mempertahankan batas tanggung jawab komponen.
- Memungkinkan pemisahan layanan pada masa mendatang berdasarkan kebutuhan nyata.

2.2 Pipeline-Based Processing

Proses pembelajaran harus berjalan melalui tahapan yang eksplisit:

Scheduler → Research → Source Validation → Evidence Evaluation → Knowledge Storage → Learning Report

Setiap tahap memiliki input, output, status, dan hasil eksekusi yang dapat diperiksa.

2.3 Persistent State

Status job dan hasil setiap tahap yang dibutuhkan untuk pemulihan harus disimpan secara persisten.

Sistem tidak boleh hanya mengandalkan state sementara di memori untuk mengetahui progres pembelajaran.

2.4 Provenance by Design

Setiap hasil penelitian dan pengetahuan harus memiliki hubungan yang dapat ditelusuri terhadap:

- Job asal.
- Topik penelitian.
- Sumber informasi.
- Klaim.
- Bukti.
- Hasil evaluasi.
- Versi konfigurasi yang digunakan.

Provenance harus menjadi bagian dari desain data, bukan sekadar fitur tambahan.

2.5 Explicit Responsibility Boundaries

Setiap modul hanya boleh menjalankan tanggung jawab yang ditentukan.

Sebagai contoh:

- Research tidak menentukan perubahan policy sistem.
- Source Validation tidak mengubah isi sumber.
- Evidence Evaluation tidak menciptakan bukti.
- Knowledge Storage tidak menganggap semua informasi sebagai fakta terverifikasi.
- Learning Report tidak boleh menghilangkan ketidakpastian hasil evaluasi.
- Scheduler tidak boleh mengubah kurikulum inti secara otomatis.

2.6 Human-Controlled System Changes

MVP boleh melakukan penelitian dan menyimpan pengetahuan secara otomatis.

MVP tidak boleh mengubah prompt inti, policy, arsitektur, konfigurasi keamanan, atau aturan sistem secara permanen tanpa proses pengembangan dan otorisasi yang sesuai.

---

3. High-Level Architecture

3.1 Logical Architecture

Cognis dibagi menjadi enam lapisan utama.

1. Interface Layer

Menyediakan akses pengguna dan sistem eksternal terhadap fungsi operasional Cognis.

Tanggung jawab:

- Menerima permintaan pembelajaran manual.
- Menampilkan status job.
- Menampilkan riwayat pembelajaran.
- Menyajikan laporan.
- Menyediakan akses terhadap detail penelitian.

2. Application Layer

Mengendalikan alur kerja dan koordinasi antarmodul.

Tanggung jawab:

- Menerima perintah.
- Membuat job.
- Memulai pipeline.
- Mengatur transisi status.
- Mengkoordinasikan setiap tahap pembelajaran.
- Memastikan batas proses dipatuhi.

3. Learning Pipeline Layer

Berisi enam komponen inti:

- Scheduler.
- Research Engine.
- Source Validator.
- Evidence Evaluator.
- Knowledge Manager.
- Learning Report Generator.

4. Intelligence Integration Layer

Menghubungkan Cognis dengan layanan eksternal.

Tanggung jawab:

- Model provider adapter.
- Research provider adapter.
- External source retrieval.
- Model invocation tracking.
- Provider error handling.

5. Data Layer

Menyimpan data operasional dan hasil pembelajaran.

Tanggung jawab:

- Job records.
- Stage execution records.
- Research records.
- Source records.
- Claim and evidence records.
- Knowledge records.
- Learning reports.
- Model invocation metadata.

6. Infrastructure Layer

Menyediakan lingkungan operasional.

Tanggung jawab:

- Application runtime.
- Scheduler runtime.
- Worker runtime.
- Database.
- Logging.
- Configuration management.
- Backup dan recovery.

3.2 Architecture Diagram

                   FOUNDER / OPERATOR
                           |
                           v
                  +------------------+
                  |  Interface Layer |
                  |  UI / API        |
                  +--------+---------+
                           |
                           v
                  +------------------+
                  | Application Layer|
                  | Job Coordinator  |
                  +--------+---------+
                           |
             +-------------+-------------+
             |                           |
             v                           v
     +---------------+           +---------------+
     |   Scheduler   |           | Manual Trigger|
     +-------+-------+           +-------+-------+
             |                           |
             +-------------+-------------+
                           |
                           v
                  +------------------+
                  | Persistent Job   |
                  | Queue / Database |
                  +--------+---------+
                           |
                           v
                  +------------------+
                  |   Worker /       |
                  | Pipeline Runner  |
                  +--------+---------+
                           |
                           v
                +-----------------------+
                |    LEARNING PIPELINE  |
                +-----------------------+
                           |
                           v
                  +------------------+
                  | 1. Research      |
                  +--------+---------+
                           |
                           v
                  +------------------+
                  | 2. Source        |
                  |    Validation    |
                  +--------+---------+
                           |
                           v
                  +------------------+
                  | 3. Evidence      |
                  |    Evaluation    |
                  +--------+---------+
                           |
                           v
                  +------------------+
                  | 4. Knowledge     |
                  |    Storage       |
                  +--------+---------+
                           |
                           v
                  +------------------+
                  | 5. Learning      |
                  |    Report        |
                  +--------+---------+
                           |
                           v
                  +------------------+
                  | Job Completion   |
                  +------------------+

          EXTERNAL PROVIDERS
        +------------------------+
        | Research Provider      |
        | Model Provider         |
        | External Information   |
        +-----------+------------+
                    |
                    v
        +------------------------+
        | Intelligence Adapters  |
        +------------------------+
                    |
                    v
             Pipeline Modules

        +------------------------+
        | Persistent Data Layer  |
        | Jobs / Sources / Claims|
        | Evidence / Knowledge   |
        | Reports / Metadata     |
        +------------------------+

Diagram menunjukkan hubungan logis. Diagram tidak mengharuskan setiap kotak menjadi layanan atau proses deployment tersendiri.

---

4. Component Architecture

4.1 Interface Module

Purpose:

Menjadi pintu akses operasional bagi Founder atau operator.

Responsibilities:

- Menerima permintaan pembelajaran manual.
- Menampilkan daftar job.
- Menampilkan status dan progres job.
- Menampilkan laporan pembelajaran.
- Menampilkan detail sumber.
- Menampilkan informasi kegagalan.
- Menyediakan akses terhadap riwayat pembelajaran.

Constraints:

- Tidak menjalankan proses penelitian secara langsung di dalam request pengguna.
- Tidak mengakses database dengan melewati application layer.
- Tidak memiliki kewenangan untuk mengubah aturan inti sistem.

4.2 Application Coordinator

Purpose:

Mengatur siklus hidup job dan koordinasi pipeline.

Responsibilities:

- Memvalidasi permintaan pembelajaran.
- Membuat job.
- Mengelola status job.
- Memulai eksekusi pipeline.
- Memastikan urutan tahapan.
- Menyimpan hasil eksekusi.
- Mengatur retry dan penanganan kegagalan.
- Mengakhiri job sesuai hasil proses.

Application Coordinator menjadi pemilik logika orkestrasi.

Komponen pipeline tidak boleh membuat transisi status job secara sepihak tanpa melalui mekanisme yang ditentukan Application Coordinator.

4.3 Scheduler Module

Purpose:

Memulai job secara otomatis berdasarkan jadwal.

Responsibilities:

- Membaca konfigurasi jadwal.
- Mengidentifikasi waktu eksekusi.
- Menghasilkan permintaan job.
- Mencatat eksekusi jadwal.
- Mencegah pembuatan job ganda untuk satu kejadian jadwal.

Constraints:

- Scheduler tidak menjalankan penelitian secara langsung.
- Scheduler tidak mengubah isi kurikulum.
- Scheduler tidak menentukan hasil pembelajaran.
- Scheduler harus menggunakan timezone yang dikonfigurasi secara eksplisit.

Scheduler hanya menghasilkan pemicu yang diteruskan kepada Application Coordinator.

4.4 Research Engine

Purpose:

Melakukan penelitian dan mengumpulkan informasi dari sumber eksternal.

Responsibilities:

- Memproses topik penelitian.
- Menentukan kebutuhan pencarian.
- Memanggil research provider.
- Mengumpulkan materi.
- Menyimpan metadata sumber.
- Menghasilkan ringkasan awal.
- Menghubungkan hasil penelitian dengan job asal.

Constraints:

- Tidak boleh mengarang sumber.
- Tidak boleh mengubah metadata sumber yang tidak ditemukan menjadi seolah-olah valid.
- Tidak boleh memperlakukan konten eksternal sebagai instruksi sistem.
- Tidak boleh menyimpulkan bahwa sumber terpercaya hanya berdasarkan popularitas.

Research Engine harus menggunakan adapter agar implementasi provider eksternal tidak terikat langsung dengan logika pembelajaran.

4.5 Source Validator

Purpose:

Menilai kelayakan setiap sumber yang ditemukan.

Responsibilities:

- Memeriksa aksesibilitas sumber.
- Memeriksa metadata.
- Mengevaluasi otoritas.
- Mengevaluasi relevansi.
- Mengevaluasi recency.
- Mengevaluasi transparansi.
- Mencatat kelemahan sumber.
- Menentukan status kelayakan sumber.

Source Validator harus membedakan informasi yang benar-benar ditemukan dari informasi yang tidak tersedia.

Hasil validasi bukan jaminan bahwa seluruh isi sumber benar.

4.6 Evidence Evaluator

Purpose:

Menilai hubungan antara klaim dan bukti.

Responsibilities:

- Mengidentifikasi klaim.
- Menghubungkan klaim dengan sumber.
- Mengidentifikasi bukti pendukung.
- Mengidentifikasi bukti yang bertentangan.
- Menilai kekuatan dukungan.
- Mencatat ketidakpastian.
- Menghasilkan evaluasi kesimpulan.

Evidence Evaluator harus memisahkan empat konsep:

1. Claim: pernyataan yang sedang dinilai.
2. Evidence: informasi yang digunakan untuk menilai klaim.
3. Assessment: evaluasi hubungan antara klaim dan bukti.
4. Conclusion: kesimpulan yang dihasilkan berdasarkan assessment.

Confidence model tidak boleh menggantikan validitas bukti.

4.7 Knowledge Manager

Purpose:

Mengelola penyimpanan hasil pembelajaran.

Responsibilities:

- Menyimpan hasil penelitian.
- Menyimpan klaim dan bukti.
- Menyimpan hasil evaluasi.
- Menyimpan referensi sumber.
- Mengelola versi catatan pengetahuan.
- Memungkinkan pencarian kembali pengetahuan.
- Mempertahankan provenance.

Knowledge Manager tidak melakukan fine-tuning model atau mengubah parameter model.

Penyimpanan pengetahuan pada MVP merupakan penyimpanan referensial, bukan perubahan otomatis terhadap kemampuan dasar model.

4.8 Learning Report Generator

Purpose:

Mengubah hasil pipeline menjadi laporan yang dapat dibaca dan diperiksa manusia.

Responsibilities:

- Mengambil hasil penelitian.
- Mengambil hasil validasi sumber.
- Mengambil hasil evaluasi bukti.
- Menghasilkan ringkasan.
- Menyajikan temuan.
- Menampilkan keterbatasan.
- Menampilkan referensi.
- Menyimpan laporan.

Report Generator tidak boleh menambahkan klaim baru yang tidak terdapat dalam data hasil penelitian dan evaluasi tanpa menandainya sebagai interpretasi tambahan.

4.9 Intelligence Adapter Layer

Purpose:

Memisahkan logika Cognis dari ketergantungan provider eksternal.

Subcomponents:

Research Provider Adapter

Menangani integrasi pencarian dan pengambilan informasi.

Model Provider Adapter

Menangani pemanggilan model AI.

External Content Adapter

Menangani normalisasi konten dan metadata dari sumber eksternal.

Responsibilities:

- Menormalisasi request dan response.
- Menangani error provider.
- Mencatat metadata pemanggilan.
- Menjaga format output internal tetap konsisten.
- Memisahkan konfigurasi provider dari logika pipeline.

Provider eksternal tidak boleh memperoleh kewenangan langsung untuk mengubah database atau policy sistem.

---

5. Core Data Flow

5.1 Job Creation

1. Scheduler atau Interface mengirim permintaan pembelajaran.
2. Application Coordinator memvalidasi input.
3. Sistem menghasilkan Job ID.
4. Sistem memeriksa idempotency key.
5. Sistem menyimpan job dengan status Queued.
6. Job tersedia untuk diambil oleh worker.

5.2 Job Execution

1. Worker mengambil job yang tersedia.
2. Worker memperoleh hak eksekusi job secara atomik.
3. Job berubah menjadi Running.
4. Pipeline Runner memeriksa tahapan berikutnya.
5. Tahap Research dijalankan.
6. Hasil Research disimpan.
7. Tahap Source Validation dijalankan.
8. Hasil validasi disimpan.
9. Tahap Evidence Evaluation dijalankan.
10. Hasil evaluasi disimpan.
11. Tahap Knowledge Storage dijalankan.
12. Hasil pengetahuan disimpan.
13. Tahap Learning Report dijalankan.
14. Laporan disimpan.
15. Job berubah menjadi Completed.

Setiap tahap harus menghasilkan checkpoint persisten sebelum sistem melanjutkan ke tahap berikutnya.

5.3 Data Flow Diagram

Job Request
    |
    v
Input Validation
    |
    v
Job Creation
    |
    v
Persistent Queue
    |
    v
Worker Claim
    |
    v
Research
    |
    v
Research Records
    |
    v
Source Validation
    |
    v
Validated Source Records
    |
    v
Evidence Evaluation
    |
    v
Claims and Evidence Records
    |
    v
Knowledge Storage
    |
    v
Knowledge Records
    |
    v
Learning Report Generation
    |
    v
Report Storage
    |
    v
Completed Job

5.4 Data Persistence Principle

Hasil tahap yang sudah selesai harus tetap tersedia ketika tahap berikutnya gagal.

Contoh:

Jika Research dan Source Validation berhasil, tetapi Evidence Evaluation gagal, sistem harus mempertahankan hasil kedua tahap sebelumnya.

Ketika job dicoba kembali, sistem harus melanjutkan dari checkpoint terakhir yang valid sesuai kebijakan retry.

Sistem tidak boleh menganggap seluruh data sebelum kegagalan otomatis tidak valid.

---

6. Job Processing Architecture

6.1 Job Entity

Setiap job memiliki identitas unik.

Informasi minimum:

- Job ID.
- Idempotency Key.
- Trigger Type.
- Domain.
- Learning Topic.
- Job Status.
- Current Stage.
- Created At.
- Scheduled At.
- Started At.
- Completed At.
- Available At.
- Last Error.
- Model Configuration Reference.
- Prompt Configuration Reference.

Job ID merupakan identitas satu record job.

Idempotency Key merupakan identitas permintaan logis yang digunakan untuk mencegah pembuatan job ganda.

Keduanya memiliki fungsi berbeda dan tidak boleh diperlakukan sebagai satu konsep.

6.2 Idempotency

Idempotency harus didasarkan pada identitas permintaan yang stabil.

Aturan:

- Request manual menggunakan request identifier yang stabil.
- Eksekusi jadwal menggunakan identitas schedule dan waktu occurrence yang telah dinormalisasi.
- Retry terhadap job menggunakan Job ID yang sama.
- Timestamp saat retry tidak boleh menghasilkan identitas permintaan baru.
- Idempotency Key harus memiliki mekanisme unique constraint atau perlindungan atomik yang setara.

Jangan menggunakan kombinasi topik, model, dan timestamp saat ini sebagai satu-satunya identitas idempotency.

Permintaan topik yang sama pada dua sesi pembelajaran berbeda tetap boleh menghasilkan dua job berbeda.

6.3 Worker Execution

Worker bertanggung jawab mengambil job dan menjalankan pipeline.

Requirements:

- Worker hanya boleh mengambil job yang tersedia.
- Pengambilan job harus dilakukan secara atomik.
- Worker harus memverifikasi status job sebelum memulai eksekusi.
- Worker harus mencatat heartbeat atau lease sesuai mekanisme yang digunakan.
- Worker tidak boleh menjalankan satu job yang sama secara bersamaan pada beberapa eksekusi aktif.
- Worker harus melepaskan hak eksekusi setelah selesai atau gagal.

6.4 Job Status Model

Status job MVP:

Status| Meaning| Terminal
Queued| Menunggu eksekusi atau waktu retry| No
Running| Sedang diproses oleh worker| No
Completed| Seluruh pipeline berhasil| Yes
Failed| Eksekusi gagal dan tidak dapat dilanjutkan| Yes
Cancelled| Job dihentikan secara eksplisit| Yes

Retry tidak perlu menjadi status job terpisah.

Ketika job menunggu retry, status job adalah Queued, sementara status tahap dan "Available At" menjelaskan waktu serta proses retry.

6.5 Allowed Job Transitions

Queued
  |
  v
Running
  |
  +---------> Completed
  |
  +---------> Failed
  |
  +---------> Queued (Retry)
  |
  +---------> Cancelled

Running
  |
  +---------> Queued (Recoverable Failure)
  |
  +---------> Failed
  |
  +---------> Cancelled

Transisi harus divalidasi oleh Application Coordinator.

Status terminal tidak boleh berubah kembali menjadi status aktif melalui proses normal.

Jika job terminal perlu diulang, sistem membuat job baru dengan identitas baru dan referensi terhadap job sebelumnya apabila diperlukan.

6.6 Stage Execution State

Status tahap pipeline dikelola secara terpisah dari status job.

Status tahap:

Status| Meaning
Pending| Belum dijalankan
Running| Sedang dijalankan
Retry Wait| Menunggu retry
Completed| Berhasil diselesaikan
Failed| Gagal secara permanen
Skipped| Dilewati karena kondisi yang diizinkan

Setiap tahap memiliki:

- Stage Run ID.
- Job ID.
- Stage Name.
- Attempt Number.
- Stage Status.
- Started At.
- Completed At.
- Input Reference.
- Output Reference.
- Error Information.

Status tahap tidak boleh digunakan untuk menggantikan status job.

6.7 Retry and Recovery

Retry hanya boleh diterapkan pada kegagalan yang dapat dipulihkan.

Contoh kegagalan yang mungkin dapat dipulihkan:

- Timeout provider.
- Gangguan jaringan sementara.
- Rate limit yang memungkinkan retry.
- Gangguan layanan eksternal sementara.

Contoh kegagalan yang umumnya tidak boleh di-retry tanpa perubahan:

- Input tidak valid.
- Konfigurasi wajib tidak tersedia.
- Format data tidak sesuai kontrak.
- Akses ditolak secara permanen.
- Pelanggaran aturan governance.

Retry policy harus memiliki:

- Maximum attempts.
- Delay sebelum retry.
- Backoff strategy.
- Klasifikasi error.
- Catatan setiap attempt.

Nilai konfigurasi final ditentukan dalam Technical Design.

6.8 Worker Crash Recovery

Apabila worker berhenti ketika job masih Running:

1. Sistem harus dapat mendeteksi worker yang sudah tidak aktif.
2. Hak eksekusi yang kedaluwarsa dapat dipulihkan melalui mekanisme lease.
3. Sistem memeriksa checkpoint tahap terakhir.
4. Tahap yang belum selesai diproses ulang sesuai retry policy.
5. Data hasil tahap yang telah selesai tidak boleh ditimpa tanpa validasi.
6. Job yang sudah mencapai batas retry harus ditangani sesuai kebijakan kegagalan.

Recovery tidak boleh bergantung hanya pada ingatan proses worker.

---

7. Persistence Architecture

7.1 Data Storage Requirements

Data utama Cognis harus disimpan dalam penyimpanan persisten yang mendukung:

- Konsistensi relasi data.
- Pencatatan identitas unik.
- Validasi constraint.
- Transaksi yang dibutuhkan untuk perubahan status.
- Penyimpanan metadata.
- Pencarian data.
- Backup dan recovery.

Pemilihan teknologi database menjadi keputusan tersendiri.

7.2 Core Data Entities

Model data konseptual MVP terdiri dari:

LearningJob

Menyimpan identitas, pemicu, topik, status, dan metadata job.

JobStageRun

Menyimpan riwayat eksekusi setiap tahap.

ResearchRun

Menyimpan identitas dan metadata proses penelitian.

SourceRecord

Menyimpan identitas, metadata, dan hasil validasi sumber.

ClaimRecord

Menyimpan klaim yang ditemukan atau dirumuskan dari materi penelitian.

EvidenceRecord

Menyimpan bukti yang digunakan dalam evaluasi klaim.

ClaimEvidenceLink

Menyimpan hubungan antara klaim dan bukti.

EvidenceAssessment

Menyimpan hasil penilaian dukungan bukti, kontradiksi, dan ketidakpastian.

KnowledgeRecord

Menyimpan hasil pembelajaran yang dapat ditelusuri ke sumber dan evaluasi.

LearningReport

Menyimpan laporan akhir yang terkait dengan job.

ModelInvocation

Menyimpan metadata pemanggilan model.

ConfigurationVersion

Menyimpan referensi versi konfigurasi prompt dan konfigurasi operasional yang digunakan.

7.3 Logical Relationship

LearningJob
    |
    +---- JobStageRun
    |
    +---- ResearchRun
    |         |
    |         +---- SourceRecord
    |         |
    |         +---- ClaimRecord
    |                    |
    |                    +---- ClaimEvidenceLink
    |                    |          |
    |                    |          +---- EvidenceRecord
    |                    |
    |                    +---- EvidenceAssessment
    |
    +---- KnowledgeRecord
    |
    +---- LearningReport
    |
    +---- ModelInvocation
    |
    +---- ConfigurationVersion

Hubungan tersebut merupakan model logis. Struktur tabel, collection, index, dan foreign key ditentukan pada dokumen data design atau technical design.

7.4 Knowledge Record Integrity

Setiap KnowledgeRecord harus memiliki informasi yang cukup untuk:

- Menentukan asal job.
- Menentukan domain dan topik.
- Mengidentifikasi sumber pendukung.
- Menemukan klaim terkait.
- Menemukan hasil evaluasi.
- Mengetahui waktu penyimpanan.
- Memeriksa versi atau riwayat.

KnowledgeRecord tidak boleh menjadi salinan teks yang kehilangan hubungan terhadap asal informasinya.

7.5 Knowledge Status and Validity

Status penyimpanan tidak boleh dicampur dengan penilaian kebenaran informasi.

Sistem harus membedakan:

Storage State

Menjelaskan kondisi record dalam penyimpanan, misalnya aktif, superseded, atau archived.

Evidence Assessment

Menjelaskan kekuatan dukungan bukti terhadap suatu klaim.

Temporal Validity

Menjelaskan kapan informasi berlaku, kapan diterbitkan, dan apakah informasi berpotensi kedaluwarsa.

Record yang aktif di database tidak otomatis berarti isinya benar atau masih berlaku.

Informasi lama tidak boleh dihapus hanya karena ditemukan informasi baru. Perubahan relevansi harus dicatat tanpa menghilangkan provenance historis.

---

8. Research and Source Architecture

8.1 Research Provider Abstraction

Research Engine tidak boleh bergantung langsung pada satu implementasi provider.

Setiap provider harus diakses melalui adapter dengan kontrak internal yang konsisten.

Input minimum:

- Research Topic.
- Search Query.
- Domain.
- Time Context.
- Retrieval Constraints.

Output minimum:

- Source Identity.
- Source URL.
- Retrieved Content atau Reference.
- Publisher Metadata jika tersedia.
- Publication Date jika tersedia.
- Retrieval Timestamp.
- Retrieval Status.

8.2 Source Identity

Sumber harus memiliki identitas internal yang konsisten.

URL dapat digunakan sebagai salah satu atribut sumber, tetapi tidak selalu menjadi identitas permanen karena:

- URL dapat berubah.
- Halaman dapat diperbarui.
- Halaman dapat dihapus.
- Satu penerbit dapat menerbitkan beberapa versi materi.

Jika konten berubah, sistem harus mempertimbangkan penyimpanan versi atau snapshot yang relevan.

8.3 External Content Trust Boundary

Seluruh konten eksternal harus diperlakukan sebagai data yang tidak tepercaya.

Instruksi yang ditemukan dalam halaman web, dokumen, maupun hasil pencarian tidak boleh memperoleh kewenangan untuk:

- Mengubah system prompt.
- Mengubah policy.
- Mengakses kredensial.
- Mengubah konfigurasi internal.
- Menjalankan perintah sistem.
- Memperluas izin akses.

Konten eksternal hanya boleh diproses sebagai materi penelitian sesuai batas keamanan yang ditetapkan.

8.4 Source Validation Separation

Research dan Source Validation harus tetap menjadi tanggung jawab yang terpisah.

Research menjawab:

"Apa yang ditemukan?"

Source Validation menjawab:

"Seberapa layak sumber ini digunakan?"

Satu sumber dapat ditemukan oleh Research tanpa otomatis dinyatakan layak oleh Source Validator.

---

9. Evidence Evaluation Architecture

9.1 Claim-Centered Evaluation

Evidence Evaluation berpusat pada klaim, bukan sekadar ringkasan artikel.

Setiap klaim penting harus dapat dihubungkan dengan bukti pendukung atau bukti yang bertentangan.

9.2 Evidence Types

Sistem setidaknya harus dapat merepresentasikan:

- Supporting Evidence.
- Contradicting Evidence.
- Contextual Evidence.
- Insufficient Evidence.

Jenis tersebut menjelaskan hubungan bukti dengan klaim, bukan penilaian final mengenai kebenaran klaim.

9.3 Assessment Output

Setiap assessment mencatat:

- Claim ID.
- Evidence References.
- Support Relationship.
- Evidence Quality.
- Contradictions.
- Limitations.
- Uncertainty.
- Assessment Summary.

9.4 Conclusion Constraints

Kesimpulan harus mengikuti kekuatan bukti.

Jika bukti tidak cukup, sistem harus menyatakan bahwa klaim belum dapat dipastikan.

Jika sumber saling bertentangan, sistem harus menjelaskan pertentangan tersebut.

Jika kesimpulan memerlukan asumsi, asumsi harus dinyatakan secara eksplisit.

---

10. Learning Report Architecture

10.1 Report Generation Inputs

Report Generator menggunakan:

- Learning Job.
- Research Results.
- Validated Sources.
- Claims.
- Evidence Records.
- Evidence Assessments.
- Knowledge Records.
- Model and Configuration Metadata yang relevan.

10.2 Report Generation Rules

Report Generator harus:

- Menggunakan data yang telah tersimpan.
- Mempertahankan referensi sumber.
- Memisahkan fakta dan interpretasi.
- Menampilkan keterbatasan.
- Menampilkan ketidakpastian.
- Menghindari klaim yang tidak didukung.
- Menggunakan bahasa Indonesia.

10.3 Report Versioning

Setiap laporan harus memiliki identitas dan versi.

Perubahan laporan tidak boleh menghilangkan laporan atau hasil historis tanpa mekanisme versioning yang jelas.

10.4 Report Completion

Job hanya dapat dinyatakan Completed apabila seluruh hasil wajib pipeline, termasuk Learning Report, sudah berhasil disimpan.

---

11. Model Integration Architecture

11.1 Provider Independence

Logika pipeline tidak boleh terikat langsung pada satu model atau provider.

Model dipanggil melalui Model Provider Adapter.

11.2 Invocation Metadata

Setiap pemanggilan model yang relevan harus mencatat:

- Invocation ID.
- Job ID.
- Stage Name.
- Provider.
- Model Identifier.
- Model Version jika tersedia.
- Prompt Configuration Reference.
- Request Timestamp.
- Response Timestamp.
- Execution Status.
- Error Information.
- Token Usage atau penggunaan resource jika tersedia.

11.3 Configuration Versioning

Konfigurasi yang digunakan dalam satu job harus dapat diidentifikasi kembali.

Perubahan konfigurasi harus menghasilkan versi baru atau identitas konfigurasi baru.

Riwayat job harus mempertahankan referensi konfigurasi yang benar-benar digunakan.

11.4 Provider Failure

Kegagalan provider harus ditangani oleh adapter dan diteruskan sebagai hasil yang dapat dipahami Application Coordinator.

Fallback ke provider lain hanya diperbolehkan apabila strategi fallback telah dikonfigurasi, diuji, dan dicatat.

Sistem tidak boleh berpindah provider secara diam-diam lalu menganggap hasilnya setara tanpa pencatatan.

---

12. Interface and Application Contracts

12.1 Internal Module Contracts

Setiap modul harus berkomunikasi melalui kontrak input dan output yang terdokumentasi.

Minimal, kontrak mencakup:

- Identifier.
- Required Fields.
- Optional Fields.
- Validation Rules.
- Output Schema.
- Error Types.
- Version Compatibility.

12.2 Application-Level Operations

MVP setidaknya membutuhkan operasi logis berikut:

Create Learning Job

Menerima permintaan dan membuat job pembelajaran.

Get Job Status

Mengambil status dan progres job.

Get Job Detail

Mengambil detail eksekusi job.

List Learning Jobs

Mengambil riwayat job.

Get Learning Report

Mengambil laporan hasil pembelajaran.

Get Research Sources

Mengambil sumber penelitian yang terkait dengan job.

Trigger Scheduled Learning

Menghasilkan job dari konfigurasi jadwal.

Operasi tersebut merupakan kontrak aplikasi, bukan ketentuan URL API atau metode HTTP final.

12.3 Authorization Boundary

Akses untuk membuat job, menjalankan fungsi operasional, membaca hasil, serta mengubah konfigurasi harus memiliki otorisasi yang sesuai.

MVP tidak boleh mengekspos fungsi administratif internal melalui endpoint publik tanpa proteksi.

---

13. Security Architecture

13.1 Secret Management

API key, token, credential, dan secret lain tidak boleh:

- Disimpan di source code.
- Dimasukkan ke dalam laporan.
- Dicetak ke log.
- Dimasukkan ke response error yang bisa diakses pengguna.
- Dikirim ke model tanpa kebutuhan yang sah.

Secret harus disimpan melalui mekanisme konfigurasi atau secret management yang sesuai dengan lingkungan deployment.

13.2 Input Validation

Seluruh input eksternal harus divalidasi sebelum diproses.

Validasi mencakup:

- Tipe data.
- Panjang input.
- Format.
- Required fields.
- Batas resource.
- Batas akses.

13.3 Prompt Injection Defense

Konten dari web dan dokumen eksternal dapat berisi instruksi yang berbahaya atau manipulatif.

Sistem harus:

- Memisahkan instruksi sistem dari konten eksternal.
- Memperlakukan konten eksternal sebagai data.
- Tidak memberikan akses tool berdasarkan instruksi dari sumber.
- Membatasi hak akses setiap komponen.
- Memvalidasi tindakan sebelum dijalankan.

13.4 Network and Retrieval Security

Jika Research Provider mengambil URL atau konten eksternal secara langsung, implementasi harus mempertimbangkan:

- Private network access restrictions.
- Internal service address restrictions.
- Redirect validation.
- URL scheme validation.
- Response size limits.
- Request timeouts.
- Content type validation.

Akses terhadap alamat internal dan metadata service tidak boleh dibuka hanya karena suatu URL berasal dari hasil pencarian.

13.5 Auditability

Aksi operasional yang berpengaruh terhadap integritas job, konfigurasi, atau data harus dapat ditelusuri.

Audit record tidak boleh menyimpan secret atau data sensitif yang tidak diperlukan.

---

14. Reliability and Observability

14.1 Logging

Sistem harus mencatat peristiwa penting, termasuk:

- Job Created.
- Job Started.
- Stage Started.
- Stage Completed.
- Stage Failed.
- Retry Scheduled.
- Worker Recovered.
- Job Completed.
- Job Failed.
- Job Cancelled.
- Provider Error.

14.2 Structured Logging

Log harus memiliki konteks yang cukup untuk menghubungkan kejadian.

Field minimum jika relevan:

- Timestamp.
- Job ID.
- Stage Run ID.
- Component.
- Event Type.
- Severity.
- Error Code.
- Correlation ID.

14.3 Metrics

Metrik operasional minimum:

- Total Jobs.
- Completed Jobs.
- Failed Jobs.
- Active Jobs.
- Stage Duration.
- Job Duration.
- Retry Count.
- Provider Failure Count.
- Resource Usage jika tersedia.

Metrik harus menggambarkan kondisi aktual, bukan nilai estimasi yang disajikan sebagai data nyata.

14.4 Health Monitoring

Sistem harus menyediakan mekanisme untuk memeriksa:

- Application Availability.
- Database Connectivity.
- Worker Availability.
- Scheduler Availability.
- Provider Availability jika didukung.

Kegagalan satu provider eksternal tidak boleh otomatis dianggap sebagai kegagalan seluruh sistem.

14.5 Backup and Recovery

Sistem harus memiliki strategi backup terhadap data yang diperlukan untuk memulihkan:

- Riwayat job.
- Data penelitian.
- Sumber.
- Klaim dan bukti.
- Knowledge Records.
- Learning Reports.
- Konfigurasi yang diperlukan untuk operasional.

Backup baru boleh dianggap terverifikasi setelah proses restore berhasil diuji.

RPO dan RTO harus ditentukan berdasarkan kebutuhan operasional dan kemampuan infrastruktur yang dipilih.

---

15. Deployment Architecture

15.1 MVP Deployment Model

Arsitektur deployment awal dapat terdiri dari:

1. Application Runtime.
2. Worker Runtime.
3. Scheduler Runtime.
4. Persistent Database.
5. External Provider Connections.
6. Logging and Monitoring.

Komponen runtime boleh menggunakan codebase dan artefak deployment yang sama.

Pemisahan proses dilakukan untuk mengisolasi pekerjaan terjadwal, request pengguna, dan pemrosesan yang berjalan lama.

15.2 Deployment Constraints

- Sistem harus dapat dijalankan tanpa memerlukan arsitektur multi-region.
- Worker harus dapat dihentikan dan dijalankan kembali tanpa kehilangan seluruh progres.
- Scheduler harus mencegah eksekusi ganda.
- Database menjadi sumber kebenaran untuk status job dan data persisten.
- Konfigurasi lingkungan harus dipisahkan dari source code.
- Deployment tidak boleh merusak data historis.

15.3 Scaling Strategy

Scaling dilakukan secara bertahap berdasarkan bukti kebutuhan.

Urutan yang disarankan:

1. Optimasi query dan penggunaan resource.
2. Pengaturan concurrency worker.
3. Pemisahan proses scheduler dan worker apabila belum dipisahkan.
4. Penambahan kapasitas database.
5. Penggunaan queue infrastructure khusus jika diperlukan.
6. Pemisahan modul menjadi layanan tersendiri apabila batas beban dan kebutuhan operasional membenarkannya.

Microservices bukan target wajib MVP.

---

16. Testing Architecture

16.1 Unit Testing

Setiap modul harus dapat diuji secara terpisah.

Fokus pengujian:

- Input validation.
- Status transition.
- Idempotency.
- Source validation rules.
- Evidence mapping.
- Knowledge persistence rules.
- Report generation.
- Error classification.

16.2 Integration Testing

Pengujian integrasi harus memverifikasi hubungan antar-komponen.

Contoh:

- Application Coordinator dengan Job Storage.
- Worker dengan Job Queue.
- Research Engine dengan Provider Adapter.
- Source Validator dengan Source Records.
- Evidence Evaluator dengan Claim dan Evidence Storage.
- Knowledge Manager dengan Persistence Layer.
- Report Generator dengan seluruh output pipeline.

16.3 End-to-End Testing

Setidaknya harus ada pengujian untuk satu siklus pembelajaran penuh:

Create Job → Execute Pipeline → Store Knowledge → Generate Report → Retrieve Report

16.4 Failure Testing

Pengujian harus mencakup:

- Provider timeout.
- Provider rate limit.
- Database connection failure.
- Worker termination.
- Duplicate job request.
- Invalid input.
- Missing source metadata.
- Empty research result.
- Conflicting evidence.
- Report generation failure.
- Retry exhaustion.

16.5 Governance Testing

Pengujian harus memastikan:

- Konten eksternal tidak dapat mengubah system policy.
- Model tidak dapat mengubah konfigurasi inti secara otomatis.
- Penyimpanan knowledge tidak mengubah prompt atau parameter model.
- Endpoint administratif dilindungi.
- Secret tidak muncul pada log atau laporan.

---

17. Architecture Decision Boundaries

Dokumen ini menetapkan keputusan arsitektur berikut sebagai baseline MVP:

Area| Decision
Architecture Style| Modular Monolith
Processing Model| Asynchronous Job Processing
Core Workflow| Sequential Learning Pipeline
Job State| Persisted and Observable
Pipeline State| Independently Tracked
Job Recovery| Checkpoint-Based
Idempotency| Stable Request Identity
Data Provenance| Required
Knowledge Storage| Persistent Reference Knowledge
Model Integration| Provider Adapter
External Content| Untrusted Input
System Modification| Not Allowed Automatically
Microservices| Deferred
Automatic Faculty Progression| Deferred
Founder Approval Workflow| Deferred

Keputusan tersebut menjadi acuan untuk implementasi MVP.

17.1 Implementation Decisions Still Open

Hal berikut belum ditentukan oleh dokumen arsitektur ini:

- Programming language.
- Backend framework.
- Frontend framework.
- Database engine.
- Database schema implementation.
- Queue implementation.
- Scheduler library.
- Research provider.
- Model provider.
- Model routing strategy.
- Deployment platform.
- Authentication implementation.
- Storage technology untuk dokumen atau snapshot.
- Concrete retry values.
- Resource limits.

Setiap keputusan harus dicatat dalam dokumen teknis terkait atau Architecture Decision Record (ADR) apabila memiliki dampak arsitektur yang signifikan.

---

18. Future Architecture Evolution

Arsitektur Cognis harus memungkinkan pengembangan berikutnya tanpa memaksa MVP membangunnya sekarang.

Phase 2: Competency and Evaluation

Potensi pengembangan:

- Competency Registry.
- Curriculum Management.
- Learning Assessment.
- Benchmark Management.
- Competency Progress Tracking.

Phase 3: Governed Improvement

Potensi pengembangan:

- Improvement Proposal Engine.
- Founder Review Interface.
- Approval Workflow.
- Change Implementation.
- Regression Testing.
- Rollback Management.

Phase 4: Advanced Intelligence

Potensi pengembangan:

- Multi-Agent Orchestration.
- Specialized Research Agents.
- Advanced Knowledge Retrieval.
- Model Evaluation and Routing.
- Advanced Long-Term Memory.
- Controlled Fine-Tuning jika terbukti diperlukan.

Setiap fase membutuhkan evaluasi dan keputusan pengembangan tersendiri.

Tidak ada fase masa depan yang boleh dianggap otomatis aktif hanya karena telah tercantum dalam dokumen.

---

19. Architecture Risks

19.1 Overengineering

Risk:

Membangun terlalu banyak layanan dan infrastruktur sebelum kebutuhan operasional terbukti.

Mitigation:

Gunakan modular monolith dan pisahkan deployment hanya jika ada alasan yang terukur.

19.2 Data Provenance Loss

Risk:

Hasil penelitian tersimpan tanpa hubungan ke sumber dan bukti.

Mitigation:

Terapkan provenance sebagai bagian wajib dari model data.

19.3 Duplicate Execution

Risk:

Scheduler, retry, atau request berulang menghasilkan job ganda.

Mitigation:

Gunakan idempotency key yang stabil dan pengamanan transaksi.

19.4 Worker Crash

Risk:

Proses berhenti sebelum pipeline selesai.

Mitigation:

Gunakan persistent job state, checkpoint, lease, dan recovery mechanism.

19.5 Provider Dependency

Risk:

Perubahan provider merusak logika pipeline.

Mitigation:

Gunakan provider adapter dan kontrak internal.

19.6 False Confidence

Risk:

Model menyajikan kesimpulan yang terlihat kuat meskipun dukungan buktinya lemah.

Mitigation:

Pisahkan claim, evidence, assessment, dan conclusion.

19.7 Governance Bypass

Risk:

Input eksternal atau komponen pipeline dapat memengaruhi aturan internal.

Mitigation:

Pertahankan trust boundary, access control, dan governance tests.

---

20. Architecture Completion Criteria

Arsitektur MVP dianggap siap diimplementasikan apabila:

1. Seluruh komponen utama memiliki tanggung jawab yang jelas.
2. Aliran data utama telah didefinisikan.
3. Job lifecycle telah memiliki status dan transisi yang konsisten.
4. Status job terpisah dari status tahap pipeline.
5. Retry dan recovery memiliki aturan yang jelas.
6. Idempotency tidak bergantung pada timestamp eksekusi saat ini.
7. Model data mempertahankan provenance.
8. Integrasi provider memiliki batas adapter.
9. Trust boundary untuk konten eksternal telah ditentukan.
10. Kebutuhan observability telah didefinisikan.
11. Batas keamanan dan governance telah ditentukan.
12. Keputusan teknis yang belum dibuat tercatat secara eksplisit.
13. Arsitektur dapat diuji melalui unit, integration, dan end-to-end tests.

Dokumen ini tidak membuktikan bahwa implementasi telah selesai atau bahwa sistem sudah memenuhi seluruh persyaratan.

Keberhasilan hanya dapat dinyatakan setelah implementasi dan pengujian memberikan bukti yang sesuai.

---

21. Final Architecture Principle

Cognis harus memiliki arsitektur yang cukup sederhana untuk dibangun, cukup terstruktur untuk diuji, dan cukup kuat untuk dikembangkan.

Kompleksitas bukan ukuran kecanggihan.

Jumlah agent bukan ukuran kecerdasan.

Jumlah data bukan ukuran pemahaman.

Arsitektur yang baik adalah arsitektur yang membuat setiap proses dapat dijelaskan, setiap hasil dapat ditelusuri, setiap kegagalan dapat ditangani, dan setiap peningkatan dapat dibuktikan.

Build the learning pipeline first. Prove reliability and evidence integrity. Expand autonomy only when the foundation deserves it.