# Segmentasi Morfologi Penguin Antarktika Menggunakan K-Means Clustering

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dickyi/kmeans-palmer-penguins/blob/main/UAS_DataMining_KMeans_PalmerPenguins.ipynb)

Repositori ini berisi notebook analisis pendukung artikel:

> Irawan, D., & Thoib, I. *Segmentasi Morfologi Penguin Antarktika Berdasarkan Ukuran Tubuh Menggunakan Algoritma K-Means Clustering*. TEPI: Teknologi, Pendidikan, dan Industri, Institut Teknologi Mojosari.

Penelitian ini mengelompokkan penguin berdasarkan empat ukuran tubuh (panjang paruh, kedalaman paruh, panjang sirip, dan massa tubuh) menggunakan algoritma K-Means, mengevaluasi hasilnya dengan Silhouette Score, lalu memvalidasinya terhadap label spesies yang tidak dipakai saat pemodelan.

## Ringkasan hasil

| Aspek | Hasil |
|---|---|
| Data | 344 penguin, 342 dipakai setelah 2 baris tanpa ukuran tubuh dihapus |
| Preprocessing | Standardisasi *z-score*; tidak ada duplikat maupun *outlier* |
| Jumlah cluster terpilih | k = 3 (Elbow Method, Silhouette Score, dan interpretasi domain) |
| Silhouette Score (k = 2 / k = 3) | 0,5315 / 0,4472 |
| Adjusted Rand Index terhadap spesies | 0,7928 |
| Penguin pada cluster sesuai spesies dominan | 313 dari 342 (91,52%) |

Tiga kelompok morfologi yang terbentuk:

| Cluster | Jumlah | Ciri utama |
|---|---|---|
| 1 | 132 | Bertubuh kecil, paruh pendek dan tebal |
| 2 | 87 | Bertubuh sedang, paruh panjang dan tebal |
| 3 | 123 | Bertubuh besar, paruh panjang dan tipis |

Analisis lanjutan di dalam notebook juga menguji pengaruh standardisasi, jenis kelamin (*sexual dimorphism*), pemilihan fitur, dan stabilitas inisialisasi K-Means.

## Isi repositori

| File | Keterangan |
|---|---|
| `UAS_DataMining_KMeans_PalmerPenguins.ipynb` | Notebook lengkap: pemahaman data, EDA, *preprocessing*, penentuan k, pemodelan K-Means, evaluasi, validasi, dan analisis lanjutan. Seluruh output sudah tersimpan. |

## Cara menjalankan

1. Klik tombol **Open in Colab** di atas, atau unggah notebook ke [Google Colab](https://colab.research.google.com).
2. Pilih **Runtime → Run all**.
3. Dataset dimuat otomatis dari repositori resmi palmerpenguins, sehingga tidak perlu mengunduh data secara manual.
4. Grafik untuk artikel tersimpan otomatis di folder `gambar_jurnal/`.

Angka pada artikel dihasilkan dengan lingkungan berikut:

| Perangkat lunak | Versi |
|---|---|
| Python | 3.13 |
| pandas | 3.0.5 |
| NumPy | 2.5.3 |
| scikit-learn | 1.9.1 |
| matplotlib | 3.11.2 |

K-Means dijalankan dengan `n_init=50` dan `random_state=42`, sehingga hasilnya dapat diulang.

## Dataset

Dataset Palmer Penguins tersedia secara terbuka dengan lisensi CC0: <https://allisonhorst.github.io/palmerpenguins/>

Jika menggunakan data ini, kutip:

- Horst, A. M., Hill, A. P., & Gorman, K. B. (2020). *palmerpenguins: Palmer Archipelago (Antarctica) penguin data* (R package version 0.1.0). https://doi.org/10.5281/zenodo.3960218
- Gorman, K. B., Williams, T. D., & Fraser, W. R. (2014). Ecological sexual dimorphism and environmental variability within a community of Antarctic penguins (genus *Pygoscelis*). *PLoS ONE, 9*(3), e90081. https://doi.org/10.1371/journal.pone.0090081

## Penulis

- **Dicky Irawan**, Program Studi Sistem Informasi, Institut Teknologi Mojosari, Nganjuk (irawandicky300@gmail.com)
- **Imam Thoib**, Institut Teknologi Mojosari, Nganjuk
