# Analisis Rangkaian Listrik Menggunakan Metode Gauss-Seidel

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![NumPy](https://img.shields.io/badge/Library-NumPy-orange)
![Matplotlib](https://img.shields.io/badge/Visualization-Matplotlib-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

Repositori ini berisi implementasi **Metode Numerik Gauss-Seidel** menggunakan Python untuk menyelesaikan Sistem Persamaan Linear (SPL) pada kasus **Rangkaian Listrik Majemuk 3-Loop**. Proyek ini dibuat untuk memenuhi Tugas Mata Kuliah Metode Numerik.

## 📌 Deskripsi Masalah

Masalah yang diselesaikan adalah mencari nilai arus ($I_1, I_2, I_3$) pada rangkaian resistif yang memiliki resistor bersama (*shared resistors*). Berdasarkan **Hukum Tegangan Kirchhoff (KVL)**, rangkaian tersebut dimodelkan menjadi sistem persamaan linear.

**Topologi Rangkaian:**
![Skema Rangkaian](assets/image_132d82.png)
*(Pastikan kamu mengupload gambar rangkaian ke folder 'assets' atau root folder)*

## 📐 Model Matematika

Sistem persamaan linear direpresentasikan dalam bentuk matriks $Ax = B$:

$$
\begin{bmatrix}
20 & -5 & 0 \\
-5 & 15 & -5 \\
0 & -5 & 20
\end{bmatrix}
\begin{bmatrix}
I_1 \\
I_2 \\
I_3
\end{bmatrix}
=
\begin{bmatrix}
100 \\
0 \\
10
\end{bmatrix}
$$

Di mana:
* **Matriks A**: Representasi Resistansi ($R$) dalam Ohm.
* **Vektor x**: Variabel Arus ($I$) dalam Ampere yang dicari.
* **Vektor B**: Sumber Tegangan ($V$) dalam Volt.

## ✨ Fitur Program

Program ini memiliki beberapa fitur unggulan:
1.  **Validasi Matriks (Diagonal Dominant):** Mengecek secara otomatis apakah matriks memenuhi syarat konvergensi ($|a_{ii}| > \sum |a_{ij}|$) sebelum iterasi dimulai.
2.  **Algoritma Gauss-Seidel:** Mengimplementasikan metode iteratif dengan pembaruan nilai langsung (*immediate update*) untuk konvergensi yang lebih cepat.
3.  **Visualisasi Data:** Menampilkan grafik konvergensi error menggunakan skala logaritmik (*Log-Scale*) dengan `matplotlib`.
4.  **Validasi Akurasi:** Membandingkan hasil numerik dengan solusi eksak dari `numpy.linalg.solve`.

## 🚀 Cara Menjalankan

### Prasyarat
Pastikan Python 3.x sudah terinstall di komputer Anda. Install pustaka yang dibutuhkan:

```bash
pip install numpy matplotlib
