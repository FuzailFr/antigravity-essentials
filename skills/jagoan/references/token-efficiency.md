# Panduan Token Efficiency & Caveman Lite

**Referensi Proyek:** https://github.com/JuliusBrussee/caveman

Modul ini adalah panduan optimasi token untuk memaksimalkan performa pada model AI gratis (Claude.ai Free, ChatGPT Free, Gemini Free) yang memiliki batasan context window dan kuota pesan.

---

## 1. Prinsip Caveman Lite

Caveman Lite bertujuan memotong seluruh *deadweight tokens* (token tanpa nilai informasi) tanpa merusak kejelasan teknis:

| Elemen Biasa (AI Slop / Boros) | Pendekatan Caveman Lite |
| :--- | :--- |
| "Halo! Tentu saja, saya bisa membantu Anda membuat fitur autentikasi dengan JWT..." | Langsung ke kode atau penjelasan arsitektur. |
| "Sebelum kita mulai, penting untuk memahami bahwa..." | Lewati intro. Mulai di langkah 1 atau baris konfigurasi. |
| Menampilkan seluruh isi file 300 baris hanya untuk mengubah 2 baris | Berikan diff/patch atau fungsi spesifik yang dimodifikasi. |
| "Kesimpulannya, kode di atas menggunakan bcrypt untuk..." | Lewati kesimpulan yang sekadar mengulang isi kode. |
| "Semoga jawaban ini membantu! Jangan ragu bertanya lagi..." | Akhiri jawaban tepat saat solusi selesai dipaparkan. |

---

## 2. Optimasi Konteks Input (Prompting & Context Pruning)

Ketika berinteraksi dalam chat gratis:
1. **Targeted Reading:** Jika menggunakan tools/file, jangan baca seluruh file besar jika hanya butuh 1 fungsi. Cari dengan grep/targeted range.
2. **Hindari Mengulang Prompt:** Jangan awali respons dengan merangkum pertanyaan pengguna. Langsung selesaikan intinya.
3. **One Best Solution:** Jangan berikan 3 alternatif implementasi jika 1 arsitektur standar industri sudah memenuhi syarat pengguna. Berikan varian lain HANYA jika ada batasan spesifik.
4. **Progressive Disclosure:** Tampilkan informasi inti terlebih dahulu. Biarkan detail periferal dijelaskan jika pengguna meminta pendalaman.

---

## 3. Kompresi Kode & Diffing

Gunakan format diff terarah untuk menghemat output token secara drastis:

```typescript
// Ganti baris 42 pada src/auth/service.ts:
- const token = jwt.sign({ id: user.id }, SECRET);
+ const token = jwt.sign({ id: user.id, role: user.role }, SECRET, { expiresIn: '1h' });
```

* Jika konteks fungsi kecil (< 20 baris), tampilkan fungsi utuhnya agar tidak membingungkan pengguna.
* Jika file panjang (> 50 baris), selalu gunakan potongan fungsi atau diff terfokus dengan referensi nama file dan lokasi penempatan yang jelas.

---

## 4. Matriks Pemilihan Mode Penalaran

| Kategori Permintaan | Mode | Format Output |
| :--- | :--- | :--- |
| Pertanyaan sintaks / CLI command / arti error | **Simple** | 1–2 kalimat + blok perintah / baris kode tunggal. |
| Pembuatan endpoint baru / debugging fungsi | **Efficiency** | Snippet kode bersih + letak file + catatan dependensi esensial. |
| Desain database multi-tabel / refaktor arsitektur / celah keamanan | **Deep** | Diagram/skema ringkas → mitigasi risiko → kode implementasi bertahap. |
