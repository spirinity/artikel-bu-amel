# Konteks Penelitian dan Kerangka Latar Belakang Artikel Ilmiah

**Topik:** Perbandingan YOLOv8-OBB dan YOLO11-OBB untuk deteksi kapal pada citra SAR Sentinel-1 di Selat Makassar (ALKI II), menggunakan dataset DSSDD.

> Dokumen kerja untuk membantu penyusunan bagian *Introduction*. Poin yang belum diputuskan diberi catatan agar tidak dianggap sebagai hasil eksperimen atau fakta yang telah dikonfirmasi.

## 1. Identitas dan Arah Penelitian

| Aspek | Konteks penelitian |
|---|---|
| Fokus utama | Deteksi kapal menggunakan *deep learning* |
| Objek | Kapal di perairan Selat Makassar |
| Wilayah studi | Selat Makassar, bagian dari ALKI II |
| Teknologi | *Synthetic Aperture Radar* (SAR) |
| Satelit | Sentinel-1 |
| Dataset pelatihan | DSSDD (*Dual-Polarimetric SAR Ship Detection Dataset*) |
| Model | YOLOv8-OBB dan YOLO11-OBB |
| Pendekatan | *Oriented Bounding Box* (OBB) |
| Jenis penelitian | Eksperimental komparatif |
| Tujuan aplikasi | Mendukung pemantauan aktivitas maritim |
| Publikasi | Artikel ilmiah berbahasa Inggris |

### Dua fokus utama

1. **Perbandingan model:** mengevaluasi performa YOLOv8-OBB dan YOLO11-OBB untuk mendeteksi kapal pada citra SAR.
2. **Penerapan wilayah studi:** menerapkan kedua model pada citra Sentinel-1 di Selat Makassar serta menganalisis hasil deteksinya.

**Catatan:** Jangan mengasumsikan YOLO11-OBB lebih baik sebelum hasil eksperimen tersedia.

## 2. Dataset DSSDD

Referensi dataset: *A Dual-Polarimetric SAR Ship Detection Dataset and a Memory-Augmented Autoencoder-Based Detection Method*.

- Sumber: Sentinel-1 IW SLC.
- Polarisasi: VV dan VH.
- Jumlah citra awal yang dilaporkan: 50.
- Jumlah *image chips* yang dilaporkan: 1.236.
- Jumlah objek kapal yang dilaporkan: 3.540.
- Dimensi chip: 256 × 256 piksel.
- Jenis anotasi: *rotated bounding box* (RBox) dan *bounding box* (BBox).
- Representasi citra: *pseudo-color* dari informasi polarimetrik.

Artikel: https://pmc.ncbi.nlm.nih.gov/articles/PMC8709314/

**Implikasi metodologis:** DSSDD dibangun dari SLC dan memanfaatkan informasi polarimetrik. Jika citra pengujian Selat Makassar berasal dari GRD, representasi datanya mungkin berbeda. Perlu direncanakan cara menyelaraskan format input dan menguji potensi *domain shift*.

## 3. Alur Argumentasi Introduction

1. **Urgensi maritim Indonesia:** pentingnya pemantauan aktivitas pelayaran dan kapal.
2. **Selat Makassar dan ALKI II:** signifikansi jalur pelayaran sebagai wilayah studi.
3. **Sentinel-1 SAR:** pengamatan siang/malam dan kemampuan dalam berbagai kondisi cuaca.
4. **Tantangan deteksi kapal SAR:** *speckle noise*, *sea clutter*, kapal kecil, dan variasi orientasi.
5. **YOLO berbasis OBB:** deteksi otomatis dengan kotak yang mengikuti orientasi kapal.
6. **DSSDD dan penelitian terdahulu:** dataset SAR dual-polarization dan karya terkait.
7. **Research gap:** perlunya evaluasi komparatif dua model dengan protokol yang sebanding dan uji penerapan di wilayah studi.
8. **Kontribusi:** hasil komparasi dan analisis deteksi di Selat Makassar.

## 4. Rencana Isi Per Paragraf

| Paragraf | Fokus | Pokok argumentasi |
|---|---|---|
| 1 | Aktivitas maritim Indonesia | Pemantauan kapal penting dalam pengawasan dan pengelolaan maritim. |
| 2 | ALKI II dan Selat Makassar | Koridor pelayaran ini relevan untuk penelitian pemantauan kapal. |
| 3 | Sentinel-1 SAR | Teknologi radar relevan sebagai sumber pengamatan maritim. |
| 4 | Tantangan deteksi | Hamburan radar, speckle, clutter, ukuran, dan orientasi kapal. |
| 5 | Deep learning dan YOLO-OBB | OBB dapat merepresentasikan orientasi kapal secara lebih spesifik daripada HBB. |
| 6 | DSSDD dan penelitian sebelumnya | Dataset dual-polarization dan metode terdahulu menyediakan landasan penelitian. |
| 7 | Research gap | Perbandingan model dan analisis generalisasi membutuhkan pengujian terkendali. |
| 8 | Tujuan dan kontribusi | Merangkum rancangan eksperimen dan keluaran penelitian. |

### Paragraf 1–2: Urgensi dan lokasi

Mulai dari kebutuhan pemantauan maritim di Indonesia, lalu persempit ke Selat Makassar sebagai bagian ALKI II. Hindari klaim peningkatan trafik kapal atau angka insiden tanpa data pendukung.

### Paragraf 3: SAR Sentinel-1

Jelaskan keunggulan pengamatan radar dibanding optik, termasuk kemampuan pengamatan siang/malam dan berbagai kondisi cuaca. Tetap akui keterbatasan pengamatan SAR.

### Paragraf 4: Tantangan teknis

Bahas *speckle*, *sea clutter*, kapal berukuran kecil, variasi intensitas hamburan dan orientasi, serta kapal berdekatan.

### Paragraf 5: YOLOv8-OBB dan YOLO11-OBB

Perkenalkan YOLO sebagai pendekatan deteksi objek, lalu OBB sebagai representasi kotak berorientasi. Jelaskan alasan perbandingan kedua model, bukan klaim keunggulan satu versi.

### Paragraf 6: Studi terdahulu

Bahas DSSDD, studi kapal kecil SAR seperti LS-SSDD-v1.0, serta penelitian relevan lainnya. Uraikan temuan dan keterbatasan setiap studi.

### Paragraf 7: Research gap

*Hipotesis gap yang masih perlu divalidasi dari literatur:* perlunya evaluasi komparatif YOLOv8-OBB dan YOLO11-OBB pada dataset SAR dual-polarization serta uji penerapan pada scene Sentinel-1 Selat Makassar. Jangan menulis bahwa belum pernah ada studi serupa tanpa tinjauan pustaka menyeluruh.

### Paragraf 8: Tujuan dan kontribusi

Nyatakan perbandingan model, metrik evaluasi, dan penerapan pada data wilayah studi. Jika data Selat Makassar tidak memiliki label referensi, batasi klaim di wilayah tersebut pada visualisasi/analisis prediksi, bukan akurasi tervalidasi.

## 5. Pertimbangan Metodologi Sebelum Menulis

| Keputusan | Hal yang perlu dipastikan |
|---|---|
| Produk citra wilayah studi | SLC atau GRD? |
| Representasi input | *Pseudo-color* DSSDD atau komposit/representasi lain? |
| Skenario uji | Evaluasi hanya DSSDD atau juga anotasi acuan Selat Makassar? |
| Varian model | YOLOv8n-OBB vs YOLO11n-OBB atau varian ukuran lain? |
| Fair comparison | Pembagian data, augmentasi, jumlah epoch, ukuran input, dan perangkat komputasi sebanding. |

DSSDD menggunakan data SLC. Jika Sentinel-1 Selat Makassar memakai GRD, informasi fase kompleks yang digunakan untuk fitur tertentu pada SLC tidak tersedia. Hal ini harus dijelaskan sebagai masalah kompatibilitas representasi dan kemungkinan *domain shift*.

## 6. Rumusan Masalah Sementara

1. Bagaimana performa YOLOv8-OBB dan YOLO11-OBB dalam mendeteksi kapal menggunakan dataset DSSDD?
2. Bagaimana perbandingan kedua model berdasarkan metrik ketepatan deteksi dan efisiensi inferensi?
3. Bagaimana kemampuan kedua model dalam mendeteksi kapal pada citra SAR Sentinel-1 di Selat Makassar sebagai bagian ALKI II?

## 7. Tujuan Penelitian Sementara

1. Mengimplementasikan YOLOv8-OBB dan YOLO11-OBB untuk deteksi kapal pada citra SAR.
2. Membandingkan kedua model dengan prosedur eksperimen yang konsisten.
3. Menerapkan kedua model dan menganalisis hasil deteksi pada citra Sentinel-1 Selat Makassar.

**Metrik yang dapat digunakan:** precision, recall, F1-score, mAP@50, mAP@50:95 untuk OBB, dan waktu inferensi/FPS jika relevan.

## 8. Persyaratan Artikel Jurnal

- Bahasa Inggris akademik.
- Minimum 6 halaman.
- Abstrak 200–300 kata yang meliputi latar belakang, kontribusi, metode, hasil, dan kesimpulan.
- Struktur: Title, Abstract, Keywords, Introduction, Methods, Results and Discussion, Conclusions, References.
- Elemen pelengkap sesuai template: Funding, Acknowledgment, Conflict of Interest, dan lainnya.
- Minimal 60 referensi relevan, menggunakan IEEE Style.
- Sekurang-kurangnya 80% referensi berasal dari lima tahun terakhir sesuai interpretasi jurnal (untuk 60 referensi berarti sedikitnya 48 referensi baru).
- Prioritaskan artikel jurnal internasional dengan DOI, bukan halaman web atau blog.
- Similarity di bawah 25% menurut aturan jurnal.
- Figure PNG/JPEG dengan ketentuan 600–1200 dpi dari jurnal; jangan mengandalkan screenshot berkualitas rendah.
- Tabel dibuat sebagai tabel asli.
- Semua gambar, tabel, dan persamaan diberi nomor, dirujuk, dan dianalisis dalam teks.
- Format akhir mengikuti template jurnal, termasuk gaya persamaan dan daftar pustaka.

## 9. Referensi Awal untuk Ditelusuri

> Daftar awal, **bukan** daftar 60 referensi final. Periksa metadata bibliografi, DOI, kualitas sumber, dan relevansi sebelum mengutip.

1. DSSDD — *A Dual-Polarimetric SAR Ship Detection Dataset and a Memory-Augmented Autoencoder-Based Detection Method*: https://pmc.ncbi.nlm.nih.gov/articles/PMC8709314/
2. Tinjauan deteksi kapal SAR — *Deep Learning for SAR Ship Detection: Past, Present and Future*: https://www.mdpi.com/2072-4292/14/11/2712
3. Dataset kapal kecil SAR — *LS-SSDD-v1.0: A Deep Learning Dataset Dedicated to Small Ship Detection*: https://www.mdpi.com/2072-4292/12/18/2997
4. Studi deteksi kapal SAR modern — *MSA-DET*: https://www.mdpi.com/1424-8220/26/13/3970
5. Sumber kontekstual ALKI II: https://ijtech.eng.ui.ac.id/article/view/7106
6. Dokumentasi teknis OBB (bukan pengganti jurnal): https://docs.ultralytics.com/tasks/obb/

## 10. Benang Merah Penelitian

**Urgensi pemantauan maritim → Selat Makassar/ALKI II → Sentinel-1 SAR → tantangan deteksi kapal → YOLO-OBB → DSSDD → research gap → kontribusi penelitian.**

Klaim ilmiah yang ingin dibangun: pemantauan kapal pada jalur strategis memerlukan metode deteksi otomatis yang relevan dengan karakteristik citra SAR. Perbandingan YOLOv8-OBB dan YOLO11-OBB pada DSSDD, beserta penerapannya pada scene Sentinel-1 Selat Makassar, dapat menghasilkan bukti empiris tentang kinerja dan keterbatasan kedua model.

**Status:** Dokumen konteks dan kerangka; bukan naskah Introduction final dan belum memuat hasil eksperimen.
