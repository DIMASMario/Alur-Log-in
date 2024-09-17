# Alur-Log-in
itur login memungkinkan pengguna untuk mengakses akun mereka dengan memasukkan kredensial yang benar. Fitur ini melibatkan proses otentikasi pengguna untuk memastikan hanya pengguna yang berwenang yang dapat mengakses aplikasi atau layanan. Berikut adalah alur fitur login yang umum digunakan:
1. Halaman Login
Deskripsi: Halaman login adalah antarmuka utama tempat pengguna memasukkan kredensial mereka.
Elemen:
Formulir Login: Memuat input untuk username dan password.
Tombol Login: Mengirim data ke server untuk proses otentikasi.
Tautan Lupa Password: Untuk pengguna yang lupa password mereka.
Tautan Daftar: Untuk pengguna baru yang belum memiliki akun.
2. Input Kredensial
Deskripsi: Pengguna memasukkan username dan password mereka ke dalam formulir login.
Validasi:
Username dan Password: Memastikan bahwa kedua input tidak kosong.
Format Valid: Memastikan bahwa format username dan password memenuhi kriteria yang ditentukan (misalnya, panjang minimum).
3. Pengiriman Data
Deskripsi: Setelah pengguna menekan tombol login, data kredensial dikirim ke server untuk proses otentikasi.
Metode: Menggunakan metode HTTP POST untuk mengirim data ke endpoint login di server.
Keamanan: Data harus dikirim melalui koneksi HTTPS untuk melindungi informasi sensitif.
4. Proses Otentikasi di Server
Deskripsi: Server memverifikasi kredensial yang dikirim oleh pengguna.
Langkah:
Pencocokan: Mencocokkan username dan password dengan data yang tersimpan di database.
Validasi: Memeriksa apakah akun tersebut aktif dan tidak terkunci.
Token: Jika kredensial valid, server menghasilkan token otentikasi (misalnya, JWT) yang akan digunakan untuk mengakses sumber daya yang dilindungi.
5. Respons dari Server
Deskripsi: Server mengirimkan respons kembali ke aplikasi berdasarkan hasil otentikasi.
Kemungkinan Respons:
Sukses: Berisi token otentikasi dan informasi pengguna. Pengguna diarahkan ke halaman utama aplikasi.
Gagal: Berisi pesan kesalahan (misalnya, "Username atau password salah"). Pengguna diminta untuk mencoba lagi.
6. Penanganan Kesalahan
Deskripsi: Menampilkan pesan kesalahan jika proses login gagal.
Pesan Umum:
Username atau Password Salah: Jika kredensial tidak sesuai.
Akun Tidak Aktif: Jika akun pengguna tidak aktif.
Masalah Server: Jika terjadi kesalahan di sisi server.
7. Akses ke Halaman Utama
Deskripsi: Setelah login berhasil, pengguna akan diarahkan ke halaman utama aplikasi.
Pengalihan: Menggunakan token otentikasi untuk memuat konten yang relevan sesuai dengan hak akses pengguna.
8. Logout
Deskripsi: Fitur logout memungkinkan pengguna untuk mengakhiri sesi mereka dan menghapus token otentikasi.
Langkah:
Hapus Token: Menghapus token otentikasi dari penyimpanan lokal (misalnya, localStorage atau sessionStorage).
Pengalihan: Mengarahkan pengguna ke halaman login atau halaman utama tanpa akses.
