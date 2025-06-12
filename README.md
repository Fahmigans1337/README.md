# Analisis Tumpukan Teknologi Aplikasi Ebdesk

Repositori ini berisi dokumentasi hasil analisis tumpukan teknologi (tech stack) yang digunakan oleh dua aplikasi web milik Ebdesk: `isa.ebdesk.com` dan `ima.ebdesk.com`. Analisis ini dilakukan sepenuhnya dari luar (black-box) tanpa akses ke kode sumber server.

---

##  Ringkasan Umum

Kedua aplikasi menunjukkan adanya standarisasi teknologi yang konsisten, menandakan praktik rekayasa perangkat lunak yang baik di dalam tim pengembang.

| Komponen                | `https://isa.ebdesk.com`         | `https://ima.ebdesk.com`          |
| ----------------------- | -------------------------------- | --------------------------------- |
| **Bahasa Backend**      | PHP                              | PHP                               |
| **Framework Backend**   | CodeIgniter (Sangat Mungkin)     | CodeIgniter (Sangat Mungkin)      |
| **Framework Frontend**  | Bootstrap                        | Bootstrap                         |
| **Library Frontend**    | jQuery                           | jQuery, Font Awesome              |
| **Web Server**          | Nginx                            | Nginx                             |
| **Versi PHP Terdeteksi**| Tidak Terdeteksi Secara Publik   | `8.1.13`                          |

---

## 🔬 Detail Analisis per Aplikasi

Berikut adalah rincian teknologi yang teridentifikasi untuk setiap aplikasi.

### 1. [https://isa.ebdesk.com](https://isa.ebdesk.com)

Aplikasi ini merupakan sebuah portal login yang dibangun dengan kombinasi teknologi yang solid dan teruji.

#### **Frontend (Sisi Klien)**

*   **Bootstrap:** Digunakan sebagai kerangka kerja CSS utama untuk membangun layout halaman yang responsif dan terstruktur. Ini terlihat dari penggunaan kelas seperti `.container`, `.row`, `.col-md-*`, dan `.form-control`.
*   **jQuery:** Library JavaScript yang dimuat untuk mempermudah manipulasi DOM dan penanganan event pada halaman.

#### **Backend (Sisi Server)**

*   **PHP:** Bahasa pemrograman utama yang berjalan di server.
*   **CodeIgniter:** Kerangka kerja (framework) PHP yang kemungkinan besar digunakan. Indikasinya adalah struktur aplikasi dan pola yang umum diadopsi oleh framework berbasis MVC ini.

#### **Infrastruktur**

*   **Nginx:** Web server yang bertugas melayani permintaan dari pengguna. Teridentifikasi dari *response header* server.

---

### 2. [https://ima.ebdesk.com](https://ima.ebdesk.com)

Mirip dengan aplikasi sebelumnya, `ima.ebdesk.com` juga merupakan portal login dengan basis teknologi yang hampir identik, namun dengan beberapa detail yang lebih spesifik.

#### **Frontend (Sisi Klien)**

*   **Bootstrap:** Kerangka kerja CSS untuk tata letak antarmuka.
*   **jQuery:** Library JavaScript untuk interaktivitas.
*   **Font Awesome:** Digunakan untuk menampilkan ikon-ikon di dalam form (misalnya, ikon email dan kunci).

#### **Backend (Sisi Server)**

*   **PHP (Versi 8.1.13):** Versi PHP yang digunakan teridentifikasi dengan jelas.
    *   **Bukti:** *Response header* `X-Powered-By: PHP/8.1.13`.
*   **CodeIgniter:** Framework PHP yang diyakini menjadi fondasi aplikasi.
    *   **Bukti:**
        1.  **Struktur URL:** Form login dikirim ke endpoint `/auth/login`, sebuah pola umum `controller/method` pada framework MVC.
        2.  **Keamanan:** Penggunaan token CSRF (`<input type="hidden" name="ebdesk_token">`) adalah fitur keamanan standar pada framework modern seperti CodeIgniter.

#### **Infrastruktur**

*   **Nginx:** Web server yang digunakan.
    *   **Bukti:** *Response header* `Server: nginx`.

---

## 💡 Metodologi Analisis

Analisis ini dilakukan dengan menggunakan metode-metode berikut:

1.  **Inspeksi Kode Sumber Halaman:** Memeriksa file HTML, CSS, dan JavaScript yang diunduh oleh browser untuk mengidentifikasi framework dan library frontend.
2.  **Analisis Jaringan (Network Analysis):** Menggunakan *Developer Tools* pada browser untuk memantau permintaan (requests) dan respons (responses) antara klien dan server.
3.  **Pemeriksaan HTTP Headers:** Menganalisis header yang dikirim oleh server untuk mengidentifikasi teknologi sisi server seperti bahasa pemrograman dan web server.

---

## 🚀 Kesimpulan

Kedua aplikasi Ebdesk (`isa` dan `ima`) dibangun di atas tumpukan teknologi yang populer dan efisien, yaitu **LEMP Stack** (Linux, **Nginx**, **MySQL/MariaDB**, **PHP**), dengan spesialisasi pada:

*   **Framework PHP:** **CodeIgniter**
*   **Framework CSS:** **Bootstrap**

Penggunaan stack yang seragam ini memungkinkan pengembangan dan pemeliharaan yang lebih efisien di seluruh ekosistem produk mereka.

---

## 📜 Lisensi

Analisis ini bersifat informatif dan disediakan apa adanya. Konten ini dilisensikan di bawah [Lisensi MIT](LICENSE).
