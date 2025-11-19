<h1>Tugas 7</h1>
<hr>
<h3> Jelaskan apa itu widget tree pada Flutter dan bagaimana hubungan parent-child (induk-anak) bekerja antar widget.</h3>
<p>Dalam Flutter, widget tree adalah struktur hierarki yang menggambarkan bagaimana semua elemen antarmuka pengguna tersusun dan saling berhubungan. Setiap tampilan yang muncul di layar, mulai dari teks, tombol, ikon, hingga keseluruhan halaman, semuanya merupakan widget. Flutter menampilkan UI dengan cara menelusuri dan merender pohon widget ini dari atas ke bawah, dimulai dari root widget seperti MaterialApp, kemudian turun ke widget lain seperti Scaffold, AppBar, Body, dan seterusnya. Di dalam widget tree, terdapat hubungan parent–child (induk–anak). Widget yang membungkus widget lain disebut parent, sedangkan widget yang dibungkus disebut child. Misalnya, dalam kode Scaffold(body: Center(child: Text("Hello"))), Scaffold adalah parent dari Center, dan Center adalah parent dari Text. Parent berperan dalam mengatur tata letak, posisi, ukuran, serta perilaku visual dari child-nya. Sebaliknya, child menyesuaikan diri dengan batasan (constraint) dan aturan yang diberikan oleh parent.</p>

<br>

<h3>Sebutkan semua widget yang kamu gunakan dalam proyek ini dan jelaskan fungsinya.</h3>
<ul>
  <li>Scaffold : Menyediakan struktur dasar halaman aplikasi seperti AppBar, body, dan floating./li>
  <li>AppBar : Bagian atas halaman yang menampilkan judul atau aksi penting.</li>
  <li>Padding : Memberikan jarak di sekitar widget agar tidak menempel pada tepi layar.</li>
  <li>Column : Menyusun widget secara vertikal.</li>
  <li>Row : Menyusun widget secara horizontal.</li>
  <li>SizedBox : Memberikan jarak vertikal atau horizontal antar widget.</li>
  <li>Center : Menempatkan widget anaknya tepat di tengah layar.</li>
  <li>GridView.count : Menampilkan widget dalam bentuk grid dengan jumlah kolom tertentu.</li>
</ul>

<br>

<h3>Apa fungsi dari widget MaterialApp? Jelaskan mengapa widget ini sering digunakan sebagai widget root.</h3>
<p>Widget MaterialApp berfungsi sebagai kerangka utama (root widget) dalam aplikasi Flutter yang menggunakan Material Design, yaitu adalah sistem desain visual milik Google. Widget ini menyediakan banyak pengaturan penting untuk seluruh aplikasi, seperti tema warna, font, navigasi antar halaman (routes), serta pengaturan lokal (localization).</p>

<br>

<h3>Jelaskan perbedaan antara StatelessWidget dan StatefulWidget. Kapan kamu memilih salah satunya?</h3>
<ul>
  <li>StatelessWidget adalah widget yang tidak memiliki state. Artinya, tampilannya hanya bergantung pada data yang diberikan saat pertama kali dibuat, dan tidak akan berubah selama widget itu aktif di layar. Jika ingin mengubah tampilannya, kita harus membuat ulang widget tersebut dengan data baru. Contohnya seperti teks statis, ikon, atau tombol yang hanya menampilkan sesuatu tanpa interaksi kompleks. Pada tugas 7, contoh StatelessWidget adalah kelas MyHomePage, InfoCard, dan ItemCard, karena tampilannya tidak berubah kecuali seluruh widget dibangun ulang.
  </li>
  <li>
    StatefulWidget adalah widget yang memiliki state dinamis, artinya tampilannya bisa berubah seiring waktu tanpa perlu membangun ulang seluruh widget. Widget ini terdiri dari dua bagian: StatefulWidget itu sendiri (sebagai struktur) dan State (yang menyimpan data yang dapat berubah). Biasanya digunakan untuk komponen interaktif seperti form input, animasi, counter, atau elemen yang menampilkan data yang terus diperbarui.
  </li>
</ul>

<br>

<h3>Apa itu BuildContext dan mengapa penting di Flutter? Bagaimana penggunaannya di metode build?</h3>
<p>
  BuildContext adalah “identitas lokasi” sebuah widget di dalam struktur aplikasi. Ia memungkinkan widget untuk mengakses data, tema, ukuran layar, navigator, dan berbagai informasi dari widget induk (parent). Misalnya, ketika kita menulis Theme.of(context) untuk mengambil warna tema, atau Navigator.of(context).push() untuk berpindah halaman, semua itu bergantung pada BuildContext agar Flutter tahu di bagian mana dari widget tree permintaan itu berasal.
</p>

<br>

<h3>Jelaskan konsep "hot reload" di Flutter dan bagaimana bedanya dengan "hot restart".</h3>
<ul>
  <li>
    Konsep “hot reload” di Flutter adalah fitur yang memungkinkan pengembang melihat perubahan kode secara langsung tanpa harus menjalankan ulang seluruh aplikasi. Ketika kamu melakukan hot reload, Flutter akan menyuntikkan perubahan kode baru ke dalam aplikasi yang sedang berjalan, lalu memperbarui tampilan UI tanpa menghapus state (keadaan) aplikasi yang sedang aktif.
  </li>
  <li>
    “Hot restart” melakukan pemulihan penuh dari aplikasi. Flutter akan memuat ulang seluruh kode dari awal dan menghapus semua state yang tersimpan. Dengan kata lain, aplikasi dijalankan ulang seperti saat pertama kali dibuka.
  </li>
</ul>

<br>

<h1>Tugas 8</h1>
<hr>

<h3>Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement() pada Flutter. Dalam kasus apa sebaiknya masing-masing digunakan pada aplikasi Football Shop kamu?</h3>
<ul>
  <li>
    Navigator.push() berfungsi untuk menambahkan halaman baru di atas halaman saat ini di stack navigasi.
Dengan Navigator.push() pengguna masih bisa kembali ke halaman sebelumnya dengan tombol back.
  </li>
  <li>
    Navigator.pushReplacement() akan mengganti halaman saat ini dengan halaman baru (halaman lama dihapus dari stack).
Navigator.pushReplacement() digunakan jika kita tidak ingin user bisa kembali ke halaman sebelumnya.
  </li>
</ul>

<br>

<h3>Bagaimana kamu memanfaatkan hierarchy widget seperti Scaffold, AppBar, dan Drawer untuk membangun struktur halaman yang konsisten di seluruh aplikasi?</h3>
<ul>
  <li>
    Scaffold --> Menjadi kerangka utama halaman dimana di dalamnya ada struktur dasar seperti AppBar, Drawer, dan body.
    Dengan Scaffold, setiap halaman punya tata letak yang konsisten.
  </li>
  <li>
    Appbar --> Berfungsi sebagai judul halaman dan memberikan identitas visual. 
  </li>
  <li>
    Drawer (LeftDrawer) --> Digunakan untuk menampilkan navigasi utama aplikasi, misalnya akses ke halaman All Products, My Products, dan Logout.
Dengan menaruh Drawer di tiap halaman, pengguna bisa berpindah antar menu tanpa harus kembali ke home.
  </li>
</ul>

<br>

<h3>Dalam konteks desain antarmuka, apa kelebihan menggunakan layout widget seperti Padding, SingleChildScrollView, dan ListView saat menampilkan elemen-elemen form? Berikan contoh penggunaannya dari aplikasi kamu.</h3>
<ul>
  <li>
    Padding --> Memberi jarak antar elemen form supaya tidak terlalu dekat. Padding membuat form kita menjadi lebih nyaman dibaca dan tidak terlihat "penuh".
  </li>
  <li>
    SingleChildScrollView --> Berguna supaya form bisa discroll saat layar kecil (misal HP kecil atau keyboard terbuka). SingleChildScrollView mencegah tampilan “overflow” ketika form-nya panjang.
  </li>
  <li>
    ListView --> Jika elemen banyak dan dinamis, ListView berguna untuk menampilkan daftar secara scrollable dan efisien.
  </li>
</ul>

<h3>Bagaimana kamu menyesuaikan warna tema agar aplikasi Football Shop memiliki identitas visual yang konsisten dengan brand toko?</h3>
<p>
  Dalam aplikasi On Target Football Shop, penyesuaian warna tema dilakukan untuk menciptakan identitas visual yang konsisten dan mudah dikenali oleh pengguna. Pengaturan warna ini dilakukan melalui properti theme di MaterialApp. Pendekatan ini memastikan bahwa seluruh komponen aplikasi secara otomatis mengikuti skema warna yang seragam tanpa perlu diatur satu per satu. Dengan konsistensi tersebut, tampilan aplikasi menjadi lebih profesional dan memiliki karakter visual yang kuat, sekaligus memperkuat citra brand “On Target Football Shop” sebagai aplikasi yang modern dan terintegrasi dengan baik.
</p>

<br>

<h1>Tugas 9</h1>
<hr>

<h3>Jelaskan mengapa kita perlu membuat model Dart saat mengambil/mengirim data JSON? Apa konsekuensinya jika langsung memetakan Map<String, dynamic> tanpa model (terkait validasi tipe, null-safety, maintainability)?</h3>
<p>Model Dart dibutuhkan supaya data dari JSON punya struktur yang jelas, tipe datanya aman, dan mudah dipakai di seluruh aplikasi. Kalau kita langsung pakai Map<String, dynamic> tanpa model, kita rawan salah ketik key, salah tipe data, dan rentan error null-safety yang susah dideteksi saat compile. Selain itu, tanpa model, kode cepat jadi berantakan karena kita harus parsing manual di banyak tempat; akhirnya maintainability buruk dan bug sulit dilacak. Dengan model, validasi tipe otomatis terjadi, IDE bisa memberi hint, dan perubahan struktur backend lebih mudah di-handle.
</p>

<h3>Apa fungsi package http dan CookieRequest dalam tugas ini? Jelaskan perbedaan peran http vs CookieRequest.</h3>
<p>
  Package http dipakai untuk melakukan request HTTP biasa seperti GET atau POST tanpa manajemen cookie atau session. Sementara CookieRequest (dari package pbp_django_auth) dibuat khusus untuk aplikasi Flutter yang butuh autentikasi Django, karena ia otomatis menyimpan dan mengirim cookie session yang diberikan Django saat login. Intinya, http cocok untuk request umum, sedangkan CookieRequest dipakai untuk semua tindakan yang butuh status login atau perlu akses ke endpoint yang dilindungi.
</p>

<h3>Jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.</h3>
<p>
  Karena CookieRequest menyimpan informasi session dan cookie pengguna yang sedang login, maka seluruh bagian aplikasi harus memakai instance yang sama supaya status login tetap konsisten. Kalau setiap widget membuat instance sendiri, maka session tidak akan sama dan Django akan menganggap pengguna belum login, sekalipun widget lain sudah login. Dengan membagikan satu instance global (biasanya lewat Provider), aplikasi memiliki autentikasi yang stabil dan tidak membuat user tiba-tiba “logout sendiri”.
</p>

<h3>Jelaskan konfigurasi konektivitas yang diperlukan agar Flutter dapat berkomunikasi dengan Django. Mengapa kita perlu menambahkan 10.0.2.2 pada ALLOWED_HOSTS, mengaktifkan CORS dan pengaturan SameSite/cookie, dan menambahkan izin akses internet di Android? Apa yang akan terjadi jika konfigurasi tersebut tidak dilakukan dengan benar?</h3>
<p>
  Flutter yang berjalan di emulator Android tidak bisa akses localhost Django secara langsung, sehingga Django harus mengizinkan host 10.0.2.2 agar emulator bisa terhubung. CORS harus diaktifkan agar Django mengizinkan request dari aplikasi Flutter (yang dianggap origin berbeda), dan pengaturan SameSite/cookie diperlukan supaya cookie sesi login bisa dikirim ulang saat melakukan request berikutnya. Di sisi Android, kita perlu permission internet supaya aplikasi bisa melakukan request ke backend. Jika konfigurasi ini salah, aplikasi tidak bisa terkoneksi, login gagal karena cookie tidak dikirim, request diblokir CORS, atau Django menolak karena host tidak dikenali.
</p>

<h3>Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.</h3>
<p>
  Ketika pengguna mengisi form di Flutter, data dikumpulkan dari controller lalu dikirim ke Django lewat request (POST/GET) sesuai endpoint yang disediakan. Django menerima data tersebut, memprosesnya (misalnya menyimpan ke database atau mengembalikan JSON), lalu mengirimkan respons berupa data JSON. Flutter kemudian menerima JSON itu, memetakkan ke model Dart, dan menampilkannya ke UI. Jadi alurnya: input → request → processing Django → JSON response → konversi ke model → tampil di layar.
</p>

<h3>Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.</h3>
<p>
  Pada register atau login, Flutter mengambil input email/username dan password lalu mengirimkannya lewat CookieRequest ke endpoint Django. Django memverifikasi data: untuk register ia membuat user baru, sedangkan untuk login ia mengecek password dan membuat session, lalu mengirimkan cookie session ke Flutter. CookieRequest menyimpan cookie ini, sehingga Flutter dianggap “logged in” di request berikutnya. Setelah login sukses, Flutter akan menampilkan menu atau halaman yang hanya bisa diakses user terautentikasi. Saat logout, Flutter memanggil endpoint logout Django, Django menghapus session/cookie, dan CookieRequest membersihkan data autentikasi sehingga user dianggap sudah keluar.
</p>

<h3>Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).</h3>
<p>
  
</p>

<br>
