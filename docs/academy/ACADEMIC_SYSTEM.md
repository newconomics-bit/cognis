ACADEMIC SYSTEM

COGNIS

Document Version: 1.0
Product Version: MVP v1
Status: Proposed Academic Structure Baseline
Document Owner: Founder
System: Cognis Academic System
Primary Language: Indonesian
Primary Timezone: Asia/Jakarta

---

1. Purpose

Dokumen ini mendefinisikan struktur akademik internal Cognis untuk mengorganisasi bidang pengetahuan, kompetensi, program pembelajaran, dan aktivitas penelitian.

Tujuan Academic System adalah memberikan struktur yang konsisten terhadap proses pembelajaran Cognis agar setiap aktivitas memiliki hubungan yang jelas dengan bidang studi dan tujuan pembelajaran.

Dokumen ini mengatur:

1. Struktur organisasi akademik.
2. Fakultas dan departemen.
3. Program studi.
4. Mata pembelajaran dan modul.
5. Learning Units.
6. Learning Activities.
7. Hubungan antara struktur akademik dan kurikulum.
8. Pengelolaan katalog akademik.
9. Pembagian tanggung jawab akademik.
10. Batas implementasi Academic System pada MVP.

Academic System menjadi lapisan organisasi akademik yang menggunakan kompetensi dari "COMPETENCY_CURRICULUM.md".

Dokumen ini tidak menggantikan spesifikasi pembelajaran, penilaian, atau kebijakan kenaikan tingkat.

---

2. Academic System Vision

Cognis dirancang memiliki struktur pembelajaran yang menyerupai organisasi akademik terintegrasi.

Sistem dapat mengorganisasi pengetahuan melalui:

- Faculty.
- Department.
- Study Program.
- Course.
- Module.
- Learning Unit.
- Learning Activity.

Setiap struktur memiliki fungsi tersendiri.

Academic System harus memungkinkan Cognis mengembangkan kompetensi dari tingkat dasar hingga analisis lintas domain tanpa kehilangan hubungan antara materi pembelajaran, kurikulum, dan tujuan akademik.

Struktur ini merupakan sistem organisasi internal AI.

Struktur fakultas dan program studi tidak berarti Cognis merupakan institusi pendidikan resmi, universitas terakreditasi, atau lembaga yang berwenang memberikan gelar akademik.

---

3. Academic Principles

3.1 Structured Knowledge Organization

Seluruh bidang pengetahuan harus memiliki struktur organisasi yang jelas.

Informasi tidak boleh dikelompokkan secara sembarangan tanpa memperhatikan hubungan konseptualnya.

3.2 Competency Alignment

Setiap program dan materi pembelajaran harus terhubung dengan kompetensi yang relevan.

Academic System menggunakan kompetensi sebagai fondasi untuk menentukan apa yang harus dipelajari.

3.3 Interdisciplinary Integration

Permasalahan nyata sering melibatkan beberapa bidang keilmuan.

Academic System harus memungkinkan satu topik pembelajaran menggabungkan kompetensi dari beberapa fakultas tanpa memaksakan satu bidang menjadi satu-satunya pemilik topik.

3.4 Progressive Learning Structure

Materi harus dapat diorganisasi berdasarkan tingkat kedalaman:

- Foundation.
- Applied.
- Analytical.
- Strategic.

Tingkat tersebut mengikuti definisi dalam "COMPETENCY_CURRICULUM.md".

Struktur akademik tidak boleh secara otomatis menyatakan bahwa Cognis telah mencapai suatu tingkat hanya karena materi pada tingkat tersebut telah dipelajari.

3.5 Separation of Responsibilities

Academic System bertanggung jawab atas organisasi pembelajaran.

Competency Curriculum bertanggung jawab atas definisi kompetensi.

Assessment System bertanggung jawab atas evaluasi kemampuan.

Faculty Progression Policy bertanggung jawab atas aturan kenaikan tingkat.

Scheduler bertanggung jawab atas waktu eksekusi pembelajaran.

Pemisahan tersebut harus dipertahankan.

---

4. Academic Hierarchy

4.1 Main Structure

Struktur akademik Cognis:

COGNIS ACADEMIC SYSTEM
          |
          v
       FACULTY
          |
          v
      DEPARTMENT
          |
          v
     STUDY PROGRAM
          |
          v
        COURSE
          |
          v
        MODULE
          |
          v
     LEARNING UNIT
          |
          v
   LEARNING ACTIVITY

Tidak semua aktivitas harus menggunakan seluruh tingkat hierarki.

Sebagai contoh, penelitian lintas domain dapat memiliki hubungan dengan beberapa fakultas, program studi, dan kompetensi sekaligus.

4.2 Structure Definitions

Faculty

Fakultas adalah organisasi akademik utama yang mewakili satu domain pengetahuan.

Department

Departemen adalah pengelompokan bidang keilmuan yang lebih spesifik di dalam fakultas.

Study Program

Program studi adalah jalur pembelajaran yang dirancang untuk mengembangkan kelompok kompetensi tertentu.

Course

Course adalah kelompok materi pembelajaran yang memiliki tujuan akademik dan ruang lingkup tertentu.

Module

Module adalah bagian dari course yang mengelompokkan materi berdasarkan topik atau kompetensi.

Learning Unit

Learning Unit adalah satuan materi pembelajaran yang memiliki tujuan dan ruang lingkup yang lebih spesifik.

Learning Activity

Learning Activity adalah aktivitas yang digunakan untuk mempelajari, meneliti, menjelaskan, atau menerapkan suatu materi.

4.3 Optional Relationships

Satu objek akademik boleh terhubung dengan lebih dari satu objek pada tingkat yang sama apabila hubungan tersebut memang diperlukan.

Contoh:

- Satu course dapat mendukung beberapa kompetensi.
- Satu kompetensi dapat digunakan dalam beberapa course.
- Satu Learning Unit dapat menjadi bagian dari beberapa program studi.
- Satu Learning Activity dapat mendukung beberapa Learning Objectives.

Hubungan tersebut harus direpresentasikan secara eksplisit, bukan melalui asumsi berdasarkan kemiripan nama.

---

5. Faculty Structure

Cognis memiliki lima fakultas utama.

Foundational Competencies merupakan kurikulum inti lintas fakultas dan bukan fakultas keenam.

5.1 Faculty of Economics

Faculty ID: FAC-ECO
Domain ID: ECO

Purpose:

Mengembangkan kemampuan memahami sistem ekonomi, perilaku pelaku ekonomi, kebijakan publik, pertumbuhan, stabilitas, dan hubungan ekonomi internasional.

Primary Competency Areas:

- Economic Foundations.
- Microeconomics.
- Industrial Economics.
- Macroeconomics.
- Monetary Economics.
- Fiscal Economics.
- International Economics.
- Development Economics.
- Economic Research.
- Economic Policy Analysis.

Competency Coverage:

ECO-001 sampai ECO-010.

Academic Objective:

Cognis mampu memahami mekanisme ekonomi dan mengevaluasi kebijakan maupun fenomena ekonomi berdasarkan teori, data, serta bukti yang relevan.

5.2 Faculty of Business

Faculty ID: FAC-BUS
Domain ID: BUS

Purpose:

Mengembangkan kemampuan memahami perusahaan, model bisnis, strategi, pasar, operasional, manajemen, dan persaingan industri.

Primary Competency Areas:

- Business Foundations.
- Market Research.
- Industry Analysis.
- Business Strategy.
- Operations Management.
- Supply Chain Management.
- Business Financial Analysis.
- Entrepreneurship.
- Management.
- Corporate Governance.

Competency Coverage:

BUS-001 sampai BUS-010.

Academic Objective:

Cognis mampu mengevaluasi keberlanjutan model bisnis, mengidentifikasi peluang dan risiko, serta menganalisis keputusan strategis perusahaan.

5.3 Faculty of Geopolitics

Faculty ID: FAC-GEO
Domain ID: GEO

Purpose:

Mengembangkan kemampuan memahami hubungan antarnegara, kepentingan strategis, konflik, keamanan, ekonomi politik internasional, dan perubahan distribusi kekuatan global.

Primary Competency Areas:

- International Relations.
- Strategic Analysis.
- Security Studies.
- Global Governance.
- Geoeconomics.
- Energy Geopolitics.
- Strategic Geography.
- International Political Economy.
- Geopolitical Research.
- Strategic Forecasting.

Competency Coverage:

GEO-001 sampai GEO-010.

Academic Objective:

Cognis mampu menganalisis kepentingan negara, dinamika geopolitik, konflik, dan risiko global dengan membedakan fakta, interpretasi, serta hipotesis.

5.4 Faculty of Finance

Faculty ID: FAC-FIN
Domain ID: FIN

Purpose:

Mengembangkan kemampuan memahami sistem keuangan, lembaga keuangan, instrumen, pembiayaan, manajemen risiko, dan stabilitas keuangan.

Primary Competency Areas:

- Financial System.
- Financial Mathematics.
- Financial Accounting.
- Banking.
- Financial Instruments.
- Corporate Finance.
- Risk Management.
- Financial Regulation.
- Financial Technology.

Competency Coverage:

FIN-001 sampai FIN-009.

Academic Objective:

Cognis mampu menganalisis sistem keuangan, kondisi lembaga keuangan, keputusan pembiayaan, serta risiko yang memengaruhi stabilitas keuangan.

5.5 Faculty of Financial Markets

Faculty ID: FAC-MKT
Domain ID: MKT

Purpose:

Mengembangkan kemampuan memahami pasar finansial, instrumen investasi, pembentukan harga, struktur pasar, likuiditas, perilaku pelaku pasar, dan manajemen risiko.

Primary Competency Areas:

- Market Structure.
- Asset Knowledge.
- Fundamental Analysis.
- Macro Market Analysis.
- Technical Analysis.
- Market Microstructure.
- Volume Analysis.
- Derivatives and Leverage.
- Trading and Investment Risk.
- Behavioral Analysis.
- Digital Asset Markets.
- Strategy Research.

Competency Coverage:

MKT-001 sampai MKT-012.

Academic Objective:

Cognis mampu menganalisis pasar finansial berdasarkan data, struktur pasar, kondisi fundamental, perilaku harga, dan risiko dengan mempertimbangkan keterbatasan masing-masing metode.

---

6. Foundational Academic Core

6.1 Purpose

Foundational Academic Core adalah kumpulan kompetensi dasar yang digunakan oleh seluruh fakultas.

Kompetensi ini tidak dimiliki secara eksklusif oleh satu fakultas karena dibutuhkan untuk seluruh proses analisis.

6.2 Core Competencies

Foundational Core mencakup:

- FND-001: Critical Thinking and Logical Reasoning.
- FND-002: Quantitative and Statistical Literacy.
- FND-003: Research and Evidence Evaluation.
- FND-004: Causal and Systems Thinking.
- FND-005: Data Interpretation and Time-Series Analysis.
- FND-006: Analytical Communication.
- FND-007: Decision Analysis and Risk Reasoning.
- FND-008: Research Ethics and Information Integrity.

6.3 Core Application

Foundational Core dapat diterapkan pada seluruh fakultas.

Contoh:

Dalam analisis geopolitik, FND-001 membantu mengevaluasi argumen dan asumsi.

Dalam analisis ekonomi, FND-002 membantu membaca data statistik.

Dalam penelitian pasar finansial, FND-003 membantu memvalidasi sumber dan bukti.

Dalam analisis bisnis, FND-004 membantu memahami hubungan antarvariabel dan konsekuensi keputusan.

6.4 Administrative Ownership

Foundational Core berada di bawah pengelolaan Academic System sebagai kurikulum lintas fakultas.

Fakultas dapat menggunakan kompetensi tersebut tanpa membuat salinan kompetensi baru.

Identitas FND harus tetap menjadi referensi utama.

---

7. Department Structure

Departemen mengelompokkan kompetensi yang memiliki hubungan konseptual dalam suatu fakultas.

Struktur berikut merupakan baseline organisasi akademik.

7.1 Economics Departments

DEP-ECO-01: Economic Foundations and Markets

Coverage:

- ECO-001.
- ECO-002.
- ECO-003.

DEP-ECO-02: Macroeconomics and Policy

Coverage:

- ECO-004.
- ECO-005.
- ECO-006.
- ECO-010.

DEP-ECO-03: International and Development Economics

Coverage:

- ECO-007.
- ECO-008.

DEP-ECO-04: Economic Research and Data

Coverage:

- ECO-009.

7.2 Business Departments

DEP-BUS-01: Business Strategy and Markets

Coverage:

- BUS-001.
- BUS-002.
- BUS-003.
- BUS-004.

DEP-BUS-02: Operations and Supply Chain

Coverage:

- BUS-005.
- BUS-006.

DEP-BUS-03: Business Finance and Performance

Coverage:

- BUS-007.

DEP-BUS-04: Entrepreneurship and Organization

Coverage:

- BUS-008.
- BUS-009.
- BUS-010.

7.3 Geopolitics Departments

DEP-GEO-01: International Relations and Strategy

Coverage:

- GEO-001.
- GEO-002.
- GEO-004.

DEP-GEO-02: Security and Conflict Studies

Coverage:

- GEO-003.

DEP-GEO-03: Geoeconomics and Resources

Coverage:

- GEO-005.
- GEO-006.
- GEO-008.

DEP-GEO-04: Strategic Geography and Intelligence

Coverage:

- GEO-007.
- GEO-009.
- GEO-010.

7.4 Finance Departments

DEP-FIN-01: Financial Systems and Banking

Coverage:

- FIN-001.
- FIN-004.
- FIN-008.

DEP-FIN-02: Financial Analysis and Instruments

Coverage:

- FIN-002.
- FIN-003.
- FIN-005.

DEP-FIN-03: Corporate Finance and Risk

Coverage:

- FIN-006.
- FIN-007.

DEP-FIN-04: Financial Technology

Coverage:

- FIN-009.

7.5 Financial Markets Departments

DEP-MKT-01: Market Foundations and Fundamentals

Coverage:

- MKT-001.
- MKT-002.
- MKT-003.
- MKT-004.

DEP-MKT-02: Market Structure and Analysis

Coverage:

- MKT-005.
- MKT-006.
- MKT-007.

DEP-MKT-03: Derivatives and Risk

Coverage:

- MKT-008.
- MKT-009.

DEP-MKT-04: Market Behavior and Digital Assets

Coverage:

- MKT-010.
- MKT-011.
- MKT-012.

7.6 Department Rules

Departemen digunakan untuk mengorganisasi kompetensi.

Satu kompetensi dapat memiliki hubungan tambahan dengan departemen lain jika memang diperlukan.

Hubungan tambahan tidak boleh membuat kepemilikan kompetensi menjadi ambigu.

Satu departemen memiliki satu fakultas induk.

Perubahan struktur departemen harus mengikuti versioning Academic System.

---

8. Study Program Structure

8.1 Definition

Study Program adalah jalur pembelajaran yang menggabungkan beberapa kompetensi untuk mencapai tujuan akademik tertentu.

Program studi tidak harus mencakup seluruh kompetensi dalam satu fakultas.

Program dapat berfokus pada bidang tertentu atau menggabungkan kompetensi lintas departemen.

8.2 Study Program Requirements

Setiap program studi harus memiliki:

- Study Program ID.
- Study Program Name.
- Faculty Owner.
- Description.
- Academic Objective.
- Target Competencies.
- Recommended Learning Pathway.
- Prerequisite References.
- Related Courses.
- Version.
- Status.

8.3 Recommended Study Programs

Program berikut merupakan katalog awal yang disarankan.

Faculty of Economics

PRG-ECO-01: Macroeconomic Analysis

Fokus:

- ECO-001.
- ECO-004.
- ECO-005.
- ECO-006.
- ECO-009.
- ECO-010.

Tujuan:

Membangun kemampuan menganalisis kondisi makroekonomi, kebijakan moneter dan fiskal, serta indikator ekonomi.

PRG-ECO-02: Microeconomics and Market Structure

Fokus:

- ECO-001.
- ECO-002.
- ECO-003.

Tujuan:

Memahami perilaku pelaku ekonomi, mekanisme harga, struktur pasar, dan persaingan.

PRG-ECO-03: International and Development Economics

Fokus:

- ECO-007.
- ECO-008.
- ECO-009.
- ECO-010.

Tujuan:

Memahami perdagangan internasional, pembangunan, ketimpangan, dan kebijakan ekonomi global.

Faculty of Business

PRG-BUS-01: Business Strategy and Management

Fokus:

- BUS-001.
- BUS-002.
- BUS-003.
- BUS-004.
- BUS-009.
- BUS-010.

Tujuan:

Membangun kemampuan mengevaluasi model bisnis, persaingan, strategi, dan organisasi perusahaan.

PRG-BUS-02: Operations and Supply Chain Management

Fokus:

- BUS-005.
- BUS-006.
- BUS-007.

Tujuan:

Menganalisis operasional, persediaan, distribusi, kapasitas, dan efisiensi bisnis.

PRG-BUS-03: Entrepreneurship and Business Development

Fokus:

- BUS-001.
- BUS-002.
- BUS-007.
- BUS-008.

Tujuan:

Mengevaluasi peluang bisnis, validasi pasar, unit economics, dan pengembangan usaha.

Faculty of Geopolitics

PRG-GEO-01: International Relations and Strategic Studies

Fokus:

- GEO-001.
- GEO-002.
- GEO-003.
- GEO-004.

Tujuan:

Memahami hubungan internasional, kepentingan negara, keamanan, dan diplomasi.

PRG-GEO-02: Geoeconomics and Global Resources

Fokus:

- GEO-005.
- GEO-006.
- GEO-008.

Tujuan:

Menganalisis hubungan kekuatan geopolitik, sumber daya, dan aktivitas ekonomi global.

PRG-GEO-03: Geopolitical Intelligence and Risk Analysis

Fokus:

- GEO-007.
- GEO-009.
- GEO-010.

Tujuan:

Menganalisis informasi strategis, risiko geopolitik, serta skenario alternatif.

Faculty of Finance

PRG-FIN-01: Financial Systems and Banking

Fokus:

- FIN-001.
- FIN-004.
- FIN-008.
- FIN-009.

Tujuan:

Memahami perbankan, lembaga keuangan, regulasi, dan infrastruktur sistem pembayaran.

PRG-FIN-02: Financial Analysis and Corporate Finance

Fokus:

- FIN-002.
- FIN-003.
- FIN-005.
- FIN-006.

Tujuan:

Menganalisis laporan keuangan, valuasi, instrumen, dan keputusan pembiayaan perusahaan.

PRG-FIN-03: Financial Risk Management

Fokus:

- FIN-005.
- FIN-007.
- FIN-008.

Tujuan:

Memahami risiko instrumen, portofolio, dan stabilitas keuangan.

Faculty of Financial Markets

PRG-MKT-01: Financial Market Analysis

Fokus:

- MKT-001.
- MKT-002.
- MKT-003.
- MKT-004.

Tujuan:

Membangun kemampuan analisis fundamental dan hubungan kondisi makroekonomi dengan pasar finansial.

PRG-MKT-02: Market Structure and Technical Analysis

Fokus:

- MKT-005.
- MKT-006.
- MKT-007.

Tujuan:

Memahami struktur harga, likuiditas, aktivitas transaksi, dan interpretasi teknikal.

PRG-MKT-03: Derivatives and Trading Risk

Fokus:

- MKT-008.
- MKT-009.
- MKT-012.

Tujuan:

Memahami instrumen derivatif, leverage, manajemen risiko, dan evaluasi strategi.

PRG-MKT-04: Digital Asset Markets

Fokus:

- MKT-002.
- MKT-006.
- MKT-008.
- MKT-009.
- MKT-011.

Tujuan:

Memahami infrastruktur, struktur pasar, likuiditas, derivatif, dan risiko aset digital.

---

9. Interdisciplinary Academic Structure

9.1 Purpose

Academic System harus mendukung pembelajaran yang melibatkan lebih dari satu fakultas.

Pembelajaran lintas domain tidak boleh dipaksakan masuk ke satu fakultas hanya demi kesederhanaan administrasi.

9.2 Interdisciplinary Studies

Pembelajaran lintas domain dikelola sebagai kategori akademik tersendiri di tingkat Academic System.

Kategori ini bukan fakultas tambahan.

Setiap pembelajaran lintas domain harus memiliki:

- Interdisciplinary Study ID.
- Research Topic.
- Primary Faculty.
- Supporting Faculties.
- Related Competencies.
- Learning Objectives.
- Scope.
- Expected Output.

Primary Faculty hanya menunjukkan domain utama untuk kebutuhan organisasi.

Primary Faculty tidak berarti fakultas tersebut memiliki seluruh kompetensi yang digunakan.

9.3 Initial Interdisciplinary Programs

XPRG-001: Global Political Economy

Integrasi:

- Economics.
- Geopolitics.
- Finance.

Fokus:

- Perdagangan internasional.
- Kebijakan ekonomi global.
- Sanksi.
- Arus modal.
- Kekuatan ekonomi negara.

XPRG-002: Energy and Commodity Systems

Integrasi:

- Economics.
- Geopolitics.
- Financial Markets.

Fokus:

- Supply and demand energi.
- Geopolitik sumber daya.
- Harga komoditas.
- Gangguan pasokan.
- Dampak terhadap inflasi.

XPRG-003: Monetary Policy and Financial Markets

Integrasi:

- Economics.
- Finance.
- Financial Markets.

Fokus:

- Bank sentral.
- Suku bunga.
- Nilai tukar.
- Obligasi.
- Emas.
- Arus modal.
- Valuasi aset.

XPRG-004: Business and Industrial Transformation

Integrasi:

- Business.
- Economics.
- Geopolitics.
- Finance.

Fokus:

- Perubahan industri.
- Persaingan perusahaan.
- Produktivitas.
- Kebijakan industri.
- Pembiayaan.
- Rantai pasok.

XPRG-005: Global Financial Stability

Integrasi:

- Economics.
- Finance.
- Geopolitics.
- Financial Markets.

Fokus:

- Stabilitas sistem keuangan.
- Risiko perbankan.
- Likuiditas.
- Kebijakan moneter.
- Risiko sistemik.
- Perubahan kondisi pasar.

9.4 Interdisciplinary Ownership

Setiap program lintas domain harus memiliki satu primary faculty untuk kebutuhan administrasi.

Kompetensi tetap menggunakan pemilik domain aslinya.

Penggabungan program tidak boleh menyebabkan duplikasi Competency ID.

---

10. Course Architecture

10.1 Definition

Course merupakan kelompok materi pembelajaran yang memiliki tujuan dan ruang lingkup tertentu.

Course harus berorientasi pada hasil pembelajaran, bukan hanya daftar topik.

10.2 Course Metadata

Setiap course minimal memiliki:

- Course ID.
- Course Name.
- Description.
- Faculty Reference.
- Department Reference jika tersedia.
- Study Program Reference jika tersedia.
- Competency References.
- Learning Objectives.
- Prerequisite References.
- Course Scope.
- Recommended Depth Level.
- Course Version.
- Status.

10.3 Course Types

Academic System mengenali beberapa jenis course.

Foundation Course

Membangun pemahaman konsep dan dasar pengetahuan.

Applied Course

Mengembangkan kemampuan menggunakan konsep untuk menganalisis kasus dan data.

Analytical Course

Mengembangkan kemampuan mengintegrasikan beberapa konsep dan mengevaluasi masalah kompleks.

Strategic Course

Mengembangkan kemampuan menganalisis skenario, trade-offs, dan masalah lintas domain.

Course Type menunjukkan tujuan dan kompleksitas materi.

Course Type tidak otomatis menyatakan bahwa Cognis telah memenuhi tingkat kompetensi terkait.

10.4 Course Boundaries

Course harus memiliki ruang lingkup yang jelas.

Satu course tidak boleh menggabungkan terlalu banyak topik yang tidak saling berhubungan.

Jika ruang lingkup terlalu luas, course dapat dibagi menjadi beberapa course yang lebih spesifik.

Jika beberapa course terlalu kecil dan saling bergantung, pengelompokan dapat dipertimbangkan.

10.5 Course Completion

Status Course Completion dan aturan kelulusan belum menjadi kebutuhan MVP v1.

Menyelesaikan aktivitas pembelajaran tidak otomatis berarti Cognis telah menguasai seluruh kompetensi course.

Kebijakan tersebut akan ditentukan melalui Assessment Policy dan Faculty Progression Policy.

---

11. Module Architecture

11.1 Definition

Module merupakan bagian dari course yang mengorganisasi materi berdasarkan tema, topik, atau kompetensi tertentu.

11.2 Module Metadata

Setiap module dapat memiliki:

- Module ID.
- Course ID.
- Module Name.
- Description.
- Competency References.
- Learning Objectives.
- Recommended Sequence.
- Required Knowledge.
- Related Learning Units.
- Version.
- Status.

11.3 Module Design Rules

Module harus:

- Memiliki ruang lingkup yang jelas.
- Terhubung dengan tujuan pembelajaran.
- Tidak menduplikasi materi tanpa alasan.
- Dapat dipelajari sebagai satu kelompok materi.
- Memiliki hubungan dengan kompetensi yang relevan.

Module tidak harus memiliki jumlah Learning Units yang sama.

Jumlah unit bergantung pada kebutuhan materi.

---

12. Learning Unit Architecture

12.1 Definition

Learning Unit adalah satuan materi paling spesifik dalam katalog akademik.

Learning Unit digunakan untuk mendefinisikan satu bagian pengetahuan atau kemampuan yang dapat dipelajari melalui aktivitas tertentu.

12.2 Learning Unit Metadata

Setiap Learning Unit minimal memiliki:

- Learning Unit ID.
- Module Reference jika tersedia.
- Topic.
- Description.
- Related Competency IDs.
- Learning Objectives.
- Required Context.
- Recommended Depth.
- Expected Learning Output.
- Related Sources jika tersedia.
- Version.
- Status.

12.3 Learning Unit Types

Concept Unit

Mempelajari konsep atau teori.

Data Unit

Mempelajari interpretasi data.

Method Unit

Mempelajari metode analisis.

Case Unit

Menganalisis kasus nyata atau historis.

Research Unit

Melakukan penelitian berdasarkan pertanyaan tertentu.

Integration Unit

Menghubungkan beberapa konsep atau domain.

12.4 Learning Unit Requirements

Learning Unit harus memiliki tujuan yang dapat dijelaskan.

Judul materi saja tidak cukup untuk menjadi definisi pembelajaran.

Contoh kurang tepat:

"Interest Rate."

Contoh lebih tepat:

"Mechanism of Interest Rate Transmission: memahami bagaimana perubahan suku bunga kebijakan dapat memengaruhi biaya pinjaman, permintaan agregat, nilai tukar, dan keputusan investasi."

12.5 Learning Unit Completion

Sistem boleh mencatat bahwa aktivitas pada Learning Unit telah selesai dijalankan.

Namun, penyelesaian aktivitas tidak boleh dianggap sebagai bukti penguasaan kompetensi tanpa assessment yang sesuai.

---

13. Learning Activity Architecture

13.1 Definition

Learning Activity merupakan aktivitas operasional yang dilakukan untuk mencapai tujuan pembelajaran.

Satu Learning Unit dapat memiliki beberapa Learning Activities.

13.2 Activity Types

Research Activity

Mengumpulkan informasi untuk menjawab pertanyaan penelitian.

Explanation Activity

Menjelaskan konsep atau mekanisme.

Data Analysis Activity

Menganalisis data dan indikator.

Comparative Activity

Membandingkan teori, kondisi, kebijakan, atau objek.

Case Study Activity

Menerapkan konsep terhadap kasus.

Synthesis Activity

Menggabungkan temuan dari berbagai sumber.

Assessment Activity

Menguji kemampuan melalui kriteria evaluasi yang telah ditetapkan.

Review Activity

Meninjau kembali pengetahuan atau hasil pembelajaran sebelumnya.

13.3 Activity Metadata

Setiap aktivitas dapat memiliki:

- Activity ID.
- Learning Unit Reference.
- Activity Type.
- Learning Objective.
- Input Requirements.
- Expected Output.
- Related Competencies.
- Time Context jika relevan.
- Execution Constraints.
- Status.

13.4 Activity Execution

Aktivitas yang memerlukan pemrosesan sistem dapat dijalankan melalui Learning Job.

Hubungan antara Academic Activity dan Learning Job harus disimpan secara eksplisit.

Satu aktivitas dapat menghasilkan satu atau beberapa job apabila desain proses membutuhkannya.

Satu job tidak harus dianggap sebagai satu course atau satu semester.

---

14. Academic System and Learning Pipeline Integration

14.1 Separation of Academic and Operational Layers

Academic System mengatur struktur pembelajaran.

Learning Pipeline menjalankan aktivitas penelitian dan pengolahan pengetahuan.

Keduanya memiliki fungsi yang berbeda.

Academic System menjawab:

- Bidang apa yang sedang dipelajari?
- Kompetensi apa yang relevan?
- Program studi mana yang sesuai?
- Materi apa yang menjadi ruang lingkup?
- Tujuan pembelajarannya apa?

Learning Pipeline menjawab:

- Bagaimana penelitian dijalankan?
- Sumber apa yang diperoleh?
- Bagaimana sumber divalidasi?
- Bagaimana bukti dievaluasi?
- Pengetahuan apa yang disimpan?
- Laporan apa yang dihasilkan?

14.2 Mapping Requirements

Ketika Learning Job berasal dari aktivitas akademik yang terstruktur, sistem harus menyimpan referensi yang relevan:

- Faculty ID jika tersedia.
- Department ID jika tersedia.
- Study Program ID jika tersedia.
- Course ID jika tersedia.
- Module ID jika tersedia.
- Learning Unit ID jika tersedia.
- Competency IDs jika tersedia.

Field yang tidak relevan atau tidak diketahui tidak boleh diisi dengan identitas buatan.

14.3 Direct Research Requests

Tidak seluruh penelitian harus berasal dari Course atau Learning Unit.

Founder dapat meminta penelitian secara langsung.

Dalam kondisi tersebut, sistem dapat menghubungkan job dengan domain atau kompetensi yang relevan tanpa harus membuat Course baru.

14.4 Academic Provenance

Laporan pembelajaran harus mempertahankan hubungan dengan struktur akademik yang digunakan apabila hubungan tersebut tersedia.

Hal ini memungkinkan operator mengetahui alasan suatu materi dipelajari dan kompetensi apa yang menjadi sasaran.

---

15. Academic Scheduling Boundary

15.1 Purpose

Academic System dapat menyediakan referensi jadwal pembelajaran yang akan digunakan oleh Scheduler.

Namun, pengaturan waktu dan eksekusi job tetap menjadi tanggung jawab Scheduler.

15.2 Academic Schedule Metadata

Konfigurasi jadwal akademik dapat mencakup:

- Schedule ID.
- Academic Activity Reference.
- Topic.
- Domain.
- Competency References.
- Preferred Execution Time.
- Timezone.
- Recurrence Rule.
- Resource Constraints.
- Status.

15.3 Scheduling Constraints

Academic System tidak boleh:

- Menjalankan job secara langsung.
- Mengelola worker.
- Mengubah status job.
- Mengabaikan batas resource.
- Membuat eksekusi ganda.
- Menganggap jadwal berarti aktivitas telah berhasil dilakukan.

15.4 MVP Boundary

Pada MVP v1, Scheduler hanya perlu mendukung jadwal dan pemicu pembelajaran yang telah dikonfigurasi.

Sistem tidak memerlukan kalender akademik kompleks, semester, tahun ajaran, atau sistem administrasi mahasiswa.

---

16. Academic Governance

16.1 Academic Ownership

Founder memiliki kewenangan atas arah dan perubahan permanen struktur akademik Cognis.

Perubahan katalog dapat dilakukan melalui proses pengelolaan dokumen dan perubahan sistem yang sesuai.

16.2 Academic Responsibilities

Founder

Bertanggung jawab terhadap:

- Arah pengembangan akademik.
- Penetapan fakultas.
- Perubahan ruang lingkup program studi.
- Persetujuan perubahan kurikulum inti.
- Keputusan final atas perubahan struktur akademik.

Academic System

Bertanggung jawab terhadap:

- Konsistensi struktur akademik.
- Hubungan antarobjek akademik.
- Validasi referensi akademik.
- Pengelolaan katalog.
- Pencatatan versi.

Learning Pipeline

Bertanggung jawab terhadap:

- Pelaksanaan aktivitas belajar.
- Penelitian.
- Validasi sumber.
- Evaluasi bukti.
- Penyimpanan pengetahuan.
- Pembuatan laporan.

16.3 AI Authority

AI boleh:

- Menggunakan katalog akademik.
- Memetakan topik ke fakultas.
- Mengidentifikasi kompetensi yang relevan.
- Mengusulkan hubungan antar-materi.
- Menyarankan kebutuhan pembelajaran tambahan.
- Menemukan kemungkinan duplikasi atau kekosongan materi.

AI tidak boleh secara otomatis:

- Membuat fakultas baru yang langsung aktif.
- Mengubah pemilik fakultas.
- Mengubah struktur departemen secara permanen.
- Menghapus program studi aktif.
- Mengubah kurikulum inti.
- Mengubah aturan akademik permanen.
- Memberikan kelulusan atau gelar.
- Menaikkan tingkat akademik secara sepihak.

16.4 Catalog Changes

Perubahan struktur akademik harus memiliki:

- Change ID.
- Object ID.
- Change Type.
- Previous Version.
- New Version.
- Change Rationale.
- Change Timestamp.
- Authorized Owner.

Perubahan harus dapat ditelusuri dan tidak menghilangkan riwayat akademik sebelumnya.

---

17. Academic Identifiers and Versioning

17.1 Identifier Standards

Setiap objek akademik harus memiliki identitas yang unik.

Format identitas baseline:

Entity| Identifier Format| Example
Faculty| FAC-{DOMAIN}| FAC-ECO
Department| DEP-{DOMAIN}-{NUMBER}| DEP-ECO-01
Study Program| PRG-{DOMAIN}-{NUMBER}| PRG-ECO-01
Interdisciplinary Program| XPRG-{NUMBER}| XPRG-001
Course| CRS-{DOMAIN}-{NUMBER}| CRS-ECO-001
Module| MOD-{DOMAIN}-{NUMBER}| MOD-ECO-001
Learning Unit| LUNIT-{DOMAIN}-{NUMBER}| LUNIT-ECO-001
Learning Activity| ACT-{DOMAIN}-{NUMBER}| ACT-ECO-001

Competency ID tetap mengikuti standar pada "COMPETENCY_CURRICULUM.md".

Academic ID tidak boleh menggantikan Competency ID.

17.2 Identifier Stability

Identifier yang sudah digunakan tidak boleh diberikan kepada objek berbeda.

Jika suatu objek sudah tidak aktif, identitasnya harus dipertahankan sebagai referensi historis.

17.3 Versioning

Setiap objek akademik yang mengalami perubahan bermakna harus memiliki versi.

Perubahan deskripsi minor dapat dicatat tanpa membuat identitas baru.

Perubahan tujuan atau ruang lingkup yang mendasar harus menghasilkan versi baru atau objek baru sesuai kebijakan.

17.4 Referential Integrity

Sistem harus memvalidasi referensi antarobjek.

Contoh:

- Department harus memiliki Faculty yang valid.
- Study Program harus memiliki Faculty Owner.
- Module harus terhubung dengan Course apabila memang menjadi bagian dari suatu Course.
- Learning Unit harus memiliki tujuan pembelajaran.
- Learning Activity harus memiliki referensi yang valid.
- Competency Reference harus sesuai dengan katalog kurikulum.

Referensi yang tidak ditemukan tidak boleh diabaikan secara diam-diam.

---

18. Academic Catalog Status

Setiap objek akademik harus memiliki status katalog.

Status baseline:

Status| Meaning
Draft| Belum siap digunakan
Active| Tersedia untuk aktivitas akademik
Deprecated| Tidak direkomendasikan untuk aktivitas baru
Archived| Disimpan untuk riwayat dan referensi

18.1 Status Rules

Draft tidak boleh diperlakukan sebagai katalog aktif.

Active dapat digunakan untuk pemetaan aktivitas baru.

Deprecated masih dapat digunakan untuk referensi historis atau proses yang sudah berjalan, tetapi tidak disarankan untuk aktivitas baru.

Archived dipertahankan untuk menjaga provenance dan riwayat.

18.2 Status and Competency

Status katalog tidak menunjukkan tingkat penguasaan kompetensi.

Objek akademik yang Active tidak berarti Cognis telah menyelesaikan atau menguasai seluruh materi di dalamnya.

---

19. Academic System Interface Requirements

Academic System pada MVP harus menyediakan kemampuan minimum untuk:

1. Membaca daftar fakultas.
2. Membaca daftar departemen.
3. Membaca daftar program studi.
4. Membaca daftar course dan module jika tersedia.
5. Membaca Learning Units.
6. Membaca kompetensi terkait.
7. Memetakan topik penelitian ke struktur akademik.
8. Mengakses hubungan antarobjek akademik.
9. Memeriksa status dan versi katalog.

Interface tidak harus berupa aplikasi administrasi akademik yang kompleks.

Katalog dapat disediakan melalui database, API, atau mekanisme internal lain sesuai desain teknis.

Namun, referensi akademik harus konsisten dan dapat diuji.

---

20. MVP v1 Scope

20.1 Included

MVP v1 mencakup:

- Lima fakultas utama.
- Foundational Academic Core.
- Struktur departemen sebagai katalog referensi.
- Program studi sebagai katalog referensi.
- Struktur Course dan Module sebagai model akademik.
- Learning Unit dan Learning Activity.
- Competency Mapping.
- Interdisciplinary Mapping.
- Academic Metadata pada Learning Job jika relevan.
- Katalog akademik dengan identifier dan status.
- Versioning dasar untuk perubahan katalog.

20.2 Excluded

MVP v1 tidak mencakup:

- Sistem pendaftaran mahasiswa.
- Multi-user academic enrollment.
- Student Information System.
- Sistem semester dan tahun ajaran.
- Sistem kalender akademik kompleks.
- Classroom management.
- Attendance tracking.
- Sistem dosen dan pengajar.
- Sistem transkrip akademik.
- Sistem pemberian gelar.
- Akreditasi institusi.
- Automatic Course Completion.
- Automatic Graduation.
- Automatic Faculty Promotion.
- Automatic Competency Graduation.
- Adaptive Curriculum Modification.
- Automatic Academic Organization Changes.

Fitur tersebut tidak boleh menjadi ketergantungan implementasi pipeline pembelajaran MVP.

---

21. Future Academic Development

Phase 1: Academic Catalog

Fokus:

- Faculty structure.
- Department structure.
- Study programs.
- Course and module definitions.
- Learning units.
- Competency mapping.

Status: Baseline untuk MVP v1.

Phase 2: Academic Operations

Potensi pengembangan:

- Academic learning plans.
- Activity scheduling.
- Course execution history.
- Learning progress records.
- Academic dashboards.

Phase 3: Assessment Integration

Potensi pengembangan:

- Assessment records.
- Competency evidence.
- Benchmark integration.
- Course assessment.
- Learning outcome evaluation.

Phase 4: Academic Progression

Potensi pengembangan:

- Faculty progression.
- Study program milestones.
- Competency aggregation.
- Advancement requirements.
- Academic completion rules.

Phase 5: Adaptive Academic System

Potensi pengembangan:

- Learning path recommendations.
- Weakness-based curriculum recommendations.
- Cross-domain optimization.
- Curriculum improvement proposals.
- Governed academic structure updates.

Setiap fase memerlukan spesifikasi dan keputusan pengembangan tersendiri.

Roadmap bukan berarti seluruh fitur tersebut sudah aktif.

---

22. Academic Integrity and Quality Requirements

Academic System harus memenuhi ketentuan berikut:

22.1 Structural Consistency

Setiap objek akademik harus memiliki hubungan yang valid dengan struktur induknya apabila hubungan tersebut diwajibkan.

22.2 Competency Alignment

Program dan materi pembelajaran harus memiliki hubungan yang jelas dengan kompetensi yang didukungnya.

22.3 No Artificial Complexity

Penambahan fakultas, departemen, course, atau module harus didasarkan pada kebutuhan organisasi pengetahuan.

Struktur tidak boleh diperumit hanya agar terlihat seperti universitas besar.

22.4 Cross-Domain Integrity

Materi lintas fakultas harus mempertahankan referensi ke kompetensi dan domain asal.

22.5 Historical Integrity

Perubahan katalog tidak boleh menghilangkan hubungan terhadap aktivitas dan hasil pembelajaran historis.

22.6 No False Academic Claims

Cognis tidak boleh mengklaim:

- Memiliki akreditasi resmi.
- Memberikan gelar yang diakui.
- Menjadi universitas resmi.
- Menghasilkan sertifikasi profesional.
- Memiliki keahlian profesional tertentu hanya karena menyelesaikan course internal.

22.7 Verifiable Learning

Penyelesaian materi dan aktivitas harus dibedakan dari penguasaan kompetensi.

Penguasaan hanya dapat dinyatakan berdasarkan bukti evaluasi yang sesuai.

---

23. MVP Acceptance Criteria

Academic System dinyatakan siap digunakan sebagai referensi MVP apabila:

1. Lima fakultas telah didefinisikan.
2. Foundational Academic Core telah didefinisikan.
3. Struktur departemen telah tersedia.
4. Program studi memiliki tujuan dan kompetensi yang relevan.
5. Struktur Course dan Module telah didefinisikan.
6. Learning Unit memiliki tujuan pembelajaran.
7. Learning Activity memiliki tipe dan ruang lingkup.
8. Interdisciplinary Programs dapat merepresentasikan hubungan lintas fakultas.
9. Academic ID mengikuti format yang konsisten.
10. Referensi akademik dapat divalidasi.
11. Academic metadata dapat dikaitkan dengan Learning Job jika relevan.
12. Perubahan katalog memiliki riwayat.
13. Academic System tidak mengambil alih fungsi Assessment Policy.
14. Academic System tidak menjalankan promosi otomatis.
15. Batas antara struktur akademik dan klaim akademik resmi telah ditetapkan.

Keberhasilan penyusunan katalog tidak membuktikan bahwa Cognis telah menguasai seluruh kompetensi di dalamnya.

Penguasaan kompetensi tetap harus dibuktikan melalui assessment.

---

24. Final Academic Principle

Academic System dibangun untuk mengorganisasi pengetahuan, bukan menciptakan kesan akademis semata.

Fakultas menjelaskan bidang keilmuan.

Departemen mengelompokkan kompetensi.

Program studi mengatur jalur pembelajaran.

Course dan module mengorganisasi materi.

Learning Unit menentukan tujuan yang spesifik.

Learning Activity menjalankan proses pembelajaran.

Setiap bagian harus memiliki fungsi yang jelas dan hubungan yang dapat ditelusuri.

Cognis harus mampu menghubungkan berbagai bidang pengetahuan tanpa kehilangan struktur dan konteksnya.

The purpose of an academic system is not to look like a university. It is to make learning structured, connected, measurable, and intellectually coherent.