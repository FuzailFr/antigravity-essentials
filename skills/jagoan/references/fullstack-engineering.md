# Panduan Rekayasa Perangkat Lunak Full-Stack

Panduan standar arsitektur dan penulisan kode terpadu untuk berbagai stack teknologi.

---

## 1. Adaptasi Stack & Konvensi

1. **Stack Agnostic:** Jangan pernah memaksakan framework (misal memaksakan Next.js jika proyek sudah memakai Laravel atau Express). Deteksi bahasa, manajer paket, dan konfigurasi yang ada.
2. **Preserve Conventions:** Ikuti gaya penamaan (camelCase vs snake_case), pola arsitektur (MVC, Clean Architecture, Feature-based), dan versi dependency yang aktif pada repositori.
3. **No Phantom Dependencies:** Jangan mengimpor library baru jika utilitas bawaan bahasa atau pustaka yang sudah terpasang dapat menyelesaikannya dengan baik.

---

## 2. Lapisan Arsitektur (Layer Responsibilities)

* **Controller / Route Handler:**
  * Validasi payload masuk (menggunakan Zod, Joi, FormRequest, atau skema bahasa terkait).
  * Teruskan data bersih ke Service Layer.
  * Kembalikan kode status HTTP yang semantik (`200 OK`, `201 Created`, `400 Bad Request`, `401 Unauthorized`, `404 Not Found`, `500 Internal Error`).
* **Service / Business Logic Layer:**
  * Tempat seluruh aturan logika bisnis dieksekusi.
  * Hindari query basis data mentah langsung di controller jika proyek memisahkan service layer.
* **Data Access / Repository Layer:**
  * Gunakan ORM/Query Builder secara efisien.
  * Waspadai masalah performa umum seperti *N+1 Query Problem*. Gunakan `eager loading` (`join` atau `include`).
  * Indexing: Pastikan kolom yang sering difilter (`WHERE`), diurutkan (`ORDER BY`), atau di-foreign key memiliki indeks.

---

## 3. Kontrak API & Tipe Data Konsisten

* Gunakan definisi tipe yang seragam antara Backend dan Frontend (misal TypeScript types/interfaces, OpenAPI spec, atau DTO).
* Struktur respons standar yang dianjurkan:
```json
{
  "success": true,
  "data": { ... },
  "message": "Deskripsi singkat jika diperlukan"
}
```
* Respons error harus informatif namun tidak membocorkan informasi sensitif (seperti stack trace server atau kredensial).

---

## 4. Frontend & Antarmuka Pengguna

* **State Management:** Prioritaskan local state (useState/signal) kecuali data memang dibutuhkan lintas komponen global.
* **Loading, Empty, & Error States:** Setiap komponen yang melakukan panggilan asynchronous wajib menangani ketiga state ini agar antarmuka tidak rusak (*graceful degradation*).
* **Aksesibilitas (a11y):** Gunakan elemen semantik HTML (`<nav>`, `<main>`, `<button>` bukan `<div onClick>`).
