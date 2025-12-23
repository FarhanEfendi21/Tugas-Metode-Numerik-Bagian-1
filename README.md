# Implementasi Algoritma Finite Difference (Selisih Hingga) 📐

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![NumPy](https://img.shields.io/badge/Library-NumPy-013243)
![Matplotlib](https://img.shields.io/badge/Library-Matplotlib-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

> **Tugas Mata Kuliah Metode Numerik**
> Topik: Penerapan Turunan Numerik untuk Estimasi Kecepatan dan Percepatan Objek dari Data Posisi Diskrit.

---

## 👨‍💻 Identitas Penulis

| Atribut | Detail |
| :--- | :--- |
| **Nama** | **Muhammad Farhan Efendi** |
| **NIM** | 21120123140181 |
| **Departemen** | Teknik Komputer |
| **Fakultas** | Fakultas Teknik |
| **Universitas** | Universitas Diponegoro |

---

## 📝 Deskripsi Proyek

Proyek ini bertujuan untuk menyelesaikan permasalahan pada sistem pemantauan (seperti kendaraan otonom) di mana sensor sering kali hanya memberikan **data posisi ($x$)** terhadap waktu ($t$) secara diskrit, tanpa diketahui fungsi analitiknya.

Untuk keperluan kontrol dan navigasi yang membutuhkan data kecepatan ($v$) dan percepatan ($a$), proyek ini menerapkan **Metode Numerik Selisih Hingga (*Finite Difference*)**. Algoritma ini mengestimasi nilai turunan pertama dan kedua dari data posisi tersebut.

Tujuan akhirnya adalah membandingkan hasil komputasi numerik dengan solusi eksak (teoritis) untuk memvalidasi akurasi algoritma.

---

## ⚙️ Metode yang Digunakan

Studi kasus ini menerapkan tiga skema pendekatan Turunan Numerik berdasarkan Deret Taylor:

1.  **Selisih Maju (*Forward Difference*)**
    * Digunakan khusus pada **Batas Awal** data ($i=0$).
    * Rumus: $f'(x_i) \approx \frac{f(x_{i+1}) - f(x_i)}{h}$
    * Error: $O(h)$

2.  **Selisih Mundur (*Backward Difference*)**
    * Digunakan khusus pada **Batas Akhir** data ($i=n$).
    * Rumus: $f'(x_i) \approx \frac{f(x_{i}) - f(x_{i-1})}{h}$
    * Error: $O(h)$

3.  **Selisih Pusat (*Central Difference*)**
    * Digunakan pada seluruh **Titik Interior** (tengah).
    * Metode ini dipilih sebagai prioritas karena memiliki akurasi lebih tinggi ($O(h^2)$) dibandingkan dua metode di atas.
    * Rumus: $f'(x_i) \approx \frac{f(x_{i+1}) - f(x_{i-1})}{2h}$

---

## 🚀 Implementasi Kode

Program ditulis menggunakan **Python** dengan memanfaatkan teknik **Vectorization** (*Slicing Array*) dari pustaka NumPy. Teknik ini membuat komputasi jauh lebih efisien dibandingkan *looping* konvensional.

### Prasyarat (Requirements)
Pastikan Anda telah menginstal pustaka berikut:
```bash
pip install numpy matplotlib
