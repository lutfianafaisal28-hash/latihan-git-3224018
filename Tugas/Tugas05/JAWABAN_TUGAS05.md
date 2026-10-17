# JAWABAN TUGAS 05 — Black-box Testing (Equivalence Partitioning & Boundary Value Analysis)

Nama: Lutfiana Faisal Patah | NIM: 3224018 | Kelas: Sistem Informasi
Mata Kuliah: Implementasi Pengujian Perangkat Lunak — Pertemuan 5

Sumber soal: `LATIHAN TERSTRUKTUR-Materi-5.pdf` · Dokumen resmi pengumpulan: [`Jawaban_Latihan_Black_Box_Testing_Materi_5.docx`](./Jawaban_Latihan_Black_Box_Testing_Materi_5.docx)

---

| Identitas | Diisi oleh mahasiswa |
|---|---|
| Nama | ................................................................ |
| NIM | ................................................................ |
| Kelas | ................................................................ |

> Catatan pengerjaan: jawaban disusun berdasarkan spesifikasi pada file Latihan Terstruktur Materi 5. Untuk contoh tanggal yang membutuhkan acuan waktu, tanggal pengujian diasumsikan 16 Oktober 2026. Jika tugas dikumpulkan atau diuji pada tanggal lain, sesuaikan tanggal tersebut.

## Ringkasan Materi

- Black-box Testing adalah pengujian fungsi perangkat lunak dari sisi input dan output tanpa perlu mengetahui struktur internal kode program.

- Equivalence Partitioning (EP) membagi domain input ke dalam kelas-kelas yang dianggap memiliki perilaku serupa. Penguji memilih nilai perwakilan dari setiap kelas valid dan invalid.

- Boundary Value Analysis (BVA) menguji nilai di sekitar batas minimum dan maksimum. Untuk rentang min sampai max, nilai yang umum diuji adalah min-1, min, min+1, max-1, max, dan max+1.

- Expected output adalah hasil yang seharusnya diberikan sistem. Hasil aktual baru diisi setelah pengujian benar-benar dijalankan.

## BAGIAN A — EQUIVALENCE PARTITIONING

### Soal 1. Form Login

Spesifikasi: username 5–20 karakter dan hanya huruf/angka; password minimal 8 karakter serta mengandung huruf besar, huruf kecil, dan angka; umur 17–100 tahun.

| Field | Partisi | Kategori | Range/Kondisi | Test Case | Expected Output |
|---|---|---|---|---|---|
| Username | P1 | Valid | 5–20 karakter, hanya huruf dan angka | alvin123 | Username diterima |
| Username | P2 | Invalid | Kosong atau kurang dari 5 karakter | abc | Pesan username minimal 5 karakter |
| Username | P3 | Invalid | Lebih dari 20 karakter | alvin123456789012345 | Pesan username maksimal 20 karakter |
| Username | P4 | Invalid | Mengandung spasi/simbol/tanda baca | alvin_123 | Pesan username hanya boleh huruf dan angka |
| Password | P1 | Valid | Minimal 8 karakter, ada huruf besar, huruf kecil, angka | Alvin1234 | Password memenuhi ketentuan |
| Password | P2 | Invalid | Kurang dari 8 karakter | Alv123 | Pesan password minimal 8 karakter |
| Password | P3 | Invalid | Tidak memiliki huruf besar | alvin1234 | Pesan password harus mengandung huruf besar |
| Password | P4 | Invalid | Tidak memiliki huruf kecil | ALVIN1234 | Pesan password harus mengandung huruf kecil |
| Password | P5 | Invalid | Tidak memiliki angka | AlvinAbcd | Pesan password harus mengandung angka |
| Umur | P1 | Invalid | Kurang dari 17 tahun | 16 | Pesan umur minimal 17 tahun |
| Umur | P2 | Valid | 17–100 tahun | 22 | Umur diterima |
| Umur | P3 | Invalid | Lebih dari 100 tahun | 101 | Pesan umur maksimal 100 tahun |
| Umur | P4 | Invalid | Bukan angka atau kosong | abc | Pesan umur harus berupa angka |

### Soal 2. Form Pemesanan Tiket

Spesifikasi: jumlah tiket 1–10; kode promo opsional dan jika diisi panjangnya 5–10 karakter; tanggal keberangkatan berformat YYYY-MM-DD dan minimal hari ini.

| Field | Partisi | Kategori | Range/Kondisi | Test Case | Expected Output |
|---|---|---|---|---|---|
| Jumlah tiket | P1 | Valid | 1–10, bilangan bulat | 3 | Jumlah tiket diterima |
| Jumlah tiket | P2 | Invalid | Kurang dari 1 | 0 | Pesan jumlah tiket minimal 1 |
| Jumlah tiket | P3 | Invalid | Lebih dari 10 | 11 | Pesan jumlah tiket maksimal 10 |
| Jumlah tiket | P4 | Invalid | Bukan bilangan bulat/kosong | 2.5 | Pesan jumlah tiket harus bilangan bulat |
| Kode promo | P1 | Valid | Kosong karena opsional | (kosong) | Pemesanan tetap dapat dilanjutkan tanpa promo |
| Kode promo | P2 | Valid | 5–10 karakter | HEMAT25 | Kode promo diterima/diperiksa |
| Kode promo | P3 | Invalid | Diisi tetapi kurang dari 5 karakter | ABC | Pesan kode promo minimal 5 karakter |
| Kode promo | P4 | Invalid | Lebih dari 10 karakter | PROMOHEMAT2026 | Pesan kode promo maksimal 10 karakter |
| Tanggal keberangkatan | P1 | Valid | Format benar dan hari ini/masa depan | 2026-10-16 | Tanggal diterima |
| Tanggal keberangkatan | P2 | Invalid | Tanggal sebelum hari ini | 2026-10-15 | Pesan tanggal tidak boleh sebelum hari ini |
| Tanggal keberangkatan | P3 | Invalid | Format tidak sesuai YYYY-MM-DD | 16-10-2026 | Pesan format tanggal tidak valid |
| Tanggal keberangkatan | P4 | Invalid | Tanggal kalender tidak valid | 2026-02-30 | Pesan tanggal tidak valid |
| Tanggal keberangkatan | P5 | Invalid | Kosong | (kosong) | Pesan tanggal keberangkatan wajib diisi |

## BAGIAN B — BOUNDARY VALUE ANALYSIS

### Soal 3. Form Pendaftaran Mahasiswa

Nilai batas diuji menggunakan enam nilai: min-1, min, min+1, max-1, max, dan max+1.

| Field | Boundary | Nilai | Kategori | Expected Output |
|---|---|---|---|---|
| Nilai Ujian | min-1 | -1 | Invalid | Pesan nilai di luar rentang |
| Nilai Ujian | min | 0 | Valid | Data diterima |
| Nilai Ujian | min+1 | 1 | Valid | Data diterima |
| Nilai Ujian | max-1 | 99 | Valid | Data diterima |
| Nilai Ujian | max | 100 | Valid | Data diterima |
| Nilai Ujian | max+1 | 101 | Invalid | Pesan nilai di luar rentang |
| IPK | min-1 | -0.1 | Invalid | Pesan nilai di luar rentang |
| IPK | min | 0.0 | Valid | Data diterima |
| IPK | min+1 | 0.1 | Valid | Data diterima |
| IPK | max-1 | 3.9 | Valid | Data diterima |
| IPK | max | 4.0 | Valid | Data diterima |
| IPK | max+1 | 4.1 | Invalid | Pesan nilai di luar rentang |
| Semester | min-1 | 0 | Invalid | Pesan nilai di luar rentang |
| Semester | min | 1 | Valid | Data diterima |
| Semester | min+1 | 2 | Valid | Data diterima |
| Semester | max-1 | 13 | Valid | Data diterima |
| Semester | max | 14 | Valid | Data diterima |
| Semester | max+1 | 15 | Invalid | Pesan nilai di luar rentang |

### Soal 4. Form Transfer Bank

Rentang nominal transfer adalah Rp10.000–Rp100.000.000. Biaya admin Rp2.500 bersifat tetap. Saldo minimal Rp50.000. Untuk expected output, diasumsikan saldo rekening mencukupi nominal transfer + biaya admin dan setelah transfer saldo tersisa minimal Rp50.000; jika syarat saldo tidak terpenuhi, transaksi seharusnya ditolak.

| Field | Boundary | Nilai | Kategori | Expected Output |
|---|---|---|---|---|
| Nominal transfer | min-1 | Rp9.999 | Invalid | Transfer ditolak; nominal minimal Rp10.000 |
| Nominal transfer | min | Rp10.000 | Valid* | Nominal diterima jika saldo mencukupi |
| Nominal transfer | min+1 | Rp10.001 | Valid* | Nominal diterima jika saldo mencukupi |
| Nominal transfer | max-1 | Rp99.999.999 | Valid* | Nominal diterima jika saldo mencukupi |
| Nominal transfer | max | Rp100.000.000 | Valid* | Nominal diterima jika saldo mencukupi |
| Nominal transfer | max+1 | Rp100.000.001 | Invalid | Transfer ditolak; nominal maksimal Rp100.000.000 |

*Valid pada tabel berarti nominal berada dalam rentang yang diperbolehkan. Validasi saldo tetap harus dilakukan secara terpisah, termasuk biaya admin Rp2.500 dan saldo minimum Rp50.000.*

## BAGIAN C — KOMBINASI EP & BVA

### Soal 5. Form Registrasi Akun

Spesifikasi: nama 3–50 karakter; username 5–20 karakter, huruf/angka dan tidak diawali angka; email valid; password minimal 8 karakter dengan huruf besar, huruf kecil, dan angka; umur 17–100; nomor telepon 10–13 digit dan diawali 08.

#### A. Equivalence Partitioning

| Field | Kategori | Kondisi/Partisi | Contoh Test Case | Expected Output |
|---|---|---|---|---|
| Nama lengkap | Valid | 3–50 karakter | Alvin Pratama | Nama diterima |
| Nama lengkap | Invalid | Kosong | (kosong) | Nama wajib diisi |
| Nama lengkap | Invalid | Kurang dari 3 karakter | Al | Nama minimal 3 karakter |
| Nama lengkap | Invalid | Lebih dari 50 karakter | Nama sepanjang 51 karakter | Nama maksimal 50 karakter |
| Username | Valid | 5–20 karakter, huruf/angka, karakter pertama huruf | alvin123 | Username diterima |
| Username | Invalid | Kurang dari 5 karakter | ali1 | Username minimal 5 karakter |
| Username | Invalid | Lebih dari 20 karakter | alvin123456789012345 | Username maksimal 20 karakter |
| Username | Invalid | Diawali angka | 1alvin | Username tidak boleh diawali angka |
| Username | Invalid | Mengandung simbol/spasi | alvin_123 | Username hanya boleh huruf dan angka |
| Email | Valid | Format email benar | alvin@example.com | Email diterima |
| Email | Invalid | Tidak memiliki @ | alvinexample.com | Format email tidak valid |
| Email | Invalid | Tidak memiliki domain setelah @ | alvin@ | Format email tidak valid |
| Email | Invalid | Kosong | (kosong) | Email wajib diisi |
| Password | Valid | Minimal 8 karakter, huruf besar/kecil dan angka | Alvin1234 | Password diterima |
| Password | Invalid | Kurang dari 8 karakter | Alv123 | Password minimal 8 karakter |
| Password | Invalid | Tidak ada huruf besar | alvin1234 | Password harus mengandung huruf besar |
| Password | Invalid | Tidak ada huruf kecil | ALVIN1234 | Password harus mengandung huruf kecil |
| Password | Invalid | Tidak ada angka | Alvinabcd | Password harus mengandung angka |
| Umur | Valid | 17–100 tahun | 22 | Umur diterima |
| Umur | Invalid | Kurang dari 17 tahun | 16 | Umur minimal 17 tahun |
| Umur | Invalid | Lebih dari 100 tahun | 101 | Umur maksimal 100 tahun |
| No. telepon | Valid | 10–13 digit dan diawali 08 | 081234567890 | Nomor telepon diterima |
| No. telepon | Invalid | Kurang dari 10 digit | 081234567 | Nomor telepon minimal 10 digit |
| No. telepon | Invalid | Lebih dari 13 digit | 0812345678901234 | Nomor telepon maksimal 13 digit |
| No. telepon | Invalid | Tidak diawali 08 | 02123456789 | Nomor telepon harus diawali 08 |
| No. telepon | Invalid | Mengandung huruf/simbol | 08123AB789 | Nomor telepon hanya boleh berisi digit |

#### B. Boundary Value Analysis

| Field | Boundary | Nilai | Kategori | Expected Output |
|---|---|---|---|---|
| Nama lengkap | min-1 | 2 karakter | Invalid | Ditolak karena di luar batas |
| Nama lengkap | min | 3 karakter | Valid | Diterima |
| Nama lengkap | min+1 | 4 karakter | Valid | Diterima |
| Nama lengkap | max-1 | 49 karakter | Valid | Diterima |
| Nama lengkap | max | 50 karakter | Valid | Diterima |
| Nama lengkap | max+1 | 51 karakter | Invalid | Ditolak karena di luar batas |
| Username | min-1 | 4 karakter | Invalid | Ditolak karena di luar batas |
| Username | min | 5 karakter | Valid | Diterima |
| Username | min+1 | 6 karakter | Valid | Diterima |
| Username | max-1 | 19 karakter | Valid | Diterima |
| Username | max | 20 karakter | Valid | Diterima |
| Username | max+1 | 21 karakter | Invalid | Ditolak karena di luar batas |
| Password | min-1 | 7 karakter | Invalid | Ditolak karena di luar batas |
| Password | min | 8 karakter | Valid* | Diterima jika aturan format/karakter juga terpenuhi |
| Password | min+1 | 9 karakter | Valid* | Diterima jika aturan format/karakter juga terpenuhi |
| Umur | min-1 | 16 tahun | Invalid | Ditolak karena di luar batas |
| Umur | min | 17 tahun | Valid | Diterima |
| Umur | min+1 | 18 tahun | Valid | Diterima |
| Umur | max-1 | 99 tahun | Valid | Diterima |
| Umur | max | 100 tahun | Valid | Diterima |
| Umur | max+1 | 101 tahun | Invalid | Ditolak karena di luar batas |
| No. telepon | min-1 | 9 digit | Invalid | Ditolak karena di luar batas |
| No. telepon | min | 10 digit | Valid* | Diterima jika aturan format/karakter juga terpenuhi |
| No. telepon | min+1 | 11 digit | Valid* | Diterima jika aturan format/karakter juga terpenuhi |
| No. telepon | max-1 | 12 digit | Valid* | Diterima jika aturan format/karakter juga terpenuhi |
| No. telepon | max | 13 digit | Valid* | Diterima jika aturan format/karakter juga terpenuhi |
| No. telepon | max+1 | 14 digit | Invalid | Ditolak karena di luar batas |

*Untuk password, panjang 8 atau 9 karakter hanya valid jika juga mengandung huruf besar, huruf kecil, dan angka. Untuk nomor telepon, nilai panjang valid tetap harus diawali 08 dan seluruh karakter berupa digit.*

#### C. Test Case Gabungan (lebih dari 20 test case)

| ID | Skenario | Input | Expected Output |
|---|---|---|---|
| TC-01 | Semua data valid | Nama Alvin Pratama; username alvin123; email alvin@example.com; password Alvin1234; umur 22; telepon 081234567890 | Registrasi berhasil |
| TC-02 | Nama kosong | Nama kosong, field lain valid | Nama wajib diisi |
| TC-03 | Nama terlalu pendek | Nama: Al | Nama minimal 3 karakter |
| TC-04 | Nama 51 karakter | Nama berisi 51 karakter | Nama maksimal 50 karakter |
| TC-05 | Username kurang dari 5 | Username: ali1 | Username minimal 5 karakter |
| TC-06 | Username 5 karakter | Username: alvin | Username diterima jika aturan lain terpenuhi |
| TC-07 | Username 21 karakter | Username berisi 21 karakter | Username maksimal 20 karakter |
| TC-08 | Username diawali angka | Username: 1alvin | Username tidak boleh diawali angka |
| TC-09 | Username mengandung simbol | Username: alvin_1 | Username hanya boleh huruf dan angka |
| TC-10 | Email tanpa @ | Email: alvinexample.com | Format email tidak valid |
| TC-11 | Email tanpa domain | Email: alvin@ | Format email tidak valid |
| TC-12 | Password 7 karakter | Password: Alvin12 | Password minimal 8 karakter |
| TC-13 | Password tanpa huruf besar | Password: alvin1234 | Password harus mengandung huruf besar |
| TC-14 | Password tanpa huruf kecil | Password: ALVIN1234 | Password harus mengandung huruf kecil |
| TC-15 | Password tanpa angka | Password: Alvinabcd | Password harus mengandung angka |
| TC-16 | Umur 16 | Umur: 16 | Umur minimal 17 tahun |
| TC-17 | Umur 17 | Umur: 17 | Umur diterima |
| TC-18 | Umur 100 | Umur: 100 | Umur diterima |
| TC-19 | Umur 101 | Umur: 101 | Umur maksimal 100 tahun |
| TC-20 | Telepon 9 digit | Telepon: 081234567 | Nomor telepon minimal 10 digit |
| TC-21 | Telepon 10 digit valid | Telepon: 0812345678 | Nomor telepon diterima |
| TC-22 | Telepon 13 digit valid | Telepon: 0812345678901 | Nomor telepon diterima |
| TC-23 | Telepon 14 digit | Telepon: 08123456789012 | Nomor telepon maksimal 13 digit |
| TC-24 | Telepon tidak diawali 08 | Telepon: 02123456789 | Nomor telepon harus diawali 08 |
| TC-25 | Telepon mengandung huruf | Telepon: 08123AB789 | Nomor telepon hanya boleh berisi digit |

## BAGIAN D — API TESTING

### Soal 6. POST /api/v1/products

Spesifikasi API: name berupa string 3–100 karakter; price angka 1.000–10.000.000; stock bilangan bulat 0–1.000; category salah satu dari electronics, clothing, food. Response: 201 Created jika berhasil, 400 Bad Request jika validasi gagal, dan 401 Unauthorized jika token tidak valid.

| No | Test Case | Request Body | Expected Status | Expected Response |
|---|---|---|---|---|
| TC-01 | Valid request | {"name":"Keyboard","price":250000,"stock":20,"category":"electronics"} | 201 Created | Product berhasil dibuat; response berisi data/ID produk |
| TC-02 | Name kurang dari 3 karakter | {"name":"TV","price":250000,"stock":20,"category":"electronics"} | 400 Bad Request | Validasi gagal; name harus 3–100 karakter |
| TC-03 | Price di bawah minimum | {"name":"Keyboard","price":500,"stock":20,"category":"electronics"} | 400 Bad Request | Validasi gagal; price minimal 1000 |
| TC-04 | Stock di atas maksimum | {"name":"Keyboard","price":250000,"stock":1001,"category":"electronics"} | 400 Bad Request | Validasi gagal; stock maksimal 1000 |
| TC-05 | Category tidak valid | {"name":"Keyboard","price":250000,"stock":20,"category":"furniture"} | 400 Bad Request | Validasi gagal; category harus electronics, clothing, atau food |
| TC-06 | Unauthorized | Request body valid; token tidak dikirim atau tidak valid | 401 Unauthorized | Akses ditolak karena token tidak valid |
| TC-07 | Price di batas minimum | {"name":"Roti","price":1000,"stock":0,"category":"food"} | 201 Created | Produk berhasil dibuat jika token valid |
| TC-08 | Name lebih dari 100 karakter | {"name":"ProdukUjiCobaDenganNamaSangatPanjangUntukMengujiBatasMaksimalSeratusKarakterAAAAAAAAAAAAAAAAAAAAAAAAA","price":250000,"stock":20,"category":"electronics"} | 400 Bad Request | Validasi gagal; name maksimal 100 karakter |
| TC-09 | Stock negatif | {"name":"Kaos","price":100000,"stock":-1,"category":"clothing"} | 400 Bad Request | Validasi gagal; stock minimal 0 |

Catatan: untuk TC-06, body bisa tetap valid seperti TC-01, tetapi header Authorization tidak disertakan atau menggunakan token tidak valid. Status 401 berasal dari aturan spesifikasi soal.

## BAGIAN E — STUDI KASUS TERPADU (BONUS)

### Soal 7. Form Pendaftaran Online

Spesifikasi: nama 3–100 karakter; email valid; nomor HP 10–13 digit dan diawali 08; tanggal lahir format YYYY-MM-DD serta umur minimal 17 tahun; password minimal 8 karakter dengan huruf besar, huruf kecil, angka, dan simbol; konfirmasi password harus sama dengan password.

Asumsi tanggal pengujian adalah 16 Oktober 2026. Dengan acuan ini, tanggal lahir 2009-10-16 tepat berusia 17 tahun, sedangkan 2009-10-17 belum berusia 17 tahun pada tanggal pengujian.

#### A. Equivalence Partitioning

| Field | Kategori | Kondisi/Partisi | Contoh Test Case | Expected Output |
|---|---|---|---|---|
| Nama | Valid | 3–100 karakter | Alvin Pratama | Nama diterima |
| Nama | Invalid | Kosong/kurang dari 3 karakter | Al | Nama minimal 3 karakter |
| Nama | Invalid | Lebih dari 100 karakter | Nama 101 karakter | Nama maksimal 100 karakter |
| Email | Valid | Format benar | alvin@example.com | Email diterima |
| Email | Invalid | Tanpa @ / tanpa domain | alvinexample.com | Format email tidak valid |
| No. HP | Valid | 10–13 digit, diawali 08 | 081234567890 | Nomor HP diterima |
| No. HP | Invalid | Kurang dari 10 atau lebih dari 13 digit | 081234567 | Panjang nomor HP tidak valid |
| No. HP | Invalid | Tidak diawali 08 atau berisi huruf | 02123456789 | Nomor HP tidak valid |
| Tanggal lahir | Valid | Tanggal valid dan umur ≥17 | 2000-05-10 | Tanggal lahir diterima |
| Tanggal lahir | Invalid | Umur <17 tahun | 2012-05-10 | Umur minimal 17 tahun |
| Tanggal lahir | Invalid | Format/tanggal tidak valid | 10-05-2000 | Format tanggal tidak valid |
| Password | Valid | ≥8 karakter; besar, kecil, angka, simbol | Alvin123! | Password diterima |
| Password | Invalid | Kurang dari 8 karakter | Alv1! | Password minimal 8 karakter |
| Password | Invalid | Tidak memenuhi salah satu komponen | Alvin1234 | Password harus mengandung simbol |
| Konfirmasi password | Valid | Sama dengan password | Alvin123! | Konfirmasi cocok |
| Konfirmasi password | Invalid | Berbeda dengan password | Alvin123? | Konfirmasi password tidak sama |

#### B. Boundary Value Analysis

| Field | Boundary | Nilai | Kategori | Expected Output |
|---|---|---|---|---|
| Nama | min-1 | 2 karakter | Invalid | Ditolak; nama minimal 3 karakter |
| Nama | min | 3 karakter | Valid | Diterima |
| Nama | min+1 | 4 karakter | Valid | Diterima |
| Nama | max-1 | 99 karakter | Valid | Diterima |
| Nama | max | 100 karakter | Valid | Diterima |
| Nama | max+1 | 101 karakter | Invalid | Ditolak; nama maksimal 100 karakter |
| No. HP | min-1 | 9 digit | Invalid | Ditolak; minimal 10 digit |
| No. HP | min | 10 digit | Valid* | Diterima jika diawali 08 |
| No. HP | min+1 | 11 digit | Valid* | Diterima jika diawali 08 |
| No. HP | max-1 | 12 digit | Valid* | Diterima jika diawali 08 |
| No. HP | max | 13 digit | Valid* | Diterima jika diawali 08 |
| No. HP | max+1 | 14 digit | Invalid | Ditolak; maksimal 13 digit |
| Password | min-1 | 7 karakter | Invalid | Ditolak; minimal 8 karakter |
| Password | min | 8 karakter | Valid* | Diterima jika memiliki huruf besar, kecil, angka, simbol |
| Password | min+1 | 9 karakter | Valid* | Diterima jika seluruh syarat terpenuhi |
| Tanggal lahir | batas usia | 2009-10-16 (17 tahun) | Valid | Tanggal lahir diterima |
| Tanggal lahir | 1 hari lebih muda | 2009-10-17 (belum 17 tahun) | Invalid | Ditolak; umur minimal 17 tahun |

*Nilai batas panjang tidak otomatis valid apabila aturan format lain tidak dipenuhi.*

#### C. Test Case Lengkap (25 Test Case)

| ID | Skenario | Input | Expected Output |
|---|---|---|---|
| TC-01 | Semua data valid | Nama Alvin Pratama; alvin@example.com; HP 081234567890; lahir 2000-05-10; password Alvin123!; konfirmasi sama | Pendaftaran berhasil |
| TC-02 | Nama 2 karakter | Nama: Al; field lain valid | Nama minimal 3 karakter |
| TC-03 | Nama 3 karakter | Nama: Ali; field lain valid | Nama diterima |
| TC-04 | Nama 101 karakter | Nama berisi 101 karakter | Nama maksimal 100 karakter |
| TC-05 | Email valid | alvin@example.com | Email diterima |
| TC-06 | Email tanpa @ | alvinexample.com | Format email tidak valid |
| TC-07 | Email tanpa domain | alvin@ | Format email tidak valid |
| TC-08 | HP 9 digit | 081234567 | Nomor HP minimal 10 digit |
| TC-09 | HP 10 digit diawali 08 | 0812345678 | Nomor HP diterima |
| TC-10 | HP 13 digit diawali 08 | 0812345678901 | Nomor HP diterima |
| TC-11 | HP 14 digit | 08123456789012 | Nomor HP maksimal 13 digit |
| TC-12 | HP tidak diawali 08 | 02123456789 | Nomor HP harus diawali 08 |
| TC-13 | HP berisi huruf | 08123AB789 | Nomor HP hanya boleh berisi digit |
| TC-14 | Tanggal lahir format salah | 10-05-2000 | Format tanggal tidak valid |
| TC-15 | Tanggal kalender tidak valid | 2000-02-30 | Tanggal lahir tidak valid |
| TC-16 | Umur 16 tahun | 2010-10-16 | Umur minimal 17 tahun |
| TC-17 | Tepat usia 17 tahun | 2009-10-16 | Tanggal lahir diterima |
| TC-18 | Belum 17 tahun satu hari | 2009-10-17 | Umur minimal 17 tahun |
| TC-19 | Password 7 karakter | Alvin1! | Password minimal 8 karakter |
| TC-20 | Password tanpa huruf besar | alvin123! | Password harus mengandung huruf besar |
| TC-21 | Password tanpa huruf kecil | ALVIN123! | Password harus mengandung huruf kecil |
| TC-22 | Password tanpa angka | AlvinAbc! | Password harus mengandung angka |
| TC-23 | Password tanpa simbol | Alvin1234 | Password harus mengandung simbol |
| TC-24 | Konfirmasi tidak sama | Password Alvin123!; konfirmasi Alvin123? | Konfirmasi password tidak sama |
| TC-25 | Konfirmasi sama | Password dan konfirmasi Alvin123! | Konfirmasi cocok; pendaftaran berhasil |

## Kesimpulan

Equivalence Partitioning membantu mengelompokkan input menjadi kelas valid dan invalid sehingga pengujian lebih efisien. Boundary Value Analysis melengkapi EP dengan menguji nilai tepat di sekitar batas. Pada API Testing, pengujian juga memeriksa status HTTP dan isi response. Semua expected output pada dokumen ini merupakan hasil yang diharapkan berdasarkan spesifikasi soal; hasil aktual perlu dicatat setelah test dijalankan pada aplikasi/API yang sesungguhnya.

## Checklist sebelum dikumpulkan

- Isi nama, NIM, dan kelas pada halaman awal.

- Periksa kembali apakah dosen meminta seluruh soal bonus atau hanya soal utama.

- Sesuaikan asumsi tanggal pengujian jika tanggal tugas berbeda.

- Jika diminta upload ke GitHub, simpan dokumen dan/atau versi Markdown di repository tugas.

- Jangan mengisi hasil aktual sebagai berhasil sebelum benar-benar melakukan pengujian.

