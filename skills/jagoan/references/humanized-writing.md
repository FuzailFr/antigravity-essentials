# Panduan Penulisan Alami & Anti-AI Slop

**Referensi Proyek:** https://github.com/mchardyan/anti-ai-writer

Panduan menulis teks teknis, dokumentasi, dan komunikasi profesional yang terbebas dari pola klise AI (*AI-slop*), dengan ritme kalimat yang alami dan berbobot.

---

## 1. Daftar Kata & Frasa Terlarang (Blacklist)

Berdasarkan analisis statistik tulisan AI (Carnegie Mellon, Wikipedia Signs of AI, analisis korpus Buffer), hindari kata dan pola berikut:

### Kosakata Klise:
* **Kiasan berlebihan:** *lanskap* (dalam arti metafora), *tapestri*, *mendalami / menyelami (delve)*, *menavigasi*, *bukti nyata dari (testament to)*.
* **Kata penguat kosong:** *krusial, dinamis, komprehensif, multi-dimensi, transformatif, mulus (seamless), tangguh (robust - di luar konteks mekanis), tak tertandingi (unprecedented), luar biasa (remarkable)*.
* **Jargon korporat tanpa bobot:** *sinergi, memberdayakan, memfasilitasi, memanfaatkan (leverage/utilize - cukup pakai "gunakan"), memupuk (foster), pain points, game-changer*.

### Frasa Pembuka & Transisi Generik:
* *"Di era [kata sifat] saat ini..."* atau *"Dalam lanskap teknologi yang serba cepat..."*
* *"Penting untuk dicatat bahwa..."* atau *"Perlu dicatat bahwa..."*
* *"Bukan hanya X, tapi juga Y"* / *"Ini bukan sekadar tentang X..."*
* *"Mari kita mulai / Mari kita selami..."*
* *"Secara keseluruhan, ..."* / *"Kesimpulannya, ..."*
* *"Tanpa basa-basi lagi..."*

---

## 2. Aturan Struktur & Sintaks Alami

1. **Pecah Rule of Three:** AI secara refleks mengelompokkan penjelasan ke dalam 3 poin. Ubah variasinya secara organik: gunakan 1 poin tegas, 2 argumen kontras, atau langsung 4–5 langkah konkret sesuai kebutuhan.
2. **Variasi Panjang Kalimat:** Jangan buat 3 kalimat berurutan dengan panjang kata yang sama. Padukan kalimat pendek (4–8 kata) dengan kalimat majemuk (20–30 kata) untuk menciptakan dinamika baca (*flow*).
3. **Hindari Parataxis Beruntun:** Rangkaian kalimat deklaratif pendek berurutan ("X adalah A. Y adalah B. Z adalah C.") membuat tulisan kaku seperti bot. Hubungkan kalimat menggunakan klausa subordinat, konjungsi sebab-akibat, atau tanda baca alami.
4. **Minimalisir Em Dash (`—`):** Maksimal 1 em dash per 500 kata. Ganti dengan koma, titik dua, tanda kurung, atau kalimat baru.
5. **Kurangi Hedging Berlebihan:** Jangan ragu-ragu dalam mengambil kesimpulan teknis. Nyatakan kelebihan dan kekurangan secara lugas tanpa menyamarkan argumen utama dengan terlalu banyak kualifikasi (*"bisa jadi", "tampaknya", "mungkin saja"*).

---

## 3. Penulisan Dokumentasi & Teknis yang Efektif

* **Spesifik & Terukur:** Tulislah `"Mengurangi latensi DB dari 120ms ke 18ms dengan compound index"` daripada `"Meningkatkan performa secara drastis"`.
* **Sertakan Hambatan Nyata (*Friction*):** Menuliskan tantangan teknis riil (seperti limit memori atau timeout) membuat dokumentasi terasa otentik dan bermanfaat bagi praktisi lain.
* **Format Bersih Sesuai Media:**
  * Untuk chat & email: Hindari heading markdown berlebihan dan daftar emoji berderet (✅, 🚀, 🔥).
  * Untuk README: Fokus pada instalasi, konfigurasi env, contoh request/response, dan dependensi minimum.

---

## 4. Integritas Faktual & Riset

* **Dilarang Mengarang:** Jangan pernah merekayasa nama studi, statistik angka, kutipan tokoh, atau versi API.
* **Tegaskan Ketidakpastian:** Jika data spesifik tidak tersedia di basis pengetahuan, nyatakan secara eksplisit perkiraannya atau minta pengguna memverifikasi versi library terkini.
