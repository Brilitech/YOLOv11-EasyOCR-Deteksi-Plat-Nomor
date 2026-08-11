# 🚗 YOLOv11-EasyOCR-Deteksi-Plat-Nomor
Notebook ini mengimplementasikan sistem ANPR (Automatic Number Plate Recognition) atau deteksi plat nomor dengan menggunakan: - **YOLOv11** (dari Ultralytics) untuk mendeteksi bounding box plat nomor. - **EasyOCR** untuk mengekstrak teks dari area plat.
Sistem ini dirancang untuk bekerja secara real-time pada video (file atau webcam) maupun pada gambar statis, dengan hasil yang cepat dan akurat.

## 📖 Deskripsi Teknologi

*   **YOLOv11 (Ultralytics):** Model deteksi objek mutakhir yang sangat cepat dan akurat. Dalam proyek ini, YOLOv11 bertugas sebagai pendeteksi utama (detector) untuk menemukan lokasi plat nomor kendaraan di dalam frame video atau gambar, kemudian membuat kotak pembatas (*bounding box*) di area tersebut.
*   **EasyOCR:** Library OCR berbasis *deep learning* yang ringan dan mendukung banyak bahasa. Setelah YOLOv11 menemukan dan memotong (*crop*) area plat nomor, EasyOCR bertugas untuk memproses potongan gambar tersebut (dengan mengubahnya ke grayscale) guna membaca dan mengekstrak teks (angka dan huruf) dari plat nomor.

## ✨ Fitur Utama
- **Deteksi Real-time:** Memproses frame video secara berurutan menggunakan OpenCV.
- **Dukungan CPU & GPU:** Otomatis mendeteksi dan menggunakan CUDA (GPU) jika tersedia untuk mempercepat proses inferensi, atau menggunakan CPU sebagai cadangan.
- **Ekstraksi Teks (OCR):** Mengubah hasil tangkapan plat nomor menjadi teks digital.
- **Visualisasi Bounding Box:** Menampilkan kotak pembatas dan teks yang terbaca langsung di atas video/gambar output.

## 🛠️ Persyaratan Sistem (Prerequisites)
Pastikan Anda telah menginstal Python (disarankan versi 3.8 ke atas). Library utama yang dibutuhkan:
- `ultralytics` (untuk YOLOv11)
- `easyocr`
- `opencv-python`
- `numpy`
- `matplotlib`
- `torch` & `torchvision` (disarankan menginstal versi CUDA untuk performa maksimal)

## 💾 Instalasi

1. **Clone repositori ini (jika menggunakan Git) atau unduh file `.ipynb`:**
   ```bash
   git clone https://github.com/Brilitech/YOLOv11-EasyOCR-Deteksi-Plat-Nomor.git
   cd YOLOv11-EasyOCR-Deteksi-Plat-Nomor
   ```

2. **Instal dependensi menggunakan pip:**
   Anda dapat menjalankan perintah instalasi langsung di terminal atau dari dalam Jupyter Notebook:
   ```bash
   pip install ultralytics easyocr opencv-python numpy matplotlib
   ```

## 🚀 Cara Penggunaan

1. **Siapkan Model YOLO:**
   Pastikan Anda memiliki file bobot (weights) model YOLO yang sudah dilatih khusus untuk plat nomor. Letakkan file `anpr_best.pt` di direktori yang sama dengan notebook, atau sesuaikan path pada kode.
   *(Catatan: Anda dapat melatih model sendiri atau merujuk ke referensi video di bawah untuk model pre-trained).*

2. **Siapkan File Video/Gambar:**
   Siapkan file video yang ingin dideteksi (misal: `bmw_60fps.mp4`) atau gunakan opsi webcam dengan parameter `source=0`.

3. **Jalankan Jupyter Notebook:**
   Buka file `.ipynb` dan jalankan *cell* satu per satu. 
   - Sistem akan mengecek ketersediaan GPU.
   - Kelas `ANPR` akan menginisialisasi model YOLO dan EasyOCR.
   - Inferensi akan berjalan, menampilkan jendela video dengan bounding box, dan menyimpan hasilnya ke `anpr_output.mp4`.

## 📁 Struktur Kode

- `detect_plates()`: Memprediksi letak plat nomor menggunakan YOLOv11.
- `extract_text()`: Mengambil hasil *crop* plat nomor, mengubah ke warna abu-abu (grayscale), dan menjalankan EasyOCR.
- `infer_video()`: Membuka stream video (kamera/file), menjalankan deteksi per frame, menampilkan anotasi, dan menyimpan output.

## 🔗 Referensi
- [Ultralytics YOLOv11](https://github.com/ultralytics/ultralytics)
- [EasyOCR by JaidedAI](https://github.com/JaidedAI/EasyOCR)
- Tutorial/Model Source: [YouTube Reference](https://www.youtube.com/watch?v=Fym4hoaoreE&t=42s)
