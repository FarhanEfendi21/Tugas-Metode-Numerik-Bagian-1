# Implementasi Metode Gauss-Seidel (Sistem Persamaan Linear) ⚡

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![NumPy](https://img.shields.io/badge/Library-NumPy-013243)
![Matplotlib](https://img.shields.io/badge/Library-Matplotlib-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

> **Tugas Mata Kuliah Metode Numerik**
> Topik: Penerapan Metode Iterasi untuk Penyelesaian Analisis Arus pada Rangkaian Listrik Majemuk.

---

## 👨‍💻 Identitas Penulis

| Atribut | Detail |
| :--- | :--- |
| **Nama** | Muhammad Farhan Efendi|
| **NIM** | 21120123140181 |
| **Departemen** | Teknik Komputer |
| **Fakultas** | Teknik |
| **Universitas** | Universitas Diponegoro |

---

## 📝 Deskripsi Proyek

Proyek ini bertujuan untuk menyelesaikan permasalahan pada **analisis rangkaian listrik majemuk (3-Loop)** di mana perhitungan arus sering kali menghasilkan Sistem Persamaan Linear (SPL) yang kompleks dan saling terikat (*coupled*).

Untuk menghindari kerumitan metode eliminasi manual, proyek ini menerapkan **Metode Numerik Gauss-Seidel**. Algoritma ini menyelesaikan persamaan matriks berbentuk $Ax = B$ yang didapatkan dari Hukum Tegangan Kirchhoff (KVL) secara iteratif.

Tujuan akhirnya adalah mendapatkan nilai arus ($I_1, I_2, I_3$) dengan presisi tinggi dan membandingkan hasil komputasi numerik dengan solusi eksak dari pustaka NumPy untuk memvalidasi akurasi algoritma.

---

## ⚙️ Metode yang Digunakan

Studi kasus ini menerapkan algoritma penyelesaian SPL Iteratif dengan karakteristik sebagai berikut:

1.  **Syarat Konvergensi (Strictly Diagonally Dominant)**
    * Algoritma hanya akan dijalankan jika matriks memenuhi syarat: $|a_{ii}| > \sum |a_{ij}|$ (untuk $j \neq i$).
    * Hal ini menjamin bahwa iterasi pasti akan menemukan solusi (konvergen) dan tidak divergen.

2.  **Pembaruan Langsung (*Immediate Update*)**
    * Berbeda dengan metode Jacobi, metode Gauss-Seidel langsung menggunakan nilai terbaru yang baru saja dihitung pada iterasi yang sama.
    * Rumus Iterasi: $x_i^{(k+1)} = \frac{1}{a_{ii}} \left( b_i - \sum_{j=1}^{i-1} a_{ij}x_j^{(k+1)} - \sum_{j=i+1}^{n} a_{ij}x_j^{(k)} \right)$

3.  **Kriteria Berhenti (*Stopping Criteria*)**
    * Iterasi dihentikan ketika **Error Relatif** antar iterasi lebih kecil dari toleransi yang ditetapkan ($\epsilon = 10^{-7}$).
    * Perhitungan error menggunakan Norma Tak-Hingga (*Infinity Norm*).

---

## 🚀 Implementasi Kode

Program ditulis menggunakan **Python** dengan memanfaatkan pustaka NumPy untuk operasi matriks dan Matplotlib untuk visualisasi grafik konvergensi (skala logaritmik).

### Prasyarat (Requirements)
Pastikan Anda telah menginstal pustaka berikut:
```bash
pip install numpy matplotlib
