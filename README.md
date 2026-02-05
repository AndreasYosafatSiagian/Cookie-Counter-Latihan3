Eksperimen 1: Persistence Test
- Cookies: [masih ada / hilang] ___Masih ada
- LocalStorage: [masih ada / hilang] ___Masih ada
- SessionStorage: [masih ada / hilang] ___Hilang
==========================================================================================================================

Eksperimen 2: Tab Isolation

Nilai counter di tab baru: 0
Nilai counter di tab lama: 5
Kesimpulan:
SessionStorage adalah tab-isolated karena setiap tab memiliki session sendiri.
==========================================================================================================================

Eksperimen 3: Storage Size Comparison

Cookies        :  4 KB
LocalStorage   :  5 MB
SessionStorage :  5 MB
==========================================================================================================================

Eksperimen 4: Decision Quiz

- Skenario 1: Menyimpan data login sementara per tab
SessionStorage
Alasan: SessionStorage bersifat tab-isolated dan akan hilang saat tab ditutup. Cocok untuk menyimpan login sementara agar tidak tersimpan di browser lama atau tab lain.
- Skenario 2: Menyimpan preferensi tema agar tetap tersimpan saat browser ditutup
LocalStorage
Alasan: LocalStorage bersifat persisten hingga dihapus secara manual. Jadi preferensi seperti tema gelap/terang akan tetap ada walau browser ditutup.
- Skenario 3: Menyimpan token sesi agar otomatis dikirim ke server tiap request
Cookies
Alasan: Cookies otomatis dikirim ke server saat request dibuat. SessionStorage atau LocalStorage tidak dikirim otomatis ke server, jadi cookies adalah pilihan tepat untuk token otentikasi.
- Skenario 4: Menyimpan data sementara yang besar dan tidak perlu dikirim ke server
Pilihan storage: SessionStorage atau LocalStorage tergantung kebutuhan tab
Jika data hanya untuk tab saat ini, gunakan SessionStorage (hilang saat tab ditutup)
Jika data harus tetap ada saat reload halaman atau membuka tab baru, gunakan LocalStorage (persisten, kapasitas besar dibanding cookies)
==========================================================================================================================
Pertanyaan Refleksi
1. Mengapa session token TIDAK boleh disimpan di LocalStorage?
Karena LocalStorage bisa diakses oleh JavaScript, jadi kalau terjadi XSS, attacker bisa dengan mudah mencuri session token.
2. Apa keuntungan SessionStorage untuk multi-step form dibanding LocalStorage?
Keuntungannya:
- Data tidak nyangkut lama
- Tidak bentrok dengan tab lain
- Lebih aman untuk data sementara (misalnya data form)
3. Jika kamu membuat aplikasi todo list offline-first, storage mana yang akan kamu gunakan dan mengapa?
Saya akan pakai LocalStorage (atau IndexedDB kalau datanya banyak), karena:
- Data harus tetap ada walaupun browser ditutup
- Cocok untuk menyimpan daftar todo secara offline
- Mudah diakses dan digunakan






Cookie Counter Latihan 3
Project ini dibuat untuk latihan pemahaman cookie dan keamanan web. Berisi simulasi vulnerable dan secure untuk pembelajaran.