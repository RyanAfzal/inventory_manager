Nama    : Ryandhika Al Afzal

NPM     : 2206081502

Kelas   : PBP A

Links Adaptable : https://inventorymanager.adaptable.app/main

Step-step memenuhi kriteria aplikasi

- Membuat proyek Django baru
1. Memiliki repository pada github dan folder yang terhubung dengan repository pada github, kemudian buat virtual environment dari folder tersebut
2. Install komponen yang dibutuhkan proyek (dependencies)
3. Mengatur siapa saja yang dapat mengakses aplikasi
4. Mengatur konfigurasi berkas-berkas yang harus diabaikan oleh git (gitignore)
5. Aktifkan virtual environment

- Membuat aplikasi dengan nama main
6. Buat aplikasi main dengan perintah python manage.py startapp main

- Routing proyek agar dapat menjalankan main
7. Daftarkan aplikasi main ke proyek dengan menambahkan 'main' pada variabel INSTALLED_APPS di settings.py

- Membuat model pada aplikasi main
Dalam aplikasi main pada berkas models.py buat class untuk model dengan parameter models.Model. Lalu isi class tersebut dengan atribut 

• name sebagai nama item dengan tipe CharField.

• amount sebagai jumlah item dengan tipe IntegerField.

• description sebagai deskripsi item dengan tipe TextField

Kemudian migrasi model agar jika ada perubahan dapat terefleksikan

- Membuat fungsi views.py yang berisi from django.shortcuts import render untuk me-render tampilan HTML dengan menggunakan data yang diberikan. Lalu buat fungsi show_main dengan parameter objek permintaan HTTP yang dikirim oleh pengguna dan isi dictionary yang berisi data yang akan dikembalikan pada template HTML.
 
- Membuat sebuah routing pada urls.py aplikasi main untuk memetakan fungsi yang telah dibuat pada views.py. Pertama import path dan show_main dari main.views pada urls.py dan buat variable app_name = main, kemudian isi path dengan cara urlpatterns = [
path('', show_main, name='show_main'),
].

Setelah itu pada urls.py di direktori proyek tambahkan path('main/',include('main.urls')), pada list urlpatterns.

- Lalu deploy aplikasi ke Adaptable dengan cara :

• Buatlah akun Adaptable.io menggunakan akun GitHub yang digunakan untuk membuat proyek shopping_list.

• Jika sudah login, silakan tekan tombol New App. Pilih Connect an Existing Repository.

• Hubungkan Adaptable.io dengan GitHub dan pilih All Repositories pada proses instalasi.

• Pilihlah repositori proyek shopping_list sebagai basis aplikasi yang akan di-deploy. Pilih branch yang ingin dijadikan sebagai deployment branch.

• Pilihlah Python App Template sebagai template deployment.

• Pilih PostgreSQL sebagai tipe basis data yang akan digunakan.

• Sesuaikan versi Python dengan spesifikasi aplikasimu. Untuk mengeceknya, nyalakan virtual environment dan jalankan perintah python --version.

• Pada bagian Start Command masukkan perintah python manage.py migrate && gunicorn namaAplikasi.wsgi.

• Masukkan nama aplikasi yang juga akan menjadi nama domain situs web aplikasimu.

• Centang bagian HTTP Listener on PORT dan klik Deploy App untuk memulai proses deployment aplikasi.

- buat README.md pada direktori utama dengan text editor

Alasan menggunakan virtual environment

• Virtual environment memungkinkan kita mengisolasi dependensi proyek. Ini berarti setiap proyek dapat memiliki versi Python dan paket dependensi yang berbeda, tanpa konflik dengan proyek lain.
• Mengelola dependencies lebih baik

Tanpa virtual environment kita tetap bisa membuat aplikasi web berbasis django, tetapi ketika terjadi penggunaan versi python yang berbeda dari tiap aplikasi pada proyek dapat menyebabkan konflik sehingga aplikasi tidak dapat berjalan.

MVC, MVP, dan MVVM

1.	Model-View-Controller atau MVC adalah sebuah metode untuk membuat sebuah aplikasi dengan memisahkan data (Model) dari tampilan (View) dan cara bagaimana memprosesnya (Controller).



	Kelebihan :

•	MVC membuat logika bisnis terpisah dalam Model.

•	Mendukung teknik asynchronous.

•	Jika terjadi suatu modifikasi, maka tidak akan mempengaruhi keseluruhan Midel.

•	Proses pengembangan aplikasi yang dilakukan dapat lebih cepat.



	Kekurangan :

•	Arsitektur ini dapat meningkatkan kompleksitas.

•	Pengujian unit terhalang.

•	Controller kode yang besar yang membuat pengembang tidak bisa mengelolahnya.



2.	MVP (Model-View-Presenter) adalah pola desain yang memberikan pendekatan terstruktur untuk membangun aplikasi perangkat lunak, khususnya dalam konteks pengembangan backend, logika presentasi.



	Kelebihan :

•	Dapat memberikan kemudahan terhadap penukaran tampilan.

•	View dan Presenter dapat digunakan kembali untuk pengembangan aplikasi.

•	Kode yang lebih mudah untuk dibaca dan dipelihara.

•	Kemudahan pengujian dikarenakan logika bisnis yang terpisah dari UI.



	Kekurangan : 

•	Ukuran kode yang terlalu besar.

•	Banyaknya interface untuk berinteraksi antar lapisan yang terpisah.

•	Memiliki hubungan yang erat antara View dan Presenter



3.	MVVM adalah salah satu arsitektur pembuatan aplikasi berbasis GUI yang berfokus pada pemisahan antara kode untuk logika bisnis dan tampilan aplikasi atau gabungan MVC dan MVP.



	Kelebihan :

•	Tidak memiliki hubungan (ketergantungan) antara View dan ViewModel.

•	Tidak ada antarmuka antara View dan Model.

•	Pengujian unit yang mudah dan kode yang digerakkan oleh peristiwa (event-driven).

	Kekurangan :

•	Pengembang harus membuat suatu kuantitas yang dapat diukur di setiap komponen UI.

•	Ukuran kode yang terlalu besar.
