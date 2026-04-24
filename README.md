README – Prosedur MySQL Validasi & Analisis Data Mahasiswa
📌 Deskripsi Proyek

Proyek ini berisi kumpulan Stored Procedure MySQL yang digunakan untuk mensimulasikan proses pemeriksaan data akademik mahasiswa sebelum pengisian KRS (Kartu Rencana Studi).

Sistem ini memproses data mahasiswa seperti:

Identitas mahasiswa
Status pembayaran UKT
Jumlah SKS
IPK
Semester

Kemudian menghasilkan informasi:

Validasi data akademik
Analisis beban studi
Evaluasi performa akademik
Rekomendasi kelayakan pengambilan KRS
Perbandingan dua mahasiswa
🗂️ Struktur Prosedur

Terdapat 4 stored procedure utama:

Prosedur	Fungsi
bagian_a	Menampilkan identitas mahasiswa
bagian_b	Validasi data akademik & analisis performa
bagian_c	Ringkasan kelayakan KRS
bagian_d	Perbandingan dua mahasiswa
⚙️ Cara Menjalankan
Jalankan script SQL di MySQL / phpMyAdmin.
Pastikan delimiter sudah sesuai (DELIMITER $$).
Setelah semua prosedur dibuat, panggil dengan perintah CALL.
🧩 Penjelasan Tiap Prosedur
🟢 1. Prosedur bagian_a – Identitas Mahasiswa
🎯 Tujuan

Menampilkan identitas mahasiswa dalam bentuk kalimat lengkap.

📥 Parameter
Parameter	Keterangan
p_nama	Nama mahasiswa
p_nim	NIM
p_semester	Semester
p_prodi	Program Studi
▶️ Contoh Pemanggilan
CALL bagian_a('Rina Putri','220101','4','Informatika');
📤 Output

Kalimat identitas mahasiswa yang telah diformat.

🟡 2. Prosedur bagian_b – Validasi & Analisis Akademik
🎯 Tujuan

Menentukan:

Status validasi data
Beban studi berdasarkan SKS
Performa akademik berdasarkan IPK
📥 Parameter
Parameter	Keterangan
p_jumlah_sks	Total SKS
p_ipk	IPK mahasiswa
p_status_ukt	Status UKT (Lunas/Belum)
p_semester	Semester
📊 Kategori Beban Studi
SKS	Kategori
1–12	Ringan
13–18	Sedang
19–24	Padat
📈 Kategori IPK
IPK	Performa
≥ 3.50	Sangat Baik
≥ 3.00	Baik
≥ 2.50	Cukup
< 2.50	Perlu Pembinaan
▶️ Contoh Pemanggilan
CALL bagian_b(20,3.45,'LUNAS',4);
🔵 3. Prosedur bagian_c – Ringkasan Kelayakan KRS
🎯 Tujuan

Menghasilkan ringkasan lengkap kelayakan mahasiswa mengambil KRS.

Output meliputi:

Identitas mahasiswa
Kampus
Beban studi
Performa akademik
Status kelayakan KRS
Alasan kelayakan
Ringkasan akhir
▶️ Contoh Pemanggilan
CALL bagian_c(
'Rina Putri','220101','4','Informatika',
20,3.45,'LUNAS'
);
🔴 4. Prosedur bagian_d – Perbandingan Dua Mahasiswa
🎯 Tujuan

Membandingkan dua mahasiswa berdasarkan:

SKS
IPK
Beban studi
Performa akademik

Sistem akan memberikan kesimpulan siapa lebih unggul.

▶️ Contoh Pemanggilan
CALL bagian_d(
'Rina','220101',4,20,3.60,'LUNAS',
'Budi','220102',4,18,3.20,'LUNAS'
);
📤 Output
Tabel perbandingan mahasiswa
Kesimpulan mahasiswa yang lebih unggul
🧠 Logika Sistem

Sistem menggunakan:

Variabel lokal (DECLARE)
Percabangan (IF, ELSEIF)
Penggabungan teks (CONCAT)
Output tabel (SELECT)
UNION ALL untuk perbandingan data
🎓 Tujuan Pembelajaran

Proyek ini bertujuan untuk melatih:

Pembuatan Stored Procedure MySQL
Penggunaan variabel & logika percabangan
Pemrosesan data akademik sederhana
Simulasi sistem validasi KRS
✅ Kesimpulan

Stored procedure ini berhasil mensimulasikan proses awal validasi data akademik mahasiswa sebelum pengisian KRS secara otomatis dan terstruktur menggunakan MySQL.
