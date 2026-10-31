COGNIS AI

SYSTEM ARCHITECTURE

Project: Cognis AI
Repository: "cognis"
Document Version: 1.0
Status: Proposed Architecture
Architecture Style: Modular Monolith with Asynchronous Workers
Primary Interface: Telegram
Primary Language: Bahasa Indonesia

---

1. Tujuan Dokumen

Dokumen ini menjelaskan arsitektur teknis Cognis AI, termasuk komponen utama, tanggung jawab setiap komponen, alur komunikasi, pengelolaan data, integrasi AI, proses penelitian, dan Autonomous Learning System (ALS).

Tujuannya adalah menyediakan rancangan teknis yang:

1. Dapat dijalankan menggunakan infrastruktur terbatas.
2. Dapat dikembangkan secara bertahap.
3. Tidak bergantung pada satu penyedia AI.
4. Mendukung proses riset dan pembelajaran jangka panjang.
5. Mendukung banyak pengguna dengan isolasi data.
6. Menyediakan kontrol manusia terhadap perubahan permanen.
7. Memungkinkan pengembangan model dan kemampuan AI di masa depan tanpa membangun ulang seluruh aplikasi.

Arsitektur ini merupakan rancangan awal. Keputusan teknologi yang belum diuji harus tetap dianggap sebagai keputusan sementara sampai divalidasi melalui implementasi dan pengujian.

2. Prinsip Arsitektur

2.1 Modular Monolith First

Cognis menggunakan satu aplikasi utama dengan modul-modul yang memiliki tanggung jawab jelas.

Pada tahap awal, modul-modul tersebut tidak perlu dijalankan sebagai layanan terpisah.

Keuntungan pendekatan ini:

- Lebih mudah dikembangkan.
- Lebih hemat resource.
- Lebih sederhana untuk debugging.
- Tidak memerlukan infrastruktur microservices.
- Memudahkan pengujian integrasi.
- Memungkinkan ekstraksi modul menjadi layanan terpisah ketika memang dibutuhkan.

Pemisahan tanggung jawab harus dilakukan sejak awal pada level kode, meskipun deployment masih berupa satu aplikasi.

2.2 Asynchronous by Design

Pekerjaan yang membutuhkan waktu panjang harus dijalankan melalui background jobs.

Contohnya:

- Penelitian multi-sumber.
- Analisis dokumen panjang.
- Pembelajaran kompetensi.
- Evaluasi benchmark.
- Penyusunan laporan harian.
- Pemrosesan dataset.

Jangan menjalankan seluruh pekerjaan panjang dalam satu request yang membuat aplikasi menunggu hingga selesai.

2.3 Provider Independence

Semua penyedia AI dan layanan eksternal harus diakses melalui adapter atau interface yang terdefinisi.

Logika bisnis Cognis tidak boleh terikat langsung pada SDK atau format khusus satu provider.

2.4 Human-Governed Evolution

ALS boleh mengidentifikasi kelemahan dan mengusulkan peningkatan secara mandiri.

Namun, perubahan permanen terhadap kurikulum, kebijakan pembelajaran, standar evaluasi, konfigurasi produksi yang kritis, dan model harus mengikuti mekanisme persetujuan.

2.5 Data Provenance

Setiap informasi penting harus memiliki asal-usul yang dapat ditelusuri.

Cognis harus mampu membedakan:

- Informasi yang ditemukan.
- Informasi yang sudah diverifikasi.
- Interpretasi hasil analisis.
- Hipotesis.
- Kesimpulan yang masih memiliki ketidakpastian.

2.6 Resource-Aware Engineering

Arsitektur harus mempertimbangkan:

- RAM.
- CPU.
- Kapasitas penyimpanan.
- API rate limits.
- Token consumption.
- Biaya model.
- Waktu eksekusi.
- Kapasitas background worker.

Jangan menambahkan infrastruktur atau dependency yang belum memiliki manfaat terukur.

3. High-Level System Architecture

Cognis terdiri dari beberapa lapisan logis.

1. Presentation Layer.
2. Application and Orchestration Layer.
3. Intelligence Layer.
4. Research Layer.
5. Autonomous Learning and Competency Layer.
6. Knowledge and Memory Layer.
7. Data and Infrastructure Layer.
8. Governance and Security Layer.

3.1 Architecture Diagram

flowchart TB
    USER["Authorized Users"]

    subgraph PRESENTATION["Presentation Layer"]
        TG["Telegram Adapter"]
        FUTURE["Future Web Interface"]
    end

    subgraph APPLICATION["Application and Orchestration"]
        API["Application Services"]
        JOB["Job Manager"]
        SCHED["Scheduler"]
        ROUTER["Task Router"]
    end

    subgraph INTELLIGENCE["Intelligence Layer"]
        MG["Model Gateway"]
        PROMPT["Prompt and Context Manager"]
        MODEL1["AI Provider A"]
        MODEL2["AI Provider B"]
    end

    subgraph RESEARCH["Research Layer"]
        RE["Research Engine"]
        SOURCE["Source Evaluator"]
        EVIDENCE["Evidence Manager"]
        EXT["External Search and Data Sources"]
    end

    subgraph LEARNING["Learning and Competency"]
        ALS["Autonomous Learning System"]
        CE["Competency Engine"]
        EVAL["Evaluation Engine"]
    end

    subgraph KNOWLEDGE["Knowledge and Memory"]
        KM["Knowledge Manager"]
        RM["Retrieval and Memory"]
    end

    subgraph GOVERNANCE["Governance and Security"]
        APPROVAL["Approval Manager"]
        AUDIT["Audit Logger"]
        ACCESS["Access Control"]
    end

    subgraph DATA["Data Layer"]
        DB[("PostgreSQL")]
        FILES[("Document Storage")]
    end

    USER --> TG
    USER --> FUTURE
    TG --> API
    FUTURE --> API

    API --> ACCESS
    API --> JOB
    API --> ROUTER

    SCHED --> JOB
    JOB --> ROUTER

    ROUTER --> MG
    MG --> PROMPT
    MG --> MODEL1
    MG --> MODEL2

    ROUTER --> RE
    RE --> EXT
    RE --> SOURCE
    SOURCE --> EVIDENCE

    ROUTER --> ALS
    ALS --> CE
    ALS --> EVAL
    EVAL --> MG
    ALS --> APPROVAL

    RE --> KM
    EVAL --> KM
    ALS --> KM
    KM --> RM

    APPROVAL --> AUDIT
    API --> AUDIT
    ACCESS --> AUDIT

    API --> DB
    JOB --> DB
    RE --> DB
    ALS --> DB
    CE --> DB
    EVAL --> DB
    KM --> DB
    AUDIT --> DB

    RE --> FILES
    KM --> FILES

Diagram ini menggambarkan hubungan logis. Diagram ini bukan berarti setiap kotak harus menjadi server atau proses yang berdiri sendiri.

4. Presentation Layer

Presentation Layer mengatur bagaimana pengguna berkomunikasi dengan Cognis.

4.1 Telegram Adapter

Telegram merupakan antarmuka interaksi pertama.

Tanggung jawab:

- Menerima pesan pengguna.
- Memeriksa identitas dan hak akses.
- Mengubah pesan menjadi perintah aplikasi.
- Mengirim perintah ke Application Layer.
- Menampilkan status pekerjaan.
- Mengirim hasil penelitian.
- Menampilkan notifikasi dan laporan.
- Menerima keputusan persetujuan.

Telegram Adapter tidak boleh memuat logika penelitian atau pembelajaran.

Contoh:

Pesan:

"Analisis hubungan kebijakan suku bunga The Fed dengan harga emas."

Telegram Adapter meneruskan permintaan tersebut ke Application Layer sebagai Research Request.

Application Layer yang menentukan proses selanjutnya.

4.2 Future Interfaces

Arsitektur harus memungkinkan penambahan antarmuka lain, seperti:

- Web application.
- Mobile application.
- Dashboard administrasi.
- API untuk integrasi eksternal.

Penambahan antarmuka baru tidak boleh mengharuskan penulisan ulang seluruh logika bisnis.

5. Application and Orchestration Layer

Lapisan ini menjadi penghubung antarbagian sistem.

5.1 Application Services

Mengatur use cases utama Cognis.

Contoh layanan:

- SubmitResearchRequest.
- CreateLearningTask.
- GetTaskStatus.
- SubmitApprovalDecision.
- GetDailyLearningReport.
- SearchKnowledge.

Application Services tidak bertanggung jawab melakukan penalaran AI secara langsung.

Tugasnya adalah mengatur alur eksekusi dan memanggil komponen yang sesuai.

5.2 Task Router

Task Router mengidentifikasi jenis pekerjaan dan menentukan alur pemrosesan.

Contoh kategori:

Task Type| Tujuan
Research| Penelitian dan analisis
Learning| Proses pembelajaran ALS
Evaluation| Pengujian kompetensi
Summarization| Ringkasan informasi
Knowledge Retrieval| Pencarian memori
Reporting| Penyusunan laporan
Governance| Persetujuan perubahan

Task Router dapat menentukan model yang sesuai berdasarkan jenis pekerjaan, tetapi tidak boleh mengubah kebijakan keamanan atau persetujuan.

5.3 Job Manager

Job Manager mengelola pekerjaan asynchronous.

Setiap pekerjaan harus memiliki:

- Job ID.
- User ID atau tenant ID.
- Job type.
- Input reference.
- Execution status.
- Priority.
- Resource budget.
- Retry count.
- Checkpoint reference.
- Creation timestamp.
- Start timestamp.
- Completion timestamp.
- Error information.

Status pekerjaan yang didukung:

- PENDING.
- QUEUED.
- RUNNING.
- WAITING_APPROVAL.
- RETRY_WAIT.
- SUCCEEDED.
- FAILED.
- CANCELLED.

Job Manager harus mendukung:

1. Persistent job storage.
2. Retry dengan batas yang jelas.
3. Exponential backoff.
4. Checkpointing.
5. Recovery setelah aplikasi restart.
6. Idempotency untuk mencegah pemrosesan ganda.
7. Pembatalan pekerjaan yang masih aman untuk dibatalkan.

Pada tahap awal, gunakan database-backed job queue sebelum mempertimbangkan message broker tambahan.

5.4 Scheduler

Scheduler menjalankan pekerjaan berdasarkan jadwal atau kondisi tertentu.

Jadwal awal:

Schedule| Action
07:00 WIB| Meminta daily brief ketika belum tersedia
18:00 WIB| Mengirim daily learning report
Configurable| Menjalankan pekerjaan pembelajaran terjadwal

Scheduler harus:

- Menggunakan timezone Asia/Jakarta sebagai konfigurasi awal.
- Menyimpan identitas eksekusi jadwal.
- Mencegah job terbuat berulang akibat restart.
- Mendukung perubahan jadwal.
- Memastikan pekerjaan terlewat dapat dideteksi.
- Memisahkan waktu eksekusi dari logika pembelajaran.

Simpan timestamp sistem dalam UTC. Gunakan timezone pengguna untuk perhitungan jadwal dan tampilan.

6. Intelligence Layer

Intelligence Layer mengatur interaksi Cognis dengan model AI.

6.1 Model Gateway

Seluruh permintaan model harus melewati Model Gateway.

Tanggung jawab:

- Memilih provider dan model.
- Mengirim request.
- Mengelola timeout.
- Mengelola retry yang aman.
- Memproses response.
- Menghitung penggunaan token jika tersedia.
- Mencatat biaya jika tersedia.
- Menangani provider errors.
- Menerapkan batas penggunaan.
- Menyediakan fallback sesuai kebijakan.

Jangan menanamkan API call provider secara langsung ke dalam Research Engine atau ALS.

6.2 Provider Adapter

Setiap provider memiliki adapter sendiri.

Contoh struktur konseptual:

ModelGateway
    |
    ├── ProviderAdapterA
    |
    ├── ProviderAdapterB
    |
    └── ProviderAdapterC

Adapter bertanggung jawab menerjemahkan format internal Cognis ke format provider dan mengembalikan response dalam format internal yang konsisten.

Provider tertentu mungkin mendukung fitur yang berbeda. Perbedaan tersebut harus dinyatakan secara eksplisit.

6.3 Model Routing

Pemilihan model harus mempertimbangkan:

- Kompleksitas tugas.
- Kualitas penalaran.
- Kualitas ekstraksi.
- Kemampuan mengikuti instruksi.
- Context window.
- Latency.
- Cost.
- Ketersediaan provider.
- Batas penggunaan.
- Kebutuhan privasi.

Contoh pembagian pekerjaan:

Task| Model Requirement
Data extraction| Model yang efisien dan akurat
Classification| Model ringan jika hasilnya tervalidasi
Research analysis| Model dengan kemampuan reasoning memadai
Complex synthesis| Model dengan kemampuan analisis lebih tinggi
Evaluation| Model evaluator yang dikontrol dan diuji
User response| Model yang sesuai dengan kompleksitas jawaban

Model routing tidak boleh menganggap model mahal selalu benar atau model murah selalu buruk.

6.4 Prompt and Context Manager

Komponen ini mengelola konteks yang dikirim ke model.

Tanggung jawab:

- Mengambil instruksi yang relevan.
- Mengambil informasi terkait dari memory.
- Menggabungkan evidence.
- Mengatur panjang konteks.
- Menghindari konteks yang tidak relevan.
- Menyediakan identitas sumber.
- Memisahkan system instructions dari external content.

Retrieved documents dan hasil pencarian tidak boleh diperlakukan sebagai instruksi sistem.

6.5 Teacher and Worker Model Strategy

Cognis dapat menggunakan model dengan kemampuan berbeda untuk pekerjaan berbeda.

Konsep awal:

- Teacher Model: membantu analisis yang lebih kompleks, riset, dan evaluasi tertentu.
- Worker Model: mengerjakan tugas yang lebih terstruktur dan berulang.
- Evaluator Model: membantu penilaian berdasarkan rubric.
- Embedding Model: digunakan untuk representasi semantik apabila diperlukan.

Pembagian tersebut adalah peran fungsional, bukan asumsi bahwa sebuah model otomatis memiliki kemampuan tertentu.

Setiap model harus diuji sebelum diberikan tugas produksi.

7. Research Layer

Research Layer bertanggung jawab mengumpulkan, menilai, dan mengolah informasi eksternal.

7.1 Research Engine

Alur penelitian:

1. Menerima pertanyaan.
2. Menentukan tujuan dan batas penelitian.
3. Mengidentifikasi subpertanyaan.
4. Menentukan sumber yang diperlukan.
5. Mengambil informasi.
6. Mengekstraksi evidence.
7. Memeriksa relevansi dan kredibilitas.
8. Membandingkan sumber.
9. Menyusun analisis.
10. Menghasilkan laporan dengan referensi.

Research Engine harus mendukung pekerjaan bertahap dan dapat melanjutkan pekerjaan dari checkpoint.

7.2 Source Evaluator

Setiap sumber dievaluasi berdasarkan:

- Kredibilitas penerbit.
- Kredibilitas penulis.
- Kedekatan dengan sumber primer.
- Kualitas metodologi.
- Tanggal publikasi.
- Relevansi terhadap pertanyaan.
- Potensi konflik kepentingan.
- Keterbatasan data.

Source Evaluator tidak boleh menghasilkan klaim bahwa sebuah sumber benar hanya karena domainnya terkenal.

7.3 Evidence Manager

Evidence Manager menyimpan bukti yang digunakan dalam analisis.

Setiap evidence sebaiknya memiliki:

- Evidence ID.
- Source ID.
- Kutipan atau ringkasan yang relevan.
- Lokasi informasi dalam sumber.
- Tanggal publikasi jika tersedia.
- Tanggal pengambilan.
- Jenis sumber.
- Status verifikasi.
- Research Task ID.

Evidence harus dapat ditelusuri kembali ke sumber aslinya.

7.4 Research Output

Output penelitian harus memiliki struktur yang konsisten:

1. Pertanyaan dan ruang lingkup.
2. Ringkasan temuan.
3. Fakta dan evidence.
4. Analisis.
5. Interpretasi.
6. Bukti yang bertentangan.
7. Ketidakpastian dan keterbatasan.
8. Kesimpulan.
9. Referensi.

Sumber yang tidak dapat diverifikasi tidak boleh diberi label sebagai sumber terverifikasi.

8. Autonomous Learning and Competency Layer

Lapisan ini merupakan inti diferensiasi Cognis.

8.1 Autonomous Learning System

ALS mengelola seluruh siklus pembelajaran.

Siklus utama:

flowchart TD
    A["Inspect Competency State"]
    B["Identify Knowledge Gap"]
    C["Create Learning Objective"]
    D["Research and Study"]
    E["Create Learning Output"]
    F["Run Evaluation"]
    G{"Evaluation Passed?"}
    H["Record Competency Result"]
    I["Identify Weaknesses"]
    J["Generate Improvement Proposal"]
    K{"Permanent Change?"}
    L["Request Human Approval"]
    M{"Approved?"}
    N["Apply Approved Change"]
    O["Post-change Evaluation"]
    P{"Regression Detected?"}
    Q["Keep Verified Change"]
    R["Rollback or Revise"]
    S["Update Learning History"]

    A --> B --> C --> D --> E --> F --> G
    G -->|Yes| H
    G -->|No| I
    H --> I
    I --> J --> K
    K -->|No| S
    K -->|Yes| L --> M
    M -->|No| S
    M -->|Yes| N --> O --> P
    P -->|No| Q --> S
    P -->|Yes| R --> S

ALS tidak boleh mengubah sistem permanen hanya berdasarkan satu hasil evaluasi.

8.2 Competency Engine

Competency Engine mengatur struktur kemampuan yang harus dikembangkan.

Tanggung jawab:

- Menyimpan competency definitions.
- Mengatur competency levels.
- Menghubungkan kompetensi dengan learning objectives.
- Menentukan prerequisites.
- Mengelola mastery criteria.
- Menyimpan assessment history.

Kompetensi tidak boleh didefinisikan hanya berdasarkan daftar topik yang telah dibaca.

Setiap kompetensi harus dapat dihubungkan dengan aktivitas atau tugas yang menunjukkan kemampuan nyata.

8.3 Evaluation Engine

Evaluation Engine menguji hasil pembelajaran.

Jenis evaluasi dapat mencakup:

- Factual recall.
- Conceptual understanding.
- Quantitative reasoning.
- Causal analysis.
- Critical analysis.
- Case study.
- Research synthesis.
- Decision-making under uncertainty.

Evaluasi harus menggunakan scoring rubric yang terdefinisi.

Untuk mengurangi bias, gunakan test set independen dan held-out evaluation cases.

8.4 Change Proposal System

Semua usulan perubahan permanen harus masuk melalui Change Proposal System.

Proposal minimal memiliki:

- Proposal ID.
- Target component.
- Existing condition.
- Identified weakness.
- Proposed change.
- Supporting evidence.
- Expected benefit.
- Risk assessment.
- Implementation plan.
- Evaluation plan.
- Rollback plan.
- Approval status.

Status proposal:

- DRAFT.
- PENDING_REVIEW.
- APPROVED.
- REJECTED.
- IMPLEMENTING.
- VERIFIED.
- ROLLED_BACK.
- CLOSED.

ALS tidak boleh mengubah status approval berdasarkan keputusan internal model.

9. Knowledge and Memory Layer

Knowledge Layer mengelola informasi yang digunakan dalam proses reasoning dan pembelajaran.

9.1 Knowledge Categories

Pisahkan knowledge menjadi beberapa kategori.

General Knowledge

Pengetahuan umum yang relatif stabil.

Contoh:

- Teori ekonomi.
- Prinsip akuntansi.
- Konsep mikroekonomi.
- Dasar statistik.

Contextual Knowledge

Informasi yang berkaitan dengan pengguna, proyek, atau aktivitas tertentu.

Akses harus mengikuti batasan kepemilikan dan izin.

Time-Sensitive Knowledge

Informasi yang dapat berubah sewaktu-waktu.

Contoh:

- Harga emas.
- Data inflasi terbaru.
- Suku bunga.
- Perubahan regulasi.
- Perkembangan geopolitik.

Informasi ini harus diverifikasi menggunakan sumber terkini sebelum digunakan untuk menjawab pertanyaan yang membutuhkan kondisi terbaru.

Evaluated Knowledge

Pengetahuan yang telah melalui proses validasi dengan standar yang ditentukan.

Status evaluated tidak berarti informasi tersebut benar untuk semua konteks atau tidak akan pernah kedaluwarsa.

9.2 Knowledge Lifecycle

flowchart LR
    A["Raw Information"]
    B["Extracted Knowledge"]
    C["Source Assessment"]
    D{"Validation Result"}
    E["Accepted Knowledge"]
    F["Rejected or Quarantined"]
    G["Periodic Review"]
    H["Updated or Deprecated"]

    A --> B --> C --> D
    D -->|Pass| E
    D -->|Fail| F
    E --> G --> H

9.3 Retrieval System

Tahap awal dapat menggunakan pencarian database dan full-text search.

Vector search tidak wajib diterapkan sejak awal.

Pertimbangkan vector search hanya setelah pengujian menunjukkan bahwa pencarian biasa tidak cukup memenuhi kebutuhan retrieval.

Setiap hasil retrieval harus membawa metadata sumber dan status validasinya.

9.4 Memory Boundaries

Memory tidak boleh menjadi tempat penyimpanan semua informasi tanpa klasifikasi.

Pisahkan:

- User preferences.
- Conversation context.
- Research records.
- Knowledge records.
- Competency state.
- Evaluation records.
- Governance records.

Penghapusan atau perubahan memory harus mengikuti aturan kepemilikan data, retensi, dan audit.

10. Governance and Security Layer

10.1 Access Control

Setiap request yang mengakses data terlindungi harus melalui pemeriksaan authorization.

Sistem harus membedakan minimal:

- User.
- Administrator.
- System worker.

Hak akses tidak boleh bergantung pada klaim model.

10.2 Multi-User Isolation

Arsitektur harus mendukung banyak pengguna sejak awal.

Data yang bersifat privat harus memiliki keterkaitan kepemilikan atau tenant yang jelas.

Setiap query yang membaca atau mengubah data privat harus memeriksa hak akses.

Tidak boleh mengandalkan Telegram user ID sebagai satu-satunya mekanisme authorization untuk seluruh sistem.

10.3 Human Approval Enforcement

Approval Manager harus menjadi kontrol aplikasi yang independen dari model AI.

Model dapat mengusulkan perubahan.

Model tidak dapat menyetujui usulannya sendiri.

Perubahan permanen harus melewati:

1. Proposal creation.
2. Authorization check.
3. Human decision.
4. Approval record.
5. Controlled execution.
6. Verification.
7. Audit recording.

10.4 Audit Logging

Catat aktivitas penting:

- Login atau authorization events.
- Research task creation.
- Learning task execution.
- Model calls.
- Approval decisions.
- Permanent configuration changes.
- Knowledge promotion.
- Rollback.
- Administrative operations.

Jangan menyimpan API key, password, atau token sensitif ke dalam audit log.

10.5 Prompt Injection Protection

Semua informasi eksternal dianggap sebagai data tidak tepercaya.

Termasuk:

- Website.
- Dokumen PDF.
- Email.
- File yang diunggah.
- Hasil pencarian.
- Tool outputs.

Informasi eksternal tidak boleh mengubah instruksi sistem, mengakses secret, atau memperluas hak akses.

10.6 Tool Permission Model

Tool yang digunakan AI harus melalui allowlist.

Setiap tool harus mempunyai:

- Identitas.
- Tujuan.
- Input schema.
- Permission requirement.
- Execution limits.
- Timeout.
- Output validation.
- Audit trail.

Eksekusi command atau kode yang tidak dibatasi tidak diperbolehkan dalam MVP.

11. Data Architecture

11.1 Primary Database

PostgreSQL menjadi pilihan database utama yang diusulkan.

Alasan:

- Mendukung transaksi.
- Mendukung banyak pengguna.
- Mendukung relational data.
- Cocok untuk job management awal.
- Mendukung pencarian terstruktur.
- Dapat dikembangkan untuk kebutuhan lebih besar.

Konfigurasi PostgreSQL harus disesuaikan dengan kapasitas VPS.

11.2 Data Ownership

Tabel yang berisi data pengguna harus memiliki mekanisme kepemilikan atau tenant association yang jelas.

Entitas global dan entitas privat harus dipisahkan secara logis.

Jangan menganggap seluruh knowledge otomatis boleh dibagikan ke semua pengguna.

11.3 Main Data Entities

Detail schema ditetapkan dalam "docs/technical/DATABASE_SCHEMA.md".

Entitas utama yang perlu dipertimbangkan:

Entity| Responsibility
users| Identitas pengguna
tenants| Batas organisasi atau ruang data
memberships| Hubungan pengguna dan tenant
conversations| Riwayat interaksi
jobs| Status pekerjaan asynchronous
job_checkpoints| Progress pekerjaan
model_providers| Konfigurasi provider
model_usage| Penggunaan dan biaya model
research_tasks| Permintaan dan proses riset
sources| Metadata sumber
evidence| Bukti penelitian
knowledge_items| Informasi yang disimpan
competencies| Definisi kompetensi
learning_objectives| Tujuan pembelajaran
learning_sessions| Aktivitas pembelajaran
evaluations| Hasil penilaian
benchmarks| Definisi benchmark
change_proposals| Usulan perubahan
approval_records| Keputusan persetujuan
audit_logs| Riwayat aktivitas kritis

Nama dan struktur tabel final harus mengikuti kebutuhan implementasi, bukan dipaksakan hanya karena tercantum dalam daftar ini.

11.4 Document Storage

Dokumen atau file berukuran besar tidak harus disimpan langsung sebagai database records.

Gunakan storage terpisah ketika kebutuhan sudah muncul.

Metadata dokumen tetap disimpan dalam database.

File storage harus memiliki:

- Ownership metadata.
- Access controls.
- Integrity checks.
- Retention policy.
- Backup strategy.

11.5 Vector Database

Vector database bukan dependency wajib MVP.

Urutan keputusan:

1. Implementasikan relational database.
2. Implementasikan full-text search.
3. Ukur retrieval quality.
4. Identifikasi kegagalan retrieval.
5. Uji embedding dan vector search jika diperlukan.
6. Adopsi hanya jika manfaatnya terbukti.

12. Deployment Architecture

12.1 Initial Deployment

Deployment awal menggunakan satu VPS dengan komponen yang terkontrol.

Konsep deployment:

COGNIS VPS
|
├── Application
|   ├── Telegram Adapter
|   ├── Application Services
|   ├── Model Gateway
|   └── API
|
├── Background Worker
|   ├── Research Jobs
|   ├── Learning Jobs
|   └── Evaluation Jobs
|
├── Scheduler
|
├── PostgreSQL
|
└── Persistent Storage

Komponen tersebut dapat berjalan dari satu repository dan satu deployment environment.

Pemisahan process dilakukan untuk menghindari pekerjaan berat menghambat interaksi pengguna.

12.2 Infrastructure Strategy

Pada tahap awal:

- Gunakan VPS untuk application runtime.
- Gunakan database lokal pada VPS atau layanan database yang sesuai dengan anggaran dan kebutuhan backup.
- Gunakan API provider untuk inference.
- Hindari menjalankan model besar secara lokal.
- Hindari GPU rental sebelum kebutuhan dan utilisasinya terbukti.
- Gunakan storage eksternal hanya jika dibutuhkan.

Kapasitas infrastruktur aktual harus diuji sebelum menetapkan jumlah worker dan concurrency.

12.3 Communication

Komunikasi internal antar-modul dilakukan melalui interface aplikasi.

Komunikasi ke layanan eksternal dilakukan melalui adapter.

Hindari menambahkan jaringan komunikasi internal antar-microservices sebelum pemisahan layanan benar-benar diperlukan.

13. Main Data Flows

13.1 Research Request Flow

sequenceDiagram
    participant U as User
    participant T as Telegram Adapter
    participant A as Application Layer
    participant J as Job Manager
    participant R as Research Engine
    participant M as Model Gateway
    participant D as Database

    U->>T: Submit research request
    T->>A: Forward request
    A->>A: Authorization and validation
    A->>J: Create research job
    J->>D: Persist job
    A-->>T: Job accepted
    T-->>U: Return job ID

    J->>R: Execute research
    R->>M: Analyze evidence
    M-->>R: Analysis result
    R->>D: Store sources and report
    R->>J: Mark job completed
    J->>T: Notify completion
    T-->>U: Deliver research report

13.2 Learning Flow

sequenceDiagram
    participant S as Scheduler
    participant ALS as ALS
    participant CE as Competency Engine
    participant R as Research Engine
    participant E as Evaluation Engine
    participant G as Governance Manager
    participant U as User
    participant D as Database

    S->>ALS: Start learning cycle
    ALS->>CE: Read competency state
    CE-->>ALS: Competency gaps
    ALS->>R: Create learning task
    R-->>ALS: Research results
    ALS->>E: Submit learning output
    E-->>ALS: Evaluation result
    ALS->>D: Save learning history
    ALS->>G: Create improvement proposal
    G->>D: Save proposal
    G-->>U: Request approval
    U->>G: Approve or reject
    G->>D: Record decision
    G-->>ALS: Return authorized decision

13.3 Approval Boundary

Approval must happen outside the model's own reasoning process.

A model response stating that a change has been approved is not a valid approval record.

Only an authenticated action accepted by Approval Manager can authorize the change.

14. Reliability and Failure Handling

The system must anticipate failure from:

- AI provider downtime.
- API rate limits.
- Network interruptions.
- Telegram API errors.
- Database failures.
- Worker crashes.
- Incomplete research.
- Invalid model output.
- Insufficient resource budget.

14.1 Job Recovery

Long-running jobs must persist state.

When a worker fails:

1. Identify the last successful checkpoint.
2. Inspect job status.
3. Verify that the previous operation was not already committed.
4. Resume from a safe checkpoint.
5. Prevent duplicate side effects.
6. Record recovery events.

14.2 Retry Policy

Retries must be bounded.

Use exponential backoff with jitter for retryable failures.

Do not retry indefinitely.

Do not retry permanent validation failures as though they were network problems.

14.3 Failure Classification

Separate:

- Transient failures.
- Provider errors.
- Rate-limit failures.
- Validation failures.
- Authorization failures.
- Resource budget exhaustion.
- Permanent application failures.

Every failed job must retain enough information for diagnosis without leaking secrets.

15. Resource and Cost Management

Every expensive operation should have a resource budget.

Budget dimensions may include:

- Maximum model calls.
- Maximum token usage.
- Maximum execution time.
- Maximum retries.
- Maximum external requests.
- Maximum file size.
- Maximum concurrent jobs.
- Maximum cost per job.

The system must support:

1. Task-level budget.
2. User-level budget.
3. Daily usage budget.
4. Global operational budget.

Budgets must be checked before expensive operations.

When the budget is exhausted, the job must stop or enter a controlled waiting state.

Do not silently continue using more expensive models.

Record usage and estimated cost where provider information is available.

16. Observability

Cognis must produce structured logs and operational metrics.

Minimum observability requirements:

- Application startup and shutdown.
- Job creation and completion.
- Job failure.
- Worker execution.
- Model provider response.
- API latency.
- Token usage.
- Estimated API cost.
- Research source counts.
- Learning cycle status.
- Evaluation results.
- Approval events.
- Database errors.

Never log credentials or sensitive personal information unnecessarily.

Logs must support diagnosis without exposing private user data to unauthorized users.

17. Backup and Recovery

Database backups must be implemented before Cognis becomes dependent on persistent learning history.

Initial requirements:

- Automated database backup.
- Backup integrity verification.
- Retention policy.
- Secure storage.
- Document storage backup where applicable.
- Recovery procedure.
- Periodic restoration test.

A backup that has never been restored successfully must not be treated as a verified recovery strategy.

Detailed instructions belong in "docs/operations/BACKUP_RECOVERY.md".

18. Scalability and Future Evolution

The architecture must support gradual evolution.

Potential future capabilities:

- Multiple AI providers.
- More specialized model roles.
- Advanced retrieval systems.
- Dedicated research agents.
- Specialized competency agents.
- Fine-tuning pipelines.
- Evaluation datasets.
- Model version comparison.
- Web application.
- Multi-tenant subscription system.
- Dedicated worker infrastructure.
- GPU-based model experimentation.

These are future possibilities, not MVP commitments.

Extract a module into a separate service only when there is a measurable reason, such as:

- Independent scaling requirements.
- Different resource requirements.
- Reliability isolation.
- Deployment independence.
- Clear operational benefits.

19. Initial Architecture Decisions

Decision| Proposed Direction| Status
Architecture style| Modular monolith| Proposed
Background execution| Database-backed jobs| Proposed
Primary database| PostgreSQL| Proposed
AI integration| Provider abstraction| Required principle
Initial interface| Telegram| Required
Scheduling| Configurable scheduler| Proposed
Memory storage| Relational and file storage| Proposed
Retrieval| Full-text first, vector later if justified| Proposed
Deployment| Single VPS initially| Proposed
Model training| Not part of MVP| Agreed scope
Multi-user support| Architecturally supported from the beginning| Required principle
Tool execution| Allowlisted and restricted| Required principle

Any change to these decisions must be documented through an Architecture Decision Record (ADR).

20. Architecture Validation Requirements

Before considering the architecture ready for full implementation, verify:

1. Application modules have clear responsibilities.
2. Telegram logic is separated from business logic.
3. AI providers can be replaced through adapters.
4. Long-running work uses persistent jobs.
5. Failed jobs can recover safely.
6. Research sources are traceable.
7. Knowledge categories are separated.
8. Competency evaluation has independent records.
9. Permanent changes require authenticated approval.
10. User data is isolated.
11. API usage and resource budgets are enforceable.
12. Backups and recovery are feasible within the infrastructure budget.

These requirements must be tested, not merely acknowledged in documentation.

21. Related Documents

This document is connected to:

- "AGENTS.md"
- "PRD.md"
- "docs/autonomous-learning/AUTONOMOUS_LEARNING_SPEC.md"
- "docs/autonomous-learning/COMPETENCY_CURRICULUM.md"
- "docs/autonomous-learning/EVALUATION_FRAMEWORK.md"
- "docs/intelligence/MODEL_STRATEGY.md"
- "docs/intelligence/DATA_MEMORY_SPEC.md"
- "docs/governance/SECURITY_GOVERNANCE.md"
- "docs/technical/DATABASE_SCHEMA.md"
- "docs/technical/API_CONTRACTS.md"
- "docs/technical/TEST_STRATEGY.md"
- "docs/operations/DEPLOYMENT_RUNBOOK.md"
- "docs/operations/BACKUP_RECOVERY.md"

---

End of Document