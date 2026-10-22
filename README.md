# Simulator Kelayakan Investasi — RSP UI

Website statis satu file (`index.html`) untuk menguji kelayakan rencana pengembangan
rumah sakit dan menganalisis utilisasi rawat inap. Semua tampilan (CSS) dan logika
(JavaScript) sudah ada di dalam `index.html` — tidak perlu folder atau file lain.

**Fitur**

- **Kelayakan investasi** — 3 langkah: uraian bebas → worksheet asumsi → hasil.
  - Parameter (CAPEX, TT, BOR, tarif, tahun target) dan kategori terbaca otomatis saat mengetik.
  - Skema pendanaan internal, pinjaman, KSO-BLT; tarif tunggal atau per segmen.
  - NPV, IRR, payback, ROI, BEP, DSCR, status kelayakan, perbandingan skenario pesimis/moderat/optimis.
  - Grafik arus kas interaktif, tabel proyeksi, unduh CSV, cetak.
- **Utilisasi & pendapatan** — slider BOR, indikator BTO/TOI/AVLOS dengan penanda rentang ideal
  Barber-Johnson, grafik yang bisa diseret, lalu kirim hasilnya ke worksheet kelayakan.
- Tema terang/gelap, responsif untuk ponsel, input terakhir tersimpan di browser.

## Menjalankan di komputer

Klik dua kali `index.html` — terbuka di browser. Tidak perlu instalasi.

## Publikasi ke GitHub Pages

1. Masuk ke <https://github.com> → **New repository**, misalnya `simulator-kelayakan`, pilih **Public**.
2. Di halaman repo, klik **uploading an existing file**, pilih `index.html` (dan `README.md` bila mau),
   lalu **Commit changes**.
3. **Settings → Pages** → *Source* = **Deploy from a branch**, branch `main`, folder `/ (root)` → **Save**.
4. Tunggu 1–2 menit. Alamatnya muncul di halaman yang sama, biasanya
   `https://<username>.github.io/simulator-kelayakan/`.

Untuk memperbarui situs: buka `index.html` di repo → ikon pensil/**Upload files** → unggah versi baru.

## Lokasi kode di dalam `index.html`

- `<style>` — seluruh tampilan (warna ada di bagian `:root` paling atas).
- `<script>` pertama — **model**: asumsi baseline per kategori (`CATEGORIES`), skenario,
  rentang ideal, dan rumus NPV/IRR/payback/BEP/BOR.
- `<script>` kedua — **UI**: navigasi, worksheet, grafik, Mode Utilisasi.

## Catatan

Prototipe ilustratif. Ekstraksi parameter dari teks memakai pencocokan kata kunci sederhana;
semua nilai tetap perlu dikonfirmasi di worksheet.
