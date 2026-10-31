COGNIS ACADEMY

Faculty Progression Policy

Document ID: CA-ACA-002
Version: 1.0.0
Status: Initial Specification
Project: Cognis AI
Subsystem: Cognis Academy
Language: Bahasa Indonesia

---

1. Purpose

Dokumen ini mengatur mekanisme perpindahan Cognis AI dari satu fakultas ke fakultas berikutnya.

Tujuannya adalah memastikan bahwa perpindahan tingkat akademik hanya terjadi ketika Cognis telah memenuhi persyaratan kompetensi dan memperoleh persetujuan eksplisit dari Founder.

Cognis diperbolehkan:

- Belajar secara mandiri.
- Melakukan penelitian.
- Mengerjakan latihan.
- Mengikuti evaluasi internal.
- Mengidentifikasi kelemahannya.
- Melakukan remedial.
- Mengusulkan kelulusan fakultas.

Namun, Cognis tidak memiliki kewenangan untuk menyetujui kelulusannya sendiri.

Prinsip utama: sistem boleh merekomendasikan kenaikan fakultas, tetapi hanya Founder yang dapat menyetujuinya.

2. Scope

Kebijakan ini berlaku untuk seluruh fakultas Cognis Academy:

1. Cognitive Foundations.
2. Economics & Monetary Systems.
3. Business & Finance.
4. Geopolitics & International Relations.
5. Financial Markets & Quantitative Analysis.

Kebijakan ini mengatur:

- Status akademik setiap fakultas.
- Persyaratan kelulusan.
- Evaluasi internal.
- Pengujian langsung oleh Founder.
- Persetujuan dan penolakan.
- Remedial dan pengujian ulang.
- Pembukaan fakultas berikutnya.
- Pencatatan keputusan akademik.
- Penanganan kondisi khusus.

Kebijakan ini tidak mengatur perubahan permanen pada kode, konfigurasi sistem, model, atau infrastruktur Cognis. Perubahan tersebut tetap tunduk pada prosedur Autonomous Learning System dan Security Governance.

3. Core Progression Principles

3.1 No Automatic Promotion

Tidak ada fakultas yang boleh terbuka secara otomatis hanya karena:

- Jadwal pembelajaran telah selesai.
- Seluruh materi telah dibaca.
- Jumlah latihan telah terpenuhi.
- Nilai evaluasi internal tinggi.
- Evaluator merekomendasikan kelulusan.
- Student Model menyatakan dirinya sudah menguasai materi.

Semua kondisi tersebut merupakan bukti pendukung, bukan persetujuan kelulusan.

3.2 Explicit Human Approval

Founder harus memberikan persetujuan secara eksplisit.

Sistem tidak boleh menafsirkan kalimat yang ambigu, respons singkat yang tidak jelas, atau ketidakaktifan Founder sebagai persetujuan.

Persetujuan hanya berlaku untuk fakultas yang sedang diajukan.

3.3 Competency-Based Progression

Kelulusan ditentukan berdasarkan kemampuan yang telah dibuktikan.

Cognis harus menunjukkan bahwa dirinya dapat:

- Memahami konsep.
- Menjelaskan konsep dengan benar.
- Menggunakan pengetahuan untuk menyelesaikan masalah.
- Menganalisis kasus yang berbeda dari contoh pembelajaran.
- Menilai kualitas bukti.
- Mengakui keterbatasan dan ketidakpastian.

3.4 Independent Evidence

Rekomendasi kelulusan harus didukung oleh bukti yang dapat diperiksa.

Sistem harus membedakan:

- Hasil belajar.
- Hasil latihan.
- Hasil evaluasi internal.
- Hasil benchmark.
- Hasil pengujian langsung oleh Founder.

Hasil dari masing-masing sumber tidak boleh dicampur seolah-olah memiliki tingkat independensi dan keandalan yang sama.

3.5 No Hidden Progression

Perubahan status akademik harus tercatat.

Sistem tidak boleh membuka fakultas berikutnya melalui proses tersembunyi, perubahan database tanpa audit, atau tindakan otomatis yang melewati persetujuan Founder.

4. Faculty State Machine

Setiap fakultas memiliki status akademik yang dikelola oleh Academic Progression Manager.

4.1 Available Status

Status| Deskripsi
LOCKED| Fakultas belum dapat dimulai karena prasyarat belum terpenuhi.
READY| Fakultas telah memenuhi prasyarat dan siap dimulai.
ACTIVE| Cognis sedang mempelajari materi fakultas.
INTERNAL_EVALUATION| Cognis sedang menjalani evaluasi internal.
REMEDIAL| Cognis sedang memperbaiki kompetensi yang belum memenuhi standar.
CANDIDATE_FOR_APPROVAL| Persyaratan internal terpenuhi dan laporan kelulusan telah disiapkan.
FOUNDER_REVIEW| Fakultas sedang dalam proses pengujian atau peninjauan Founder.
APPROVED| Founder telah menyetujui kelulusan fakultas.
REJECTED| Pengajuan kelulusan ditolak atau belum disetujui Founder.
ON_HOLD| Proses akademik ditahan karena kondisi tertentu.

4.2 Valid State Transitions

Transisi status yang diperbolehkan:

LOCKED
   |
   | Prasyarat terpenuhi
   v
READY
   |
   | Founder telah menyetujui fakultas sebelumnya
   | dan sistem mengaktifkan fakultas ini
   v
ACTIVE
   |
   | Materi pembelajaran memenuhi cakupan
   v
INTERNAL_EVALUATION
   |
   +---------------------------+
   |                           |
   | Belum memenuhi standar    | Memenuhi standar
   v                           v
REMEDIAL              CANDIDATE_FOR_APPROVAL
   |                           |
   | Evaluasi ulang            | Founder memulai peninjauan
   |                           v
   |                    FOUNDER_REVIEW
   |                           |
   |                  +--------+--------+
   |                  |                 |
   |                  |                 |
   |              Disetujui         Tidak disetujui
   |                  |                 |
   |                  v                 v
   |              APPROVED          REJECTED
   |                                    |
   +------------------------------------+
                    |
                    | Perbaikan dan pengajuan ulang
                    v
                REMEDIAL

"ON_HOLD" dapat digunakan untuk menahan aktivitas dari status yang relevan ketika terjadi kendala, seperti kegagalan evaluator, masalah sumber data, batas anggaran, atau masalah keamanan.

Setelah kendala diselesaikan, status dikembalikan ke tahap sebelumnya melalui transisi yang tercatat.

4.3 Invalid Transitions

Sistem wajib menolak transisi berikut:

- LOCKED langsung menjadi ACTIVE tanpa pemenuhan prasyarat.
- INTERNAL_EVALUATION langsung menjadi APPROVED.
- CANDIDATE_FOR_APPROVAL langsung menjadi APPROVED tanpa persetujuan Founder.
- REJECTED langsung menjadi fakultas berikutnya.
- ON_HOLD langsung menjadi APPROVED.
- Perubahan status yang tidak memiliki identitas proses atau catatan audit.

Setiap transisi harus melalui validasi aturan akademik.

5. Internal Graduation Requirements

Sebelum mengajukan kelulusan, Cognis harus menyelesaikan persyaratan internal.

5.1 Curriculum Coverage

Cognis harus mempelajari seluruh materi wajib yang ditentukan dalam kurikulum fakultas.

Sistem harus membedakan:

- Materi wajib.
- Materi pendukung.
- Materi pengayaan.
- Materi yang belum tersedia.
- Materi yang tidak dapat diselesaikan karena keterbatasan sumber.

Materi wajib yang belum dipelajari tidak boleh ditandai selesai hanya berdasarkan ringkasan atau klaim Student Model.

5.2 Competency Mastery

Setiap kompetensi wajib memiliki catatan penguasaan.

Catatan tersebut minimal mencakup:

- Competency ID.
- Nama kompetensi.
- Target penguasaan.
- Bukti pembelajaran.
- Bukti penerapan.
- Hasil evaluasi.
- Status penguasaan.
- Kelemahan yang ditemukan.

Penguasaan kompetensi tidak boleh ditentukan hanya dari jumlah dokumen yang sudah dibaca.

5.3 Internal Assessment

Cognis wajib menyelesaikan evaluasi internal sesuai "ASSESSMENT_POLICY.md".

Evaluasi sekurang-kurangnya mencakup:

1. Knowledge Assessment.
2. Reasoning Assessment.
3. Application Assessment.
4. Evidence Assessment.
5. Uncertainty Assessment.
6. Transfer Assessment.

5.4 Benchmark Completion

Cognis harus mengikuti benchmark yang relevan dengan fakultas aktif.

Benchmark harus mencakup soal yang belum pernah digunakan dalam latihan rutin.

Sistem wajib menyimpan:

- Versi benchmark.
- Tanggal pengujian.
- Soal atau identitas kasus.
- Jawaban Cognis.
- Rubrik penilaian.
- Hasil penilaian.
- Keterbatasan pengujian.

5.5 Critical Weakness Review

Sebelum rekomendasi kelulusan dikeluarkan, sistem harus memeriksa kelemahan kritis.

Contoh:

- Kesalahan logika berulang.
- Ketidakmampuan membedakan fakta dan asumsi.
- Kesimpulan yang tidak didukung bukti.
- Ketidakmampuan mengenali ketidakpastian.
- Kesalahan penerapan konsep dasar.
- Kecenderungan memberikan jawaban meyakinkan tanpa dasar.

Kelemahan kritis harus diperbaiki atau secara eksplisit dinyatakan sebagai batas kemampuan yang belum terselesaikan.

Sistem tidak boleh menyembunyikan kelemahan tersebut melalui rata-rata nilai yang tinggi.

6. Graduation Recommendation

Setelah seluruh persyaratan internal terpenuhi, Academic Progression Manager dapat menetapkan status:

"CANDIDATE_FOR_APPROVAL"

Status ini hanya berarti Cognis siap mengikuti peninjauan Founder.

Status tersebut bukan kelulusan.

6.1 Recommendation Report

Laporan kelulusan harus berisi:

A. Academic Identity

- Nama fakultas.
- Faculty ID.
- Periode pembelajaran.
- Versi kurikulum.
- Status akademik.

B. Learning Coverage

- Daftar materi yang diselesaikan.
- Materi yang belum diselesaikan.
- Kompetensi yang telah diuji.

C. Evaluation Results

- Hasil ujian.
- Hasil benchmark.
- Hasil studi kasus.
- Hasil pengujian penerapan.

D. Competency Analysis

- Kompetensi kuat.
- Kompetensi memadai.
- Kompetensi lemah.
- Kompetensi yang belum teruji.

E. Evidence Quality

- Sumber yang digunakan.
- Kualitas sumber.
- Bukti yang mendukung kesimpulan.
- Batasan dan ketidakpastian.

F. Remedial History

- Kelemahan yang pernah ditemukan.
- Tindakan perbaikan.
- Hasil pengujian ulang.

G. Graduation Recommendation

- Direkomendasikan lulus atau belum.
- Alasan rekomendasi.
- Risiko yang masih tersisa.
- Rekomendasi pengujian Founder.

6.2 No Self-Certification

Student Model boleh menjelaskan mengapa dirinya dianggap siap.

Namun, Student Model tidak boleh menjadi satu-satunya pihak yang menyatakan kelulusan.

Rekomendasi harus didukung hasil evaluasi dan bukti yang dapat diperiksa.

7. Direct Founder Examination

7.1 Examination Authority

Founder memiliki hak untuk menguji Cognis secara langsung setelah status fakultas mencapai "CANDIDATE_FOR_APPROVAL".

Pengujian dilakukan melalui antarmuka percakapan Cognis, termasuk Telegram apabila integrasi tersebut tersedia.

7.2 Founder Examination Methods

Founder dapat menggunakan metode pengujian berikut:

1. Conceptual Questioning

Menguji apakah Cognis benar-benar memahami konsep.

2. Critical Challenge

Mempertanyakan asumsi, kesimpulan, dan alasan yang digunakan Cognis.

3. Unseen Case

Memberikan persoalan baru yang tidak terdapat dalam materi latihan.

4. Evidence Challenge

Meminta sumber dan bukti untuk mendukung klaim.

5. Counterargument

Memberikan pandangan yang bertentangan untuk menguji konsistensi penalaran.

6. Practical Application

Meminta Cognis menerapkan pengetahuan pada situasi nyata atau simulasi.

7. Error Correction

Memberikan informasi yang salah atau argumen yang keliru untuk menguji kemampuan Cognis mengidentifikasi dan mengoreksinya.

Founder bebas menggabungkan berbagai metode tersebut.

7.3 Examination Session Record

Setiap sesi pengujian dapat disimpan sebagai Founder Examination Record.

Data minimal:

- Examination Session ID.
- Faculty ID.
- Waktu pengujian.
- Pertanyaan atau kasus yang diberikan.
- Jawaban Cognis.
- Catatan Founder.
- Kompetensi yang diuji.
- Hasil peninjauan.
- Rekomendasi tindak lanjut.

Sesi yang belum selesai tidak boleh dianggap sebagai bukti kelulusan final.

7.4 Founder Examination Independence

Pertanyaan Founder tidak harus berasal dari Teacher Model atau Benchmark Engine.

Founder dapat membuat pertanyaan sendiri.

Sistem harus mempertahankan identitas sumber pengujian agar dapat membedakan ujian internal dan pengujian langsung.

8. Founder Decision Policy

Setelah pengujian langsung, Founder dapat menentukan salah satu keputusan berikut.

8.1 APPROVE

Founder menyetujui kelulusan fakultas.

Konsekuensi:

1. Sistem memvalidasi bahwa fakultas sedang berada pada FOUNDER_REVIEW.
2. Keputusan disimpan secara permanen dalam audit log.
3. Status fakultas berubah menjadi APPROVED.
4. Fakultas berikutnya dapat berubah menjadi READY.
5. Academic Planner menyiapkan pembelajaran berikutnya.
6. Student Model dapat memulai fakultas berikutnya setelah aktivasi sistem.

Persetujuan hanya berlaku pada fakultas yang diajukan.

8.2 REQUEST_REMEDIAL

Founder menemukan kelemahan yang memerlukan perbaikan.

Konsekuensi:

1. Pengajuan kelulusan dihentikan.
2. Sistem mencatat alasan remedial.
3. Kompetensi terkait ditandai untuk diperbaiki.
4. Academic Planner menyusun rencana remedial.
5. Cognis kembali menjalani pembelajaran dan evaluasi yang diperlukan.

8.3 REQUEST_ADDITIONAL_TEST

Founder meminta pengujian tambahan sebelum mengambil keputusan.

Konsekuensi:

1. Pengajuan tetap terbuka.
2. Status berada dalam proses peninjauan.
3. Sistem menyiapkan pengujian tambahan.
4. Hasil pengujian ditambahkan ke laporan akademik.
5. Founder dapat mengambil keputusan setelah hasil tersedia.

8.4 REJECT

Founder menolak kelulusan berdasarkan hasil peninjauan.

Konsekuensi:

1. Keputusan penolakan dicatat.
2. Fakultas berikutnya tetap terkunci.
3. Sistem mencatat alasan penolakan.
4. Cognis tidak boleh menganggap dirinya lulus.
5. Pengajuan ulang hanya dapat dilakukan setelah tindak lanjut yang diperlukan.

8.5 HOLD

Founder menahan proses akademik untuk sementara.

Konsekuensi:

- Perpindahan fakultas dihentikan.
- Aktivitas terkait dapat dijeda.
- Status dan alasan penahanan dicatat.
- Proses baru dapat dilanjutkan setelah Founder memberikan instruksi yang jelas.

9. Approval Security

Persetujuan Founder merupakan tindakan yang memiliki konsekuensi langsung terhadap progres akademik.

Karena itu, implementasinya wajib memenuhi ketentuan berikut:

1. Persetujuan harus berasal dari akun Founder yang terautentikasi.
2. Pengguna lain tidak boleh menyetujui kelulusan.
3. Pesan dari sumber yang tidak terverifikasi harus ditolak.
4. Pesan ambigu tidak boleh diinterpretasikan sebagai persetujuan.
5. Persetujuan harus terikat pada Faculty ID dan pengajuan yang sedang aktif.
6. Pengajuan yang sudah diputuskan tidak boleh disetujui ulang menggunakan token atau perintah lama.
7. Keputusan harus dicatat dalam audit log.
8. Kegagalan autentikasi harus menghentikan proses persetujuan.
9. Sistem tidak boleh mengandalkan kecocokan teks semata tanpa pemeriksaan identitas dan konteks.
10. Status akademik tidak boleh diubah melalui akses tidak sah ke endpoint atau database.

Persetujuan akademik harus menggunakan mekanisme otorisasi yang ditentukan dalam "SECURITY_GOVERNANCE.md".

10. Reassessment and Remedial Policy

Remedial ditujukan untuk memperbaiki kelemahan yang ditemukan.

10.1 Targeted Remedial

Sistem harus menentukan kompetensi yang memerlukan perbaikan.

Contoh:

Jika Cognis lemah dalam causal reasoning, sistem memprioritaskan:

- Identifikasi variabel.
- Hubungan sebab dan akibat.
- Confounding variables.
- Counterfactual reasoning.
- Evaluasi bukti kausal.

Sistem tidak harus mengulang seluruh materi logika jika kompetensi tersebut telah terbukti memadai.

10.2 Reassessment

Setelah remedial selesai, Cognis wajib mengikuti pengujian ulang.

Soal pengujian harus cukup berbeda dari materi latihan agar hasilnya menunjukkan kemampuan penerapan, bukan sekadar hafalan jawaban.

10.3 Repeated Failure

Jika Cognis terus gagal pada kompetensi yang sama, sistem harus:

1. Menganalisis pola kegagalan.
2. Memeriksa kualitas materi pembelajaran.
3. Memeriksa kesesuaian Teacher Model.
4. Mengevaluasi kualitas soal.
5. Memeriksa keterbatasan Student Model.
6. Mengusulkan perubahan metode pembelajaran.
7. Meminta persetujuan jika perubahan tersebut termasuk perubahan sistem permanen.

Sistem tidak boleh mengubah standar kelulusan secara diam-diam agar Cognis terlihat berhasil.

11. Faculty Access Control

Academic Progression Manager wajib mengontrol akses pembelajaran berdasarkan status fakultas.

Aturan:

- Hanya satu fakultas utama yang berstatus ACTIVE pada satu waktu.
- Fakultas berikutnya tetap LOCKED atau READY sampai proses aktivasi yang sah.
- Materi fakultas berikutnya tidak boleh menjadi kurikulum utama sebelum persetujuan Founder.
- Pengetahuan fakultas terdahulu tetap dapat diakses.
- Pengujian lintas fakultas boleh dilakukan untuk menguji retensi dan integrasi pengetahuan.
- Pengujian lintas fakultas tidak dianggap sebagai perpindahan status akademik.

Sistem boleh melakukan penelitian pengayaan yang berkaitan dengan fakultas berikutnya apabila diperlukan untuk memahami persoalan lintas disiplin.

Namun, penelitian pengayaan tersebut tidak boleh dianggap sebagai pembelajaran resmi fakultas berikutnya atau digunakan untuk melewati gerbang akademik.

12. Special Cases

12.1 Missing Evaluation Data

Jika data evaluasi tidak lengkap, sistem tidak boleh mengasumsikan hasil yang hilang sebagai nilai lulus.

Status kelulusan harus ditahan sampai data yang diperlukan tersedia atau kekurangan tersebut ditangani melalui keputusan yang tercatat.

12.2 Evaluator Failure

Jika evaluator mengalami gangguan:

- Evaluasi ditandai gagal atau tertunda.
- Hasil yang tidak valid tidak boleh digunakan.
- Sistem mencoba kembali sesuai batas retry.
- Jika kegagalan berlanjut, proses masuk ON_HOLD.

12.3 Benchmark Contamination

Jika ditemukan bahwa Student Model sudah terpapar jawaban benchmark tertutup:

- Benchmark terkait ditandai terkontaminasi.
- Hasilnya tidak boleh diperlakukan sebagai pengujian independen.
- Benchmark alternatif harus disiapkan.
- Laporan harus menyebutkan keterbatasan tersebut.

12.4 Model or System Change

Jika terjadi pergantian model, konfigurasi, prompt inti, atau perubahan sistem yang signifikan selama evaluasi:

- Sistem harus mencatat versi sebelum dan sesudah perubahan.
- Hasil evaluasi dari konfigurasi berbeda tidak boleh dicampur tanpa penjelasan.
- Evaluasi yang terdampak harus ditinjau kembali.
- Perubahan permanen tetap mengikuti tata kelola ALS.

12.5 Founder Unavailability

Jika Founder belum memberikan keputusan:

- Status tetap menunggu peninjauan.
- Fakultas berikutnya tetap terkunci.
- Sistem boleh melanjutkan pekerjaan administrasi yang tidak mengubah status kelulusan.
- Sistem tidak boleh menganggap tidak adanya respons sebagai persetujuan.

13. Audit and Academic History

Setiap keputusan harus memiliki rekaman audit yang tidak dapat diubah secara diam-diam.

Informasi minimal:

- Decision ID.
- Faculty ID.
- Previous Status.
- New Status.
- Decision Type.
- Founder Identity.
- Decision Timestamp.
- Reason or Notes.
- Related Evaluation IDs.
- Related Report ID.
- Curriculum Version.
- Model Configuration Reference.

Jika terjadi koreksi administratif, sistem harus membuat catatan koreksi baru dan tetap mempertahankan riwayat sebelumnya.

Audit log harus cukup untuk merekonstruksi alasan dan urutan perpindahan status akademik.

14. Acceptance Criteria

Implementasi kebijakan ini dianggap berhasil apabila:

1. Fakultas berikutnya tidak dapat aktif tanpa persetujuan Founder.
2. Sistem dapat memeriksa persyaratan kelulusan internal.
3. Sistem dapat menghasilkan rekomendasi kelulusan.
4. Founder dapat menguji Cognis secara langsung.
5. Sesi pengujian dapat dicatat.
6. Founder dapat menyetujui, menolak, meminta remedial, meminta pengujian tambahan, atau menahan proses.
7. Keputusan yang ambigu tidak memicu perpindahan fakultas.
8. Pengguna yang tidak memiliki otorisasi tidak dapat menyetujui kelulusan.
9. Remedial hanya berfokus pada kompetensi yang perlu diperbaiki.
10. Fakultas berikutnya tetap terkunci ketika keputusan belum tersedia.
11. Semua perubahan status dapat diaudit.
12. Sistem dapat membedakan persetujuan akademik dari persetujuan perubahan sistem permanen.
13. Kegagalan evaluator atau benchmark tidak menghasilkan kelulusan palsu.
14. Riwayat kelulusan fakultas terdahulu tetap tersedia.

15. Implementation Dependencies

Dokumen ini harus diimplementasikan secara konsisten dengan:

- "docs/academy/ACADEMIC_SYSTEM.md"
- "docs/academy/ASSESSMENT_POLICY.md"
- "docs/academy/LEARNING_SCHEDULE.md"
- "docs/autonomous-learning/COMPETENCY_CURRICULUM.md"
- "docs/autonomous-learning/EVALUATION_FRAMEWORK.md"
- "docs/autonomous-learning/AUTONOMOUS_LEARNING_SPEC.md"
- "docs/governance/SECURITY_GOVERNANCE.md"
- "docs/technical/DATABASE_SCHEMA.md"
- "docs/technical/API_CONTRACTS.md"

Jika ditemukan konflik kebijakan, implementasi tidak boleh memilih salah satu secara diam-diam.

Konflik harus dicatat, dianalisis, dan diselesaikan melalui revisi dokumentasi yang sesuai sebelum implementasi terkait dilakukan.

16. Final Policy

Cognis Academy menerapkan sistem kenaikan fakultas berbasis kompetensi dan validasi manusia.

Cognis bertanggung jawab untuk belajar, berlatih, menguji kemampuan, menemukan kelemahan, dan mempersiapkan bukti pencapaiannya.

Academic Progression Manager bertanggung jawab memastikan seluruh persyaratan dan alur status dijalankan dengan benar.

Founder bertanggung jawab memberikan keputusan akhir atas kelulusan fakultas.

Tidak ada kenaikan tingkat otomatis.

Tidak ada kelulusan berdasarkan klaim sepihak.

Tidak ada persetujuan berdasarkan asumsi.

Cognis may learn independently, but it cannot promote itself.

Only the Founder can authorize faculty progression.

---

End of Document