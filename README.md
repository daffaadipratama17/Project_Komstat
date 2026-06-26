```markdown
# SPASI 📊 (Smart Statistical Planning System)

**SPASI (Smart Statistical Planning System)** adalah aplikasi berbasis web yang dibangun menggunakan **R Shiny** dan **bslib** (dengan tema *Lux*). Aplikasi ini dirancang untuk membantu mahasiswa, peneliti, dan praktisi statistika dalam melakukan **Analisis Kekuatan Uji (Power Analysis)**, menentukan ukuran sampel minimum secara objektif, melakukan analisis sensitivitas, serta menyusun narasi metodologi penelitian secara otomatis.

Aplikasi ini dikembangkan khusus sebagai proyek final untuk mata kuliah **Komputasi Statistika (Komstat)** di Program Studi **Statistika, Universitas Negeri Jakarta**.

---

## 🚀 Fitur Utama

Aplikasi SPASI dilengkapi dengan 4 panel navigasi utama:

1. **Estimator (Power Analysis)**
   * Menghitung ukuran sampel minimum secara *A priori* berdasarkan jenis uji, tingkat signifikansi ($\alpha$), dan kekuatan uji (*Statistical Power* / $1-\beta$) yang diinginkan.
   * Dilengkapi dengan visualisasi **Power Curve** interaktif berbasis `ggplot2`.
   * Menyediakan **Protocol of Power Analyses** berupa log riwayat kalkulasi terstruktur lengkap dengan penanda waktu (*timestamp*).

2. **Sensitivity Analysis**
   * Menyediakan **Heatmap Ukuran Sampel** untuk melihat perpaduan berbagai nilai *Effect Size* dan tingkat *Power*.
   * Menyediakan **Grafik Hubungan Effect Size & Sample Size** (Line Chart) untuk menganalisis sensitivitas desain penelitian.
   * Menampilkan **Tabel Matriks Power** dalam format tabel interaktif yang siap disalin.

3. **Effect Size Calculator**
   * Menghitung nilai kalkulasi **Cohen's d** secara otomatis berdasarkan nilai rerata (*Mean*) Kelompok 1, Kelompok 2, dan *Standard Deviation (SD) Pooled*.
   * Mengklasifikasikan kekuatan efek berdasarkan kriteria Cohen (*Negligible*, *Small*, *Medium*, *Large*).
   * Fitur **"Kirim ke Power Analysis"** untuk memindahkan nilai efek yang terhitung langsung ke konfigurasi utama di sidebar secara instan.

4. **Automatic Interpretation (Interpretasi Otomatis)**
   * Menghasilkan draf teks otomatis yang siap digunakan untuk **Bab 3: Metodologi Penelitian (Sub-bab Ukuran Sampel)** pada Skripsi/Tugas Akhir.
   * Menghasilkan draf ringkas yang siap disalin untuk kebutuhan penulisan **Jurnal / Artikel Ilmiah**.

---

## 🛠️ Uji Statistik yang Didukung

Aplikasi ini mendukung analisis kekuatan uji untuk berbagai rumpun uji statistika melalui paket `pwr`:

* **t tests:**
  * *Means: Difference between two independent means* (Uji t Dua Sampel Independen)
  * *Means: Difference between paired means* (Uji t Sampel Berpasangan)
  * *Means: Difference from constant* (Uji t Satu Sampel)
* **Correlation and Regression:**
  * *Correlation: Bivariate normal model* (Analisis Korelasi Bivariat)
* **F tests:**
  * *ANOVA: Fixed effects, omnibus* (Uji ANOVA Satu Arah / One-Way ANOVA)
  * *ANOVA: Repeated measures, within factors* (Uji ANOVA Pengukuran Berulang)

---

## 📦 Prasyarat & Library R

Sebelum menjalankan aplikasi, pastikan Anda telah memasang beberapa paket (*packages*) R berikut:

```R
install.packages(c("shiny", "bslib", "pwr", "ggplot2"))
