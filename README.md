# 📊 Analisis Klaster dan Visualisasi Spasial Pembangunan Provinsi di Indonesia
## 🧠 Deskripsi Proyek
Proyek ini menganalisis tingkat pembangunan antarprovinsi di Indonesia menggunakan kombinasi analisis statistik, pembelajaran mesin, dan data spasial.
Dengan pendekatan PCA (Principal Component Analysis) dan K-Means Clustering, proyek ini mengidentifikasi pola kemiripan antarprovinsi berdasarkan indikator sosial ekonomi utama, serta memvisualisasikannya dalam bentuk peta tematik interaktif.

## 📌 Tujuan Proyek
1. Mengidentifikasi perbedaan dan kemiripan pembangunan antarprovinsi di Indonesia.
2. Mengelompokkan provinsi berdasarkan indikator sosial-ekonomi menggunakan K-Means Clustering.
3. Menggunakan PCA untuk menurunkan dimensi dan menemukan faktor dominan pembangunan.
4. Memvisualisasikan hasil analisis dalam bentuk peta klasterisasi dan grafik korelasi.

## 📊 Data yang Digunakan
| Jenis Data | Deskripsi |
| --- | --- |
| Data Sosial Ekonomi Provinsi | Berisi indikator seperti Jumlah Penduduk, Kepadatan Penduduk, IPM, PDRB, dan Garis Kemiskinan |
| Data Spasial (Shapefile) | Batas wilayah administratif provinsi dan kabupaten di Indonesia |
| Output Analisis | Cluster, PCA1, PCA2, dan hasil regresi antarindikator |

## 🛠️ Library yang Digunakan
````
import pandas as pd
import numpy as np
import geopandas as gpd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
from sklearn.decomposition import PCA
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score
import statsmodels.api as sm
from scipy.stats import zscore
````

## ⚙️ Metodologi
1. Eksplorasi Data (EDA)
Meliputi pemeriksaan nilai hilang, distribusi data, serta korelasi antar variabel.

2. Standardisasi Data
Dilakukan agar semua variabel berada pada skala yang sama sebelum dilakukan klasterisasi.

3. Reduksi Dimensi (PCA)
Digunakan untuk menyederhanakan variabel menjadi komponen utama yang merepresentasikan mayoritas variasi data.

4. Klasterisasi (K-Means)
Menentukan jumlah klaster optimal dengan Elbow Method dan Silhouette Score.

5. Visualisasi Spasial
Hasil klasterisasi divisualisasikan menggunakan peta Indonesia dengan bantuan Geopandas/ArcGIS.

## 📊 Hasil dan Insight

- Provinsi terbagi menjadi 4 klaster utama berdasarkan karakteristik pembangunan.
- Klaster dengan IPM dan PDRB tinggi didominasi provinsi di wilayah barat (Jawa, Bali), sedangkan klaster dengan indikator pembangunan rendah tersebar di kawasan timur Indonesia.
- PCA menunjukkan bahwa dua komponen utama sudah menjelaskan >80% variasi data.
