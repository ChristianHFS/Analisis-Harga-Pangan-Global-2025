Analisis Harga Pangan Global 2025 🌾📊
Repositori ini berisi proyek akhir (Final Project) untuk program CODA RMT-012. Proyek ini berfokus pada pembangunan sistem End-to-End Data Engineering untuk menganalisis dinamika harga komoditas pangan global pada tahun 2025, mengintegrasikan data ekonomi (GDP), dan menyediakan wawasan berbasis data untuk pengambilan keputusan strategis.

Daftar Isi 🗒️
Project Overview

Latar Belakang Masalah

Arsitektur & Teknologi

Proses ETL

Struktur File

Cara Menggunakan

Dependencies & Libraries

Author

Project Overview 📝
Proyek ini menggunakan dataset dari WFP (World Food Programme) yang bersifat granular. Kami mengintegrasikan data harga pangan dengan indikator ekonomi seperti GDP per kapita untuk memahami hubungan antara daya beli masyarakat dan fluktuasi harga pasar. Data diproses menggunakan arsitektur modern yang mengutamakan skalabilitas dan efisiensi biaya.

Tahapan Utama:

Exploratory Data Analysis (EDA): Pembersihan data dan pemetaan negara menggunakan CountryISO3.

Data Transformation: Pemodelan data menjadi Star Schema untuk kebutuhan Data Warehouse.

Automated Pipeline: Orkestrasi data menggunakan Airflow dan pemrosesan batch dengan PySpark.

Latar Belakang Masalah 🧐
Bagaimana cara memahami dinamika harga komoditas global yang fluktuatif? Masalah utama yang diselesaikan adalah:

Mengidentifikasi tren harga antar wilayah.

Menganalisis ketimpangan harga pangan dibanding kondisi ekonomi (GDP).

Memberikan rekomendasi operasional yang efisien (seperti waktu restok komoditas) berbasis data.

Arsitektur & Teknologi ⚙️
Kami menggunakan Arsitektur Modern Hemat Biaya:

Pemrosesan Data: Apache Spark (PySpark) untuk performa tinggi.

Orkestrasi: Apache Airflow untuk manajemen workflow.

Database: Neon PostgreSQL sebagai Cloud Data Warehouse.

Containerization: Docker untuk konsistensi lingkungan pengembangan.

Proses ETL 🚀
1. Extract
Mengambil data mentah (CSV) secara otomatis dari WFP Humanitarian Data Portal menggunakan protokol HTTP/API.

2. Transform
Cleaning: Menghapus HXL Metadata dan menangani missing values.

Modeling: Memecah data menjadi Fact Table (fact_food_price) dan Dimension Tables (dim_commodity, dim_country, dim_market, dim_date).

Storage: Data disimpan sementara dalam format Parquet untuk efisiensi.

3. Load
Data dimuat ke dalam Neon PostgreSQL menggunakan Spark JDBC, siap untuk dikonsumsi oleh alat visualisasi seperti Tableau atau Power BI.

Struktur File 📂
airflow-with-spark/: Berisi konfigurasi DAGs dan docker-compose untuk pipeline.

Dashboard/: File terkait visualisasi hasil analisis.

EDA/: Notebook analisis awal data harga pangan.

final_project_analysis.ipynb: Analisis utama dan pemodelan data.

final_project.sql: Skema database PostgreSQL (DDL).

datamodelling.png: Diagram skema tabel (Star Schema).

Cara Menggunakan 💻
Persiapan Database: Setup database di Neon PostgreSQL dan masukkan kredensial ke file konfigurasi.

Environment: Pastikan Docker terinstal. Jalankan docker-compose up di folder airflow-with-spark.

Running Pipeline: Aktifkan DAG di dashboard Airflow untuk memulai proses ETL.

Analysis: Buka final_project_analysis.ipynb untuk melihat hasil pengolahan data.

Dependencies & Libraries 📚
Author ✍️
Christian H. F. S.

Proyek ini dibuat sebagai bagian dari pemenuhan syarat kelulusan program CODA RMT-012.
