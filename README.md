Nama    : Ryandhika Al Afzal

NPM     : 2206081502

Kelas   : PBP A

Links Adaptable : https://inventorymanager.adaptable.app/main

**PBP tugas 2**

# Step-step memenuhi kriteria aplikasi

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

Bagan request client ke web aplikasi Django
![Django graph](https://github.com/RyanAfzal/inventory_manager/assets/137851158/f5db7f29-9c16-4943-b2f3-60622824822d)

# Alasan menggunakan virtual environment

• Virtual environment memungkinkan kita mengisolasi dependensi proyek. Ini berarti setiap proyek dapat memiliki versi Python dan paket dependensi yang berbeda, tanpa konflik dengan proyek lain.
• Mengelola dependencies lebih baik

Tanpa virtual environment kita tetap bisa membuat aplikasi web berbasis django, tetapi ketika terjadi penggunaan versi python yang berbeda dari tiap aplikasi pada proyek dapat menyebabkan konflik sehingga aplikasi tidak dapat berjalan.

# MVC, MVT, dan MVVM

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

ciri : menerima input dari user dan memanipulasi Model/View sesuai kebutuhan


2.	MVT (Model-View-Template) adalah pola desain untuk aplikasi berbasis web yang merupakan struktur turunan dari MVC.

Model membantu untuk mengatur database, template untuk mengatur interface, view berguna untuk menjalankan logika bisnis dan berinteraksi dengan model untuk membawa data dan render template.

ciri : tidak ada pemisahan controller, karena template untuk interface maka template menentukan bagaimana data ditampilkan pada view


3.	MVVM adalah salah satu arsitektur pembuatan aplikasi berbasis GUI yang berfokus pada pemisahan antara kode untuk logika bisnis dan tampilan aplikasi atau gabungan MVC dan MVP.



	Kelebihan :

•	Tidak memiliki hubungan (ketergantungan) antara View dan ViewModel.

•	Tidak ada antarmuka antara View dan Model.

•	Pengujian unit yang mudah dan kode yang digerakkan oleh peristiwa (event-driven).


	Kekurangan :

•	Pengembang harus membuat suatu kuantitas yang dapat diukur di setiap komponen UI.

•	Ukuran kode yang terlalu besar.

Ciri : menjadi media antara Model dan View, menangani input user, dan menangani data yang akan ditampilkan

**PBP tugas 3**

# Perbedaan get dan post

1. Data dengan get ditampilkan dalam url dan data dengan post sebagai request body (tidak terlihat)
2. Post lebih aman daripada get
3. Post digunakan untuk mengirim data contohnya untuk mengumpulkan form, sedangkan get digunakan untuk mengambil data, tetapi get juga bisa untuk transmit data misalnya untuk transmit data melalui link
4. Get memiliki batasan string sepanjang 2047 karakter, sedangkan post tidak memiliki batasan

# Perbedaan Json, Xml, dan HTML

Json (JavaScript Object Notation)
- Struktur : JSON menyimpan elemennya secara efisien akan tetapi tidak rapi untuk dilihat
- Nama dari file JSON akan diakhiri dengan ekstensi .json
- Penggunaan : JSON sering digunakan untuk pertukaran data antara aplikasi web dan server, serta untuk menyimpan konfigurasi dan pengaturan

-Xml (eXtensible Markup Language)
- Struktur : XML menyimpan elemen-elemen nya dengan cara yang terstruktur, mudah dibaca oleh manusia dan mesin, akan tetapi kurang efisien.
- Nama dari file Xml diakhiri dengan ekstensi .xml
- Penggunaan : XML sering digunakan untuk pertukaran data antara sistem yang berbeda atau untuk menyimpan data dalam format yang dapat diolah secara struktural. terutama dalam lingkungan bisnis dan web services.

HTML (Hyper Text Markup Language)
- Struktur : menggunakan mark atau tag untuk sebuah dokumen yang mengindikasikan struktur logis nya seperti paragraf dan secara semantik
- Nama dari file HTML diakhiri dengan ekstensi .html
- Penggunaan : HTML digunakan untuk membuat halaman web, menampilkan teks, gambar, tautan, dan elemen-elemen lainnya secara terstruktur.

# Alasan JSON sering digunakan dalam pertukaran data antara aplikasi web modern
1. Karena Json dapat menyimpan data secara efisien dan sintaks nya singkat
2. Json memiliki kemampuan parsing 
3. Untuk aplikasi AJAX Json lebih cepat daripada Xml
4. Json memiliki kemiripan dengan JavaScript sehingga program JavaScript dapat dengan mudah mengubah data Json ke object native JavaScript
5. ukuran file cenderung kecil
6. Json didukung oleh banyak bahasa pemrograman seperti Python, PHP, C++, Ruby, dan Perl.
7. Mendukung Internationalization: JSON mendukung encoding Unicode, yang memungkinkan untuk merepresentasikan teks dalam berbagai bahasa dan karakter khusus.
8. Mendukung Tipe Data Umum: JSON mendukung tipe data umum seperti string, angka, objek, dan array. Ini memungkinkan untuk merepresentasikan berbagai jenis data dalam satu format.

# Step-step tugas 3 

# Membuat input form
1. Sebelum membuat form saya membuat templates html terlebih dahulu untuk kerangka umum halaman web lainnya setelah itu buat tampilan lainnya menggunakan template utama.Lalu buat form di forms.py pada direktori main untuk menerima data produk baru.
2. Yang dibuat di forms.py import ke views.py yang ada pada main
3. Kemudian buat fungsi create_product untuk menambahkan produk baru dan fungsi show_main untuk yang akan ditampilkan di web dan tidak lupa untuk menambahkannya di urls.py
4. fungsi create_product juga dibuatkan html nya agar dapat diakses di web dengan tidak lupa membuat buttonnya

# Membuat 5 fungsi views
1. Pertama-tama pada views.py import HttpResponse yang berisi parameter data hasil query yang sudah diserialisasi dan serializers digunakan untuk translate objek model menjadi format lain
2. Kemudian buat fungsi show_xml, show_json, show_xml_by_id, dan show_json_by_id

# Membuat routing URL untuk masing-masing views
1. Pada urls.py pada main import function untuk masing-masing views
2. Tambahkan path url ke dalam urlpatterns untuk mengakses fungsi yang sudah diimpor 
