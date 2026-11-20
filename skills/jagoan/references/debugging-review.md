# Panduan Debugging & Code Review

Panduan sistematis untuk menemukan akar masalah (RCA) dan melakukan audit kode yang berbobot.

---

## 1. Alur Investigasi Debugging (Root Cause Analysis)

Hindari menebak-nebak (*guess-and-check*). Ikuti lima langkah berikut:

```
[1. Pahami Gejala] → [2. Isolasi Lokasi] → [3. Bukti Akar Masalah] → [4. Perbaikan Minimal] → [5. Verifikasi]
```

1. **Pahami Gejala & Error:** Baca pesan error lengkap, status code, dan baris stack trace. Pisahkan fakta dari asumsi.
2. **Isolasi Aliran Data:** Lacak dari mana input masuk dan di titik mana nilai menjadi tidak valid (`null`, `undefined`, atau format salah).
3. **Identifikasi Akar Masalah:** Tentukan mengapa bug terjadi (misal: *race condition*, tipe data tidak cocok, off-by-one, atau unhandled exception).
4. **Terapkan Perbaikan Minimal:** Perbaiki akar masalahnya langsung tanpa merombak file atau fungsi lain yang tidak terkait.
5. **Verifikasi:** Tentukan skenario pengujian untuk memastikan bug hilang dan tidak menimbulkan efek samping (*side effects*).

---

## 2. Checklist & Prioritas Code Review

Saat meninjau kode, prioritaskan dampak nyata daripada sekadar preferensi estetika:

### Prioritas 1: Bug & Kesalahan Logika (Logic Errors)
* Penanganan kondisi batas (*edge cases* seperti array kosong, string kosong, null).
* Eksekusi asinkron (*unhandled promises*, hilangnya `await`, *race conditions*).
* Kebocoran memori (*unclosed connections*, *event listeners* yang tidak di-cleanup).

### Prioritas 2: Celah Keamanan (Security Risks)
* Validasi input tidak memadai (potensi SQLi, XSS, SSRF).
* Celah otorisasi (akses data pengguna lain tanpa verifikasi session/role).
* Data sensitif bocor di log atau client payload.

### Prioritas 3: Kinerja (Performance)
* Loop tidak efisien (kompleksitas $O(n^2)$ pada dataset besar).
* Query database berulang (*N+1 problem*).
* Ukuran bundle atau rendering berlebihan pada frontend.

### Prioritas 4: Risiko Regresi & Maintainability
* Apakah perubahan ini memecahkan kontrak API yang sudah digunakan klien lain?
* Keterbacaan alur logika dan kejelasan penamaan variabel/fungsi.

---

## 3. Format Laporan Review

Gunakan format padat berikut:

```markdown
- [SEVERITY] Nama Masalah (File:Baris)
  Dampak: Penjelasan risiko nyata dalam 1 kalimat.
  Koreksi: Baris perbaikan atau diff konkret.
```

**Tingkat Keparahan:**
* **`[HIGH]`**: Celah keamanan eksploitatif, kehilangan data, atau aplikasi crash/rusak total.
* **`[MEDIUM]`**: Bug logika fungsional dengan dampak terbatas atau performa lambat signifikan.
* **`[LOW]`**: Peningkatan keterbacaan kode, potensi refaktor kecil, atau inkonsistensi minor.
