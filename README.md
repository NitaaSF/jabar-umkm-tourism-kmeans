# 📊 Pengelompokan Kabupaten/Kota di Jawa Barat Berdasarkan Indikator UMKM dan Pariwisata Menggunakan K-Means

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8%2B-blue.svg" alt="Python Version">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-orange.svg" alt="Pandas">
  <img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-f7931e.svg" alt="Scikit-Learn">
  <img src="https://img.shields.io/badge/Folium-Spatial%20Mapping-77bb41.svg" alt="Folium">
  <img src="https://img.shields.io/badge/Status-Completed-success.svg" alt="Status">
</p>

Repositori ini berisi kode sumber dan pipeline analisis data untuk mengevaluasi dampak pandemi COVID-19 terhadap sektor UMKM dan Pariwisata di 27 Kabupaten/Kota di Provinsi Jawa Barat. Analisis dibagi menjadi tiga fase periode waktu: **Pra-Pandemi (2019)**, **Masa Pandemi (2020–2021)**, dan **Pasca-Pandemi (2022–2023)**.

---

## 🚀 Fitur Utama & Alur Analisis
1. **Pembersihan & Integrasi Data:** Menggabungkan multi-sheet data sekunder dari Badan Pusat Statistik / Dinas terkait (Master Data UMKM & Pariwisata).
2. **Kategori Periode Waktu:** Pemetaan otomatis berdasarkan tahun pengamatan (`Pra-COVID`, `Saat-COVID`, `Pasca-COVID`).
3. **Feature Scaling:** Normalisasi rentang fitur menggunakan `MinMaxScaler` untuk menyetarakan bobot variabel numerik (Jumlah UMKM, Tenaga Kerja UMKM, Jumlah Hotel, Pengunjung Nusantara, dan Pengunjung Mancanegara).
4. **Unsupervised Machine Learning (K-Means Clustering):** 
   * Penentuan jumlah klaster optimal ($k=3$) menggunakan **Elbow Method**.
   * Validasi model lanjutan menggunakan **Silhouette Score**, **Davies–Bouldin Index**, dan **Calinski–Harabasz Index**.
   * Uji stabilitas klaster dengan *Adjusted Rand Index (ARI)* pada berbagai inisialisasi acak (`random_state`).
5. **Visualisasi Spasial:** Pemetaan interaktif sebaran klaster wilayah menggunakan pustaka `Folium` (`map_cluster_*.html`).

---

## 📂 Struktur Repositori
```text
├── Master Data Dashboard.xlsx         # Dataset indikator pariwisata & hotel
├── Master Data Nita (2).xlsx          # Dataset indikator UMKM & tenaga kerja
├── hasil_cluster_fix_per_periode.csv  # Hasil akhir pengelompokan per kabupaten/tahun
├── perbandingan_cluster_periode.csv   # Tabel pivot perbandingan pergeseran klaster
├── cluster_map_jabar.html             # Peta sebaran spasial interaktif
├── main.ipynb / script.py             # Notebook utama pemrosesan data & pemodelan
└── README.md                          # Dokumentasi proyek

⚙️ Persyaratan Sistem & Instalasi
1. Pastikan Anda telah memasang pustaka Python berikut sebelum menjalankan skrip:
pip install pandas numpy scikit-learn matplotlib seaborn geopy folium openpyxl
2. Jalankan aplikasi Streamlit melalui terminal:
streamlit run app.py

📈 Metodologi & Hasil Singkat
- Metode: Unsupervised Learning (K-Means Clustering) dengan normalisasi MinMaxScaler.
- Evaluasi: Menggunakan Silhouette Score dan validasi struktur klaster untuk memastikan pemisahan wilayah yang optimal.
- Kategori Klaster: Pengelompokan dibagi menjadi 3 kategori utama (Rendah, Sedang, Tinggi) guna melihat tingkat ketahanan sektor UMKM dan pariwisata daerah.

📝 Lisensi
Proyek ini bersifat open-source di bawah lisensi MIT. Silakan gunakan dan kembangkan kembali!
