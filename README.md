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

# Akses kelima url
1. SS HTML
<img width="641" alt="SS HTML" src="https://github.com/RyanAfzal/inventory_manager/assets/137851158/33d2392f-8f7a-43bf-b6f4-1998beecc54c">

2. SS Xml
<img width="642" alt="SS Xml" src="https://github.com/RyanAfzal/inventory_manager/assets/137851158/d6990df0-b36b-4191-a550-9ea7fbfb55c4">

3. SS Json
<img width="646" alt="SS Json" src="https://github.com/RyanAfzal/inventory_manager/assets/137851158/4c8c9f4c-e91a-4862-b6a8-0136ccc473d8">

4. SS XML by ID
<img width="638" alt="SS Xml id" src="https://github.com/RyanAfzal/inventory_manager/assets/137851158/78829c0b-4b07-41dc-baf5-959b98f6d216">

5. SS Json by ID
<img width="646" alt="SS Json ID" src="https://github.com/RyanAfzal/inventory_manager/assets/137851158/be8761d0-1a71-45f1-b7b8-53639f6ccd80">


**PBP tugas 4**

# UserCreationForm
UserCreationForm adalah impor formulir bawaan yang memudahkan pembuatan formulir pendaftaran pengguna dalam aplikasi web. 

Kelebihan : 
1. Dengan formulir ini, pengguna baru dapat mendaftar dengan mudah di situs web Anda tanpa harus menulis kode dari awal.
2. Memiliki validasi built-in terkait hal yang biasa dibutuhkan pengguna, seperti memeriksa username unik, email yang valid, password yang kuat, dan lain-lain.
3. Dapat disesuaikan dengan kebutuhan, walaupun memiliki beberapa tempat untuk atribut yang sudah diatur secara default, pengguna dapat menambahkan tempat untuk atribut-atribut yang belum ada atau menghapus tempat dari atribut yang tidak dibutuhkan.

Kekurangan :
1. Jika tempat untuk atribut dan tampilan default tidak sesuai dengan kebutuhan, pengguna harus menyesuaikan sendiri dengan kebutuhan.
2. Tidak dapat memenuhi kebutuhan yang kompleks dari pengguna secara fungsi misalnya membutuhkan verifikasi email untuk login, maka lebih baik membuat form sendiri agar lebih sesuai dengan kebutuhan.

# Autentikasi dan Otorisasi pada Django
Perbedaannya :

1. Dari pengertian autentikasi adalah proses yang memeriksa atau memverifikasi siapa pengguna (untuk mengetahui identitas), misalnya pada saat login. Sedangkan otorisasi adalah proses yang memeriksa apakah pengguna memiliki akses untuk melakukan atau menggunakan suatu fitur.
2. Perbedaan waktu di mana autentikasi dilakukan terlebih dahulu setelah itu otorisasi.

Pentingnya autentikasi dan otorisasi :
1. Untuk keamanan, autentikasi dapat mencegah dari orang yang tidak dikenal mengakses aplikasi atau sistem yang kita miliki.
2. Dapat melindungi data, karena autentikasi dapat memeriksa siapa saja yang berhak untuk masuk ke suatu sistem maka yang dapat mengakses data hanyalah orang-orang yang diizinkan saja sehingga data lebih aman.
3. Otorisasi melindungi beberapa akses yang mungkin dapat disalahgunakan, merugikan, dan merusak jika diakses oleh sembarang orang termasuk yang diizinkan masuk ke dalam suatu sistem. Hanya orang yang diizinkan untuk masuk ke dalam sistem dan memiliki izin akses saja yang dapat mengakses fitur tertentu.

# Apa itu cookies dan bagaimana menggunakan cookies untuk mengelola data sesi pengguna
cookies adalah kumpulan data (rekam jejak digital dan aktivitas) yang diterima komputer dari sebuah situs dan mengirimkan kembali ke situs yang dikunjungi.

Cara cookies mengelola data sesi pengguna adalah dengan menyimpan informasi login misalnya yang disimpan adalah session id, saat pengguna login cookies ini akan dikirimkan ke browser lalu server(Django) akan membaca cookies yang telah dikirimkan sebelumnya sehingga server(Django) tahu sesi dari pengguna dan data sesi akan disimpan sampai kurun waktu tertentu, kemudian cookies juga dapat diperbarui untuk menyimpan data sesi pengguna terbaru. Saat sesi berakhir data sesi pada cookies juga dapat dihapus.

# Keamanan penggunaan cookies secara default
Dalam kondisi normal/default cookies aman, cookies tidak bisa mentransfer malware atau virus karena data yang dibawa cookies tidak berubah ketika berpindah dari komputer ke website dan sebaliknya.

Namun tetap ada risiko potensial yang harus diwaspadai karena kita menggunakan cookies di internet dan internet dapat diakses oleh siapapun. Risikonya yaitu :
1. Jika mengunjungi situs yang berbahaya data pada cookies bisa dicuri.
2. Masalah privasi, karena adanya kemungkinan data pada cookies dicuri maka data yang bersifat privasi sebaiknya tidak disimpan di dalam cookies.
3. Adanya risiko dari Web Application Threats seperti sql injection, XSS, CSRF, Cookie/Session poisoning dan lain-lain yang dapat merugikan pengguna karena dapat memanipulasi apapun termasuk cookies dan data sesi sehingga peretas dapat melakukan akses yang tidak dikehendaki oleh pengguna.

# Cara mengimplementasi checklist tugas 4 secara step by step

# Mengimplementasikan fungsi registrasi, login, dan logout
1. Pada views.py pada subdirektori buat 3 fungsi registrasi, login_user, dan logout_user serta import yang dibutuhkan oleh fungsi tersebut. untuk registrasi import redirect, UserCreationForm, dan messages; untuk login_user import authenticate dan login; dan untuk logout_user import logout.
2. Buat konfigurasi HTML dari 3 fungsi tersebut pada folder main/templates. Untuk register buat register.html beserta isi kode html nya, untuk login_user buat 
login.html beserta isi kode html nya, dan untuk logout tambahkan kode html untuk logout pada main.html
3. Pada urls.py di subdirektori main import ke 3 fungsi tersebut dan tambahkan ke dalam urlpatterns

# Membuat dua akun pengguna dengan masing-masing tiga dummy data
1. Jalankan server kemudian tekan tombol register untuk membuat dua akun.
2. Setelah login tambahkan 3 dummy data dengan menekan tombol Add New Product, tetapi saat ini data kedua akun masih sama, karena setiap akun masih terhubung pada data yang sama. Agar dapat membuat masing-masing 3 dummy data yang berbeda harus melakukan tahap berikutnya terlebih dahulu.

akun 1
<img width="356" alt="Screenshot akun 1 tugas PBP" src="https://github.com/RyanAfzal/inventory_manager/assets/137851158/15b204c7-1b73-4dc2-a394-da1077751598">

akun 2
<img width="397" alt="Screenshot akun 2 tugas PBP" src="https://github.com/RyanAfzal/inventory_manager/assets/137851158/0b1e6196-7517-4dd3-9de5-ac44e3a221a8">

# Menghubungkan model Item dengan User
1. Pada models.py di subdirektori main impor model dengan from django.contrib.auth.models import User
2. Pada Class Product tambahkan user = models.ForeignKey(User, on_delete=models.CASCADE) untuk menghubungkan satu produk/item dengan satu user melalui sebuah relationship, dimana sebuah produk pasti terasosiasikan dengan seorang user.
3. Pada views.py sesuaikan fungsi create_product seperti berikut
def create_product(request):
 form = ProductForm(request.POST or None)

 if form.is_valid() and request.method == "POST":
     product = form.save(commit=False)
     product.user = request.user
     product.save()
     return HttpResponseRedirect(reverse('main:show_main'))
     ...
...

4. Agar data tiap user tidak sama dan memiliki integrasi antara data dan user sendiri. Sesuaikan fungsi show_main seperti berikut
def show_main(request):
    products = Product.objects.filter(user=request.user)

    context = {
        'name': request.user.username,
        ...
...
5. Simpan semua perubahan dan lakukan migrasi model. python manage.py makemigrations untuk menyimpan perubahan pada model dan python manage.py migrate untuk mengaplikasi perubahan

# Menampilkan detail informasi pengguna yang sedang logged in seperti username dan menerapkan cookies seperti last login pada halaman utama aplikasi.
1. Pada main.html pada subdirektori main tambahkan <h5>Sesi terakhir login: {{ last_login }}</h5> untuk menampilkan last login 
2. tambahkan <h5>Username: {{ request.user.username }}</h5> untuk detail informasi pengguna yang sedang logged in seperti username.

**PBP tugas 5**

# CSS element selector dan elemen selektor pada CSS secara umum
CSS selector adalah salah satu rangkaian aturan dari CSS yang memiliki fungsi untuk memilih suatu elemen yang ingin dibergi gaya atau tampilan tergantung pada aturan pencocokan pola. Selector terdiri dari beberapa jenis yang memiliki beberapa manfaat, yaitu :

1. Universal Selector (*)
    Manfaat: untuk memilih semua elemen di halaman web. Dapat digunakan untuk mengatur tampilan default setiap elemen.

2. Element Selector (Tag Selector)

    Manfaat: untuk memilih semua elemen yang sesuai dengan nama tag HTML tertentu. Dapat digunakan untuk mengatur tampilan atau gaya elemen tertentu.

3. Class Selector (.classname)

    Manfaat: untuk memilih elemen berdasarkan nama kelas CSS yang dipilih. Dapat digunakan untuk memberi gaya beberapa elemen yang memiliki kelas yang sama.

4. ID Selector (#idname)

    Manfaat: untuk memilih elemen berdasarkan atribut id yang unik. Dapat digunakan untuk memberi gaya elemen yang harus tampil dengan gaya unik, dan setiap ID harus unik dalam satu halaman.

# HTML5 Tag
Tag adalah sebuah penanda awalan dan akhiran dari sebuah elemen di HTML5. HTML5 adalah versi terbaru dari bahasa markup HTML yang digunakan untuk membuat halaman web. Berikut beberapa contoh HTML5 Tag:
1. `<html>` : untuk memulai dokumen html
2. `<head>` : Bagian kepala dokumen yang berisi informasi seperti judul halaman, meta tag, dan tautan ke berkas CSS
3. `<body>` : Bagian utama halaman web yang berisi konten yang akan ditampilkan kepada pengguna.
4. `<a>` : Membuat tautan hyperlink ke halaman web lain atau berkas lain.
5. `<h1>` sampai `<h6>` : Digunakan untuk menandai judul atau heading dengan tingkat kepentingan yang berbeda.
dan lain-lain.

# Perbedaan Padding dan Margin
1. Margin
- Pengertian : ruang di luar elemen HTML. Ini adalah jarak antara elemen tersebut dan elemen-elemen lain di sekitarnya atau elemen lain di luar kontainer jika itu elemen terluar.
- Fungsi :  untuk mengontrol jarak antara elemen dengan elemen-elemen di luarnya.
- Margin bersifat transparan; elemen di bawahnya bisa terlihat melalui margin.

2. Padding 
- Pengertian : jarak antara elemen dan konten elemen itu sendiri (biasanya tepi elemen)
- Fungsi :  untuk mengontrol jarak antara konten elemen dan batas (border) elemen tersebut.
- Padding tidak bersifat transparan

# Perbedaan framework CSS tailwind dan bootstrap
1. Perbedaan pada desain

    - Bootstrap menawarkan set class CSS dan komponen yang telah dirancang sebelumnya dengan tampilan yang cukup terstruktur dan konsisten. Ini cocok untuk proyek dengan desain tradisional yang membutuhkan kerangka kerja yang stabil dan mudah digunakan.

    - Tailwind menganut pendekatan yang lebih "utility-first", di mana kita membangun antarmuka dengan menggabungkan class utilitas yang lebih kecil. Ini memberikan kebebasan kreatif yang lebih besar dan memungkinkan penggunaan class yang sangat spesifik.

2. Perbedaan secara fleksibilitas

    - Bootstrap menawarkan kerangka kerja yang relatif terstruktur dengan banyak komponen yang telah dirancang sebelumnya. Ini memberikan stabilitas dan kemudahan penggunaan, tetapi mungkin memiliki batasan dalam hal fleksibilitas desain yang unik.

    - Tailwind memberikan fleksibilitas yang lebih besar dengan pendekatan "utility-first" yang memungkinkan kita membangun desain yang sangat kustom sesuai kebutuhan. kita memiliki kendali penuh atas gaya dan tata letak dengan kombinasi class utilitas yang spesifik.

3. Perbedaan pada ukuran file

    - Bootstrap adalah kerangka kerja yang lebih besar dalam hal ukuran file karena menyediakan banyak fitur dan komponen yang siap pakai. Ini mungkin berdampak pada kecepatan pengunduhan dan performa halaman web.

    - Tailwind dirancang untuk lebih ringan dalam hal ukuran file. Namun, ketika kita menggunakan banyak class utilitas dalam kode, ukuran file CSS dapat meningkat.

4. Perbedaan ekosistem pengembangan

    - bootstrap memiliki ekosistem yang sangat kuat dengan dokumentasi yang kaya, banyak tema dan template yang tersedia, serta dukungan komunitas yang luas. Ini membuatnya mudah untuk memulai dan mendapatkan sumber daya yang diperlukan.

    - Tailwind juga memiliki ekosistem yang berkembang pesat dengan dokumentasi yang baik dan komunitas yang aktif, kita dapat menemukan banyak sumber daya, plugin, dan integrasi dengan kerangka kerja JavaScript seperti React atau Vue.

5. Perbedaan keutamaan
    - bootstrap menyediakan template dan kelas CSS untuk komponen umum yang dapat menyesuaikan tampilan dan menyediakan komponen siap pakai
    - tailwind tidak menyediakan komponen siap pakai, tetapi harus menggunakan kelas utilitas yang disediakan oleh tailwind.

- bootstrap sebaiknya digunakan jika ingin membangun web secara cepat walaupun pengaksesan web lebih lambat karena ukuran file bootstrap yang lebih besar daripada tailwind, ketika tidak ingin memberi banyak perubahan/custom pada design karena bootstrap sudah memiliki styling, dan ingin menggunakan komponen UI yang sudah ada

- tailwind sebaiknya digunakan ketika ingin membangun web yang memerlukan banyak penyesuaian, kustomisasi, dan tampilan yang unik dan spesifik.

# Cara mengimplementasi checklist tugas 5 secara step by step
1. Saya melakukan kustomisasi halaman login, register, dan tambah inventori dengan cara menyatukan yang ingin diubah dengan <div> tag.
2. Lalu lakukan kustomisasi dengan <style> tag yang berisi aturan tampilan dari <div> tag yang dipilih, contoh untuk kustomisasi login.html :
 body {
        display: flex;
        justify-content: center;
        align-items: center;
        font-family: "Poppins", sans-serif;
        min-height: 100vh;
        background: linear-gradient(red, blue);
    }
3. Saya juga menggunakan boostrap untuk melakukan kustomisasi contoh penerapan pada kode saya: <div class="d-flex justify-content-center">
4. Untuk kustomisasi register saya membuat custom UserCreationForm sebagai class baru pada forms.py di direktori main dan digunakan di fungsi register pada views.py pada direktori main
5. Kemudian untuk daftar item/inventory saya menggunakan card dengan cara membungkus inventory pada main.html di direktori main dengan <div> tag yang diberi nama class card.
6. Dan class card tersebut diatur dengan bootstrap dan CSS dengan <style> tag 

# Bonus tugas 5 PBP
<img width="382" alt="Bonus tugas 5 PBP" src="https://github.com/RyanAfzal/inventory_manager/assets/137851158/883fea26-37fa-47fe-b214-d0acbf65dce7">

**PBP tugas 5**

# Perbedaan antara asynchronous programming dengan synchronous programming
1. asynchronous programming bersifat multi-thread, artinya banyak operasi atau program dapat berjalan secara paralel, sedangkan synchronous programming bersifat single-thread, artinya hanya 1 operasi yang dapat berjalan pada waktu yang sama
2. asynchronous programming bersifat non-blocking, artinya mengirim banyak request ke server, sedangkan synchronous programming bersifat blocking, artinya hanya 1 request yang dikirim ke server pada waktu yang sama dan menunggu request tersebut dijawab oleh server
3. asynchronous programming throughput nya lebih banyak dari synchronous programming, sedangkan synchronous programming lebih lambat


# Paradigma event-driven programming pada penerapan Javascript dan Ajax
pengertian event-driven programming adalah paradigma programming yang mengatur dan membuat alur code terstruktur berdasarkan event yang terjadi atau merespons event bukan alur code dari atas ke bawah seperti biasanya, event ini berasal dari sumber external seperti input user dan perubahan sistem.

Contoh penerapannya pada tugas ini:
1. Asynchronous Function: Dalam JavaScript, ada dua fungsi yang digunakan dengan kata kunci async: getProducts dan addProduct. Fungsi ini adalah asinkron, yang berarti mereka dapat menjalankan operasi jaringan seperti pengambilan data atau pengiriman data tanpa menghalangi eksekusi program utama.

2. Event Listeners/Handlers: Kode JavaScript juga menggunakan event listeners. Sebagai contoh, document.getElementById("button_add").onclick = addProduct adalah event listener yang menunggu klik pada elemen HTML dengan ID "button_add" dan akan memanggil fungsi addProduct saat tombol tersebut diklik. Event listeners adalah dasar dari pemrograman berbasis peristiwa.

3. Fetch API: fetch digunakan untuk mengambil data dari URL. Ini adalah contoh tipikal dari operasi asinkron yang melibatkan jaringan dalam pemrograman berbasis peristiwa.

4. Manipulasi DOM: Kode JavaScript mengambil elemen-elemen HTML dengan document.getElementById dan mengubah isi atau struktur HTML dengan innerHTML. Ini adalah bagian dari manipulasi Document Object Model (DOM), yang merupakan salah satu aspek utama dalam pemrograman berbasis peristiwa.

# Penerapan asynchronous programming pada AJAX.
penerapan asyncrhonous programming pada ajax biasanya dengan XMLHttpRequest, dengan cara membuat object XMLHttpRequest terlebih dahulu, lalu menentukan apa yang akan dilakukan saat request ke server selesai, kemudian mengirim request ke server, terakhir Aksi akan dipicu oleh JavaScript sesuai dengan yang dibuat.

atau bisa juga menggunakan Fetch API karena Fetch API dapat melakukan semua yang dilakukan oleh XMLHttpRequest (XHR) object. Contohnya:

```async function getProducts() {
    return fetch("{% url 'main:get_product_json' %}").then((res) => res.json())
}
```

# Perbandingan Fetch API dan library jquery
1. ukuran jquery lebih besar daripada Fetch API. Karena jquery adalah library yang memiliki banyak fitur lain yang mungkin tidak diperlukan dalam proyek tertentu sehingga ukuran lebih besar, sedangkan Fetch API hanya menyediakan fungsionalitas dasar untuk mengambil dan mengirim data.

2. Fetch API: Fetch API menggunakan Promise, yang merupakan teknik asynchronous modern yang membuat kode lebih mudah dibaca dan dikelola, terutama ketika Anda harus menangani banyak permintaan data secara bersamaan. Sedangkan jQuery: jQuery menggunakan pendekatan callback yang lebih tua untuk menangani permintaan AJAX. Ini dapat menghasilkan kode yang lebih sulit dibaca dan memahami jika ada banyak permintaan bersarang.

3. Fetch API Cenderung lebih cepat dalam penggunaan yang tepat, sedangkan jquery Mungkin memiliki overhead tambahan dan sedikit lebih lambat dalam beberapa kasus

4. Fetch API memberikan fleksibilitas yang tinggi kepada pengembang untuk membangun fitur tambahan sesuai kebutuhan. Anda dapat mengontrol dengan detail bagaimana permintaan dan respons dielaborasi, termasuk header, jenis konten, metode permintaan, dan banyak hal lainnya, serta lebih modular. Sedangkan jquery terbatas pada fitur ajax dan jQuery cocok untuk proyek-proyek yang membutuhkan manipulasi DOM yang kuat dan berbagai efek visual, tetapi mungkin tidak sesuai jika Anda memerlukan kendali yang lebih besar atas permintaan dan respons HTTP.

Karena pada tugas ini membutuhkan yang lebih cepat dan lebih fleksibel maka dipilih Fetch API.

# Cara mengimplementasi checklist tugas 6 secara step by step
1. Buat fungsi get_product_json pada views.py untuk mengambil data product dalam format JSON seperti berikut:
``` shell
def get_product_json(request):
    product_item = Product.objects.all()
    return HttpResponse(serializers.serialize('json', product_item))
```

2. Mengubah code cards agar dapat mendukung ajax get seperti berikut pada main.html:
``` shell
async function refreshProducts() {
            document.getElementById("product_table").innerHTML = "";
            const products = await getProducts();
            
            let htmlString = '<div class="card-deck">'

            products.forEach((item, index) => {
                let cardClass = "card";
                if (index === products.length - 1) {
                    cardClass += " last-card"
                }
                htmlString += `
                    <div class="${cardClass}">
                        <div class="card-body">
                            <h5 class="card-title">${item.fields.name}</h5>
                            <p class="card-text">Amount: ${item.fields.amount}</p>
                            <p class="card-text">Description: ${item.fields.description}</p>
                            <div class="button">
                                <a href="edit-product/${item.pk}" class="btn btn-primary">
                                    Edit
                                </a>
                                <a href="delete/${item.pk}" class="btn btn-danger">
                                    Delete
                                </a>
                            </div>
                        </div>
                    </div>`
            })
            htmlString += '</div>'
            document.getElementById("product_table").innerHTML = htmlString;
        }

        refreshProducts();
```

3. Membuat tombol modal sebagai form untuk menambahkan item, dengan cara pada main.html tambahkan kode berikut
``` shell

<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <h1 class="modal-title fs-5" id="exampleModalLabel">Add New Product</h1>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body">
                <form id="form" onsubmit="return false;">
                    {% csrf_token %}
                    <div class="mb-3">
                        <label for="name" class="col-form-label">Name:</label>
                        <input type="text" class="form-control" id="name" name="name"></input>
                    </div>
                    <div class="mb-3">
                        <label for="price" class="col-form-label">Price:</label>
                        <input type="number" class="form-control" id="price" name="price"></input>
                    </div>
                    <div class="mb-3">
                        <label for="description" class="col-form-label">Description:</label>
                        <textarea class="form-control" id="description" name="description"></textarea>
                    </div>
                </form>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                <button type="button" class="btn btn-primary" id="button_add" data-bs-dismiss="modal">Add Product</button>
            </div>
        </div>
    </div>
</div>
``` 

Dan untuk tombol nya
``` shell

<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">Add Product by AJAX</button>
```

4. Membuat ajax post untuk menambahkan item, dengan menambahkan fungsi berikut pada views.py
``` shell
@csrf_exempt
def add_product_ajax(request):
if request.method == 'POST':
    name = request.POST.get("name")
    price = request.POST.get("price")
    description = request.POST.get("description")
    user = request.user

    new_product = Product(name=name, price=price, description=description, user=user)
    new_product.save()

    return HttpResponse(b"CREATED", status=201)

return HttpResponseNotFound()
```

5. seperti biasa fungsi yang dibuat tambahkan ke urlspatterns pada urls.py dan tidak lupa untuk import fungsi tersebut, contoh :
``` shell

    path('get-product/', get_product_json, name='get_product_json'),
    path('create-product-ajax/', add_product_ajax, name='add_product_ajax')
```
6. Buat fungsi JavaScript untuk menambahkan item
di dalam tag `<script></script>` tambahkan 
``` shell

function addProduct() {
        fetch("{% url 'main:add_product_ajax' %}", {
            method: "POST",
            body: new FormData(document.querySelector('#form'))
        }).then(refreshProducts)

        document.getElementById("form").reset()
        return false
    }
document.getElementById("button_add").onclick = addProduct
```

7. Jalankan perintah
```
python manage.py collectstatic
```











