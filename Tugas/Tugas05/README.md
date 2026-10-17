# Tugas 05 — Black-box Testing (Equivalence Partitioning & Boundary Value Analysis)

Nama: Lutfiana Faisal Patah | NIM: 3224018 | Kelas: Sistem Informasi
Mata Kuliah: Implementasi Pengujian Perangkat Lunak — Pertemuan 5

## Isi folder

| File | Keterangan |
|---|---|
| [`JAWABAN_TUGAS05.md`](./JAWABAN_TUGAS05.md) | Jawaban lengkap seluruh soal dalam format tabel (terbaca langsung di GitHub) |
| [`Jawaban_Latihan_Black_Box_Testing_Materi_5.docx`](./Jawaban_Latihan_Black_Box_Testing_Materi_5.docx) | Dokumen resmi pengumpulan, isinya sama dengan file Markdown |

## Cakupan jawaban

| Bagian | Soal | Teknik | Jumlah test case |
|---|---|---|---|
| A | Soal 1 — Form Login | Equivalence Partitioning | 13 partisi |
| A | Soal 2 — Form Pemesanan Tiket | Equivalence Partitioning | 13 partisi |
| B | Soal 3 — Form Pendaftaran Mahasiswa | Boundary Value Analysis | 18 nilai batas |
| B | Soal 4 — Form Transfer Bank | Boundary Value Analysis | 6 nilai batas |
| C | Soal 5 — Form Registrasi Akun | Kombinasi EP & BVA | 25 test case (syarat: minimal 20) |
| D | Soal 6 — `POST /api/v1/products` | API Testing | 9 test case (syarat: minimal 6) |
| E | Soal 7 — Form Pendaftaran Online (bonus) | Studi kasus terpadu | 25 test case (syarat: minimal 25) |

## Catatan pengerjaan

- Seluruh kolom `Expected Output` berisi **hasil yang diharapkan berdasarkan spesifikasi soal**,
  bukan hasil aktual. Hasil aktual baru boleh diisi setelah test benar-benar dijalankan
  pada aplikasi atau API yang sesungguhnya.
- Soal 7 memakai asumsi tanggal pengujian **16 Oktober 2026**, sehingga `2009-10-16` tepat
  berusia 17 tahun dan `2009-10-17` belum berusia 17 tahun. Sesuaikan bila dikumpulkan
  pada tanggal lain.
- Soal 4 hanya meminta nilai batas **Nominal Transfer**. Biaya admin Rp2.500 dan saldo
  minimum Rp50.000 adalah validasi terpisah, sehingga kolom `Valid*` pada nominal tetap
  bergantung pada pencukupan saldo.
- Field tanpa rentang numerik (misalnya Email) sengaja tidak diberi tabel BVA karena BVA
  berlaku untuk input yang punya batas bawah dan atas.

## Referensi materi

- Slide: `Pertemuan-5-Slide_Kuliah_Black-box_Testing.pdf`
- Soal: `LATIHAN TERSTRUKTUR-Materi-5.pdf`
