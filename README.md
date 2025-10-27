# SegmentasiCitraLanjut

Ini adalah repositori untuk pembelajaran **Segmentasi Citra Lanjut (Edge-Based dan Region-Based)** berdasarkan materi **Pekan 7 – Pengolahan Citra Digital**.

Deskripsi:
Segmentasi citra adalah proses pemisahan objek dari latar belakang agar dapat dianalisis lebih lanjut.  
Pada proyek ini diterapkan empat metode segmentasi buatan sendiri menggunakan bahasa **Python** tanpa menyalin dari modul praktikum.

Metode yang diimplementasikan meliputi:
1. **Sobel Edge Detection (Manual)**
2. **Canny Sederhana**
3. **Region Growing**
4. **Watershed Sederhana**

---

## Notebook atau File Program
File utama: `segmentasi_lanjut_manual.py`  
Melakukan langkah-langkah berikut:

1. Membaca gambar uji dalam format grayscale.  
2. Melakukan **Edge Detection** menggunakan operator Sobel (manual konvolusi kernel).  
3. Mengimplementasikan **Canny sederhana** tanpa fungsi `cv2.Canny`, dengan tahapan:
   - Gaussian Blur manual  
   - Perhitungan gradien dengan Sobel  
   - Double threshold dan hysteresis sederhana  
4. Menerapkan **Region Growing** berbasis satu titik seed dan perbedaan intensitas.  
5. Melakukan **Watershed sederhana** berbasis distance transform dan connected components.  
6. Menampilkan hasil ke dalam jendela **Matplotlib** untuk perbandingan hasil segmentasi.  

---

## Penjelasan Setiap Metode

### 1. Sobel Edge Detection
- Mendeteksi tepi objek berdasarkan perubahan intensitas antar piksel.  
- Menggunakan kernel konvolusi horizontal dan vertikal secara manual.  
- Menghasilkan peta tepi (edge map) dari magnitudo gradien.

### 2. Canny Sederhana
- Implementasi manual tanpa fungsi OpenCV bawaan.  
- Proses terdiri dari Gaussian blur → deteksi gradien → threshold ganda → hysteresis.  
- Hasilnya berupa deteksi tepi halus dengan reduksi noise.

### 3. Region Growing
- Algoritma berbasis area homogen.  
- Dimulai dari **seed point** kemudian menumbuhkan region dengan membandingkan nilai intensitas.  
- Menghasilkan mask biner untuk area homogen dalam citra.

### 4. Watershed
- Menganggap citra sebagai topografi (puncak dan lembah).  
- Menggunakan distance transform dan connected components untuk menentukan batas antar wilayah.  
- Menghasilkan batas segmentasi berwarna merah yang memisahkan objek.

---

## Visualisasi Hasil
Program menampilkan 5 subplot hasil segmentasi:
1. Citra Asli  
2. Sobel Manual  
3. Canny Sederhana  
4. Region Growing  
5. Watershed Sederhana  

Setiap metode divisualisasikan menggunakan **Matplotlib** agar dapat dibandingkan secara visual.

---

## Persyaratan
- **Python 3.x**  
- **OpenCV** (`opencv-python`)  
- **NumPy**  
- **Matplotlib**  

---

## Instalasi
Jalankan perintah berikut di terminal:
```bash
pip install opencv-python numpy matplotlib
