# Panduan Keamanan & Rekayasa Aman (Security by Design)

Panduan praktis pencegahan celah keamanan dan integrasi API yang aman.

---

## 1. Pencegahan Celah Keamanan Populer (OWASP Essentials)

* **SQL / NoSQL Injection:**
  * Wajib gunakan *parameterized queries* atau fitur sanitasi ORM/Query Builder.
  * Dilarang melakukan string concatenation pada query SQL (`"SELECT * FROM users WHERE id = " + id`).
* **Cross-Site Scripting (XSS):**
  * Hindari rendering raw HTML langsung (`dangerouslySetInnerHTML`, `v-html`, atau `innerHTML`) kecuali data telah disanitasi dengan pustaka seperti DOMPurify.
  * Pasang header keamanan dasar (`Content-Security-Policy`, `X-Content-Type-Options: nosniff`).
* **Broken Authentication & Authorization:**
  * Validasi otorisasi selalu di sisi server. Menyembunyikan tombol UI bukan bentuk proteksi.
  * Lindungi dari IDOR (*Insecure Direct Object References*): pastikan pengguna hanya bisa memanipulasi resource miliknya sendiri (`WHERE user_id = current_user.id`).
  * Hash password menggunakan algoritma modern dan kuat seperti `Argon2id` atau `bcrypt` dengan salt memadai.
* **CSRF (Cross-Site Request Forgery):**
  * Terapkan token CSRF untuk form berbasis session atau gunakan atribut `SameSite=Lax` / `SameSite=Strict` pada cookie auth.
* **Server-Side Request Forgery (SSRF):**
  * Jika aplikasi mengunduh URL dari input user, lakukan validasi alamat IP untuk memblokir IP lokal/internal (`127.0.0.1`, `10.0.0.0/8`, `169.254.169.254`).

---

## 2. Pengelolaan Rahasia (Secrets & Credentials)

1. Jangan pernah melakukan hardcode terhadap token, password, atau private key di dalam file kode sumber atau git history.
2. Gunakan Environment Variables (`.env`) dan sediakan file contoh `.env.example` tanpa nilai asli.
3. Tambahkan `.env` dan file sertifikat ke `.gitignore`.

---

## 3. Integrasi AI & Layanan Pihak Ketiga

Ketika menghubungkan model AI (OpenAI, Gemini, Anthropic, dll.):
* **Simpan Kunci Server-Side:** API key dilarang dipanggil langsung dari antarmuka browser publik/frontend.
* **Perlakukan Output AI Sebagai Data Tak Tepercaya:** Validasi skema output (misal dengan Zod) sebelum mengeksekusi aksi lanjutan atau menyimpannya ke database.
* **Penanganan Kegagalan (Resilience):** Pasang batasan *timeout* dan mekanisme *exponential backoff* untuk menangani *rate limits* (HTTP 429).
* **Proteksi Prompt Injection:** Batasi akses model ke tool sistem yang destruktif dan sanitasi input pengguna sebelum dimasukkan ke dalam prompt sistem.

---

## 4. Sikap Faktual Terhadap Keamanan

* Jangan pernah mengklaim sebuah sistem "100% aman" atau "kebal peretasan".
* Bedakan antara rekomendasi teoretis dan pengujian penetrasi nyata.
