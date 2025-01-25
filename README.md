Botnet Meris

Pada awal September 2021, laboratorium QRATOR menerbitkan artikel tentang gelombang baru serangan DDoS, yang berasal dari botnet yang melibatkan perangkat MikroTik.
Sejauh yang kami lihat, serangan ini menggunakan router yang sama yang pernah disusupi pada tahun 2018 , saat MikroTik RouterOS memiliki kerentanan, yang dengan cepat diperbaiki.
Tidak ada kerentanan baru di RouterOS dan tidak ada malware yang bersembunyi di dalam sistem berkas RouterOS bahkan pada perangkat yang terpengaruh. Penyerang mengonfigurasi ulang perangkat RouterOS untuk akses jarak jauh, menggunakan perintah dan fitur RouterOS itu sendiri.
Sayangnya, menutup kerentanan lama tidak serta merta melindungi router ini. Jika seseorang mendapatkan kata sandi Anda pada tahun 2018, sekadar memperbaruinya tidak akan membantu. Anda juga harus mengubah kata sandi, memeriksa ulang firewall Anda jika tidak mengizinkan akses jarak jauh ke pihak yang tidak dikenal, dan mencari skrip yang tidak Anda buat.
Kami telah mencoba menghubungi semua pengguna RouterOS mengenai hal ini, tetapi banyak dari mereka yang belum pernah menghubungi MikroTik dan tidak memantau perangkat mereka secara aktif. Kami juga sedang mengupayakan solusi lainnya.
Tidak ada kerentanan baru pada perangkat ini. RouterOS baru-baru ini diaudit secara independen oleh beberapa pihak ketiga.

Tindakan terbaik yang dapat dilakukan:

Selalu perbarui perangkat MikroTik Anda dengan pemutakhiran rutin.
Jangan membuka akses ke perangkat Anda dari sisi internet kepada semua orang, jika Anda memerlukan akses jarak jauh, hanya buka layanan VPN yang aman, seperti IPsec.
Gunakan kata sandi yang kuat dan jika pun Anda melakukannya, ubahlah sekarang!
Jangan berasumsi bahwa jaringan lokal Anda dapat dipercaya. Malware dapat mencoba menyambung ke router Anda jika kata sandi Anda lemah atau tidak ada kata sandi.
Periksa konfigurasi RouterOS Anda untuk pengaturan yang tidak diketahui (lihat di bawah).
Bekerja sama dengan peneliti keamanan independen, kami menemukan bahwa ada malware yang mencoba mengonfigurasi ulang perangkat MikroTik Anda dari komputer Windows di dalam jaringan Anda. Inilah mengapa penting untuk menetapkan kata sandi yang lebih baik sekarang (untuk menghindari login tanpa kata sandi atau serangan kamus oleh malware ini) dan untuk terus memperbarui router MikroTik Anda (karena malware ini juga mencoba mengeksploitasi kerentanan CVE-2018-14847 yang telah lama diperbaiki).

Konfigurasi yang perlu diperhatikan dan dihapus:

Sistem -> Aturan penjadwal yang menjalankan skrip Fetch. Hapus aturan ini.
IP -> Proksi Socks. Jika Anda tidak menggunakan fitur ini atau tidak tahu fungsinya, fitur ini harus dinonaktifkan.
Klien L2TP bernama “lvpn” atau klien L2TP apa pun yang tidak Anda kenali.
Masukkan aturan firewall yang mengizinkan akses untuk port 5678.
Anda juga dapat bekerja sama dengan ISP Anda untuk memblokir alamat-alamat berikut, yang dihubungkan oleh skrip-skrip berbahaya ini:
