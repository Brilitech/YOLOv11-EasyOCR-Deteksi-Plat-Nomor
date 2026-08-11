# YOLOv11-EasyOCR-Deteksi-Plat-Nomor
Notebook ini mengimplementasikan sistem ANPR (Automatic Number Plate Recognition) atau deteksi plat nomor dengan menggunakan: - **YOLOv11** (dari Ultralytics) untuk mendeteksi bounding box plat nomor. - **EasyOCR** untuk mengekstrak teks dari area plat.
Sistem ini dirancang untuk bekerja secara real-time pada video (file atau webcam) maupun pada gambar statis, dengan hasil yang cepat dan akurat.

✨ Fitur Utama
- Deteksi bounding box plat nomor menggunakan YOLOv11.
- OCR (Optical Character Recognition) menggunakan EasyOCR untuk membaca teks plat.
- Mendukung inferensi pada:
- Video (file .mp4, .avi, dll.)
- Kamera langsung (webcam)
- Gambar statis (.jpg, .png, dll.)
- Visualisasi hasil dengan bounding box dan teks yang terbaca.
- Output video hasil deteksi dapat disimpan.
