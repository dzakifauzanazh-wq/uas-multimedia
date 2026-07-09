# uas-multimedia

# Proyek Deteksi Buah Menggunakan YOLOv8

## Latar Belakang

Perkembangan teknologi kecerdasan buatan (Artificial Intelligence) khususnya pada bidang Computer Vision memungkinkan komputer untuk mengenali dan mendeteksi objek secara otomatis dari citra digital. Salah satu penerapan Computer Vision yang banyak digunakan adalah Object Detection, yaitu teknik untuk mengidentifikasi dan menentukan lokasi suatu objek dalam gambar.

Pada proyek ini, dilakukan pembangunan sistem deteksi buah menggunakan algoritma YOLOv8 (You Only Look Once Version 8). Sistem ini dirancang untuk mengenali beberapa jenis buah, yaitu apel (apple), pisang (banana), dan jeruk (orange) berdasarkan dataset gambar yang telah diberi anotasi.

## Tujuan Proyek

Tujuan dari proyek ini adalah:

1. Membangun model Object Detection menggunakan YOLOv8.
2. Melatih model agar mampu mengenali dan membedakan objek buah.
3. Mengevaluasi performa model berdasarkan hasil training dan validasi.
4. Menghasilkan sistem deteksi yang dapat digunakan untuk mengidentifikasi buah secara otomatis pada gambar.

## Dataset

Dataset yang digunakan terdiri dari gambar buah beserta file anotasi dalam format Pascal VOC (.xml). Setiap file XML berisi informasi posisi objek berupa bounding box dan label kelas objek yang terdapat pada gambar.

Dataset dibagi menjadi dua bagian, yaitu:

* Data Training: digunakan untuk melatih model.
* Data Testing/Validation: digunakan untuk menguji kemampuan model setelah proses pelatihan.

Sebelum digunakan pada YOLOv8, file anotasi XML dikonversi terlebih dahulu ke format YOLO (.txt). Pada proses konversi, setiap objek diberi label numerik sebagai berikut:

* 0 = Apple
* 1 = Banana
* 2 = Orange

Format anotasi YOLO terdiri dari:

class_id x_center y_center width height

dengan seluruh koordinat dinormalisasi ke rentang 0–1.

## Metode yang Digunakan

Model yang digunakan pada proyek ini adalah YOLOv8. YOLO merupakan salah satu algoritma Object Detection yang terkenal karena memiliki kecepatan dan akurasi yang tinggi. Berbeda dengan metode deteksi tradisional yang memproses objek dalam beberapa tahap, YOLO melakukan deteksi dalam satu kali proses sehingga lebih efisien.

Tahapan yang dilakukan dalam proyek ini meliputi:

1. Persiapan Dataset

   * Mengumpulkan gambar dan anotasi.
   * Mengecek struktur dataset.
   * Mengonversi anotasi XML ke format YOLO.

2. Pembuatan Struktur Dataset YOLO

   * Menyusun folder images/train.
   * Menyusun folder images/val.
   * Menyusun folder labels/train.
   * Menyusun folder labels/val.

3. Konfigurasi Dataset

   * Membuat file data.yaml yang berisi lokasi dataset dan daftar kelas objek.

4. Training Model

   * Menggunakan model YOLOv8 sebagai model dasar.
   * Melatih model menggunakan dataset yang telah dipersiapkan.
   * Menentukan jumlah epoch, ukuran gambar, dan parameter pelatihan lainnya.

5. Evaluasi Model

   * Mengukur performa model menggunakan data validasi.
   * Menganalisis nilai precision, recall, dan mAP.

6. Pengujian Model

   * Menggunakan model hasil training untuk mendeteksi objek pada gambar baru.
   * Menampilkan hasil prediksi berupa bounding box dan label kelas.

## Implementasi Menggunakan Google Colab

Seluruh proses pengembangan dilakukan menggunakan Google Colab karena menyediakan lingkungan Python yang mudah digunakan dan mendukung pemanfaatan GPU untuk mempercepat proses training.

Library utama yang digunakan meliputi:

* Python
* Ultralytics YOLOv8
* OpenCV
* NumPy
* XML ElementTree
* Matplotlib

Google Colab digunakan untuk:

* Mengolah dataset.
* Mengonversi anotasi.
* Melatih model YOLOv8.
* Melakukan evaluasi model.
* Menampilkan hasil deteksi objek.

## Hasil dan Pembahasan

Setelah proses training selesai, model berhasil mempelajari karakteristik masing-masing buah berdasarkan dataset yang diberikan. Model mampu mendeteksi lokasi objek pada gambar serta mengklasifikasikan jenis buah sesuai kelas yang telah ditentukan.

Hasil deteksi ditampilkan dalam bentuk bounding box yang mengelilingi objek serta label kelas dan nilai confidence score. Semakin tinggi confidence score yang dihasilkan, semakin yakin model terhadap hasil prediksi yang diberikan.

Performa model dievaluasi menggunakan metrik Object Detection seperti Precision, Recall, dan Mean Average Precision (mAP). Nilai-nilai tersebut digunakan untuk mengetahui tingkat akurasi model dalam mendeteksi objek pada data yang belum pernah dilihat sebelumnya.

## Kesimpulan

Berdasarkan proyek yang telah dilakukan, dapat disimpulkan bahwa algoritma YOLOv8 mampu digunakan untuk membangun sistem deteksi buah secara otomatis dengan hasil yang cukup baik. Melalui proses pelatihan menggunakan dataset yang telah dianotasi, model dapat mengenali objek apel, pisang, dan jeruk pada gambar dengan cepat dan akurat.

Proyek ini menunjukkan bahwa teknologi Computer Vision dapat diterapkan untuk berbagai kebutuhan identifikasi objek secara otomatis, serta dapat dikembangkan lebih lanjut dengan menambahkan jumlah data, variasi objek, maupun optimasi parameter model guna meningkatkan performa deteksi.
