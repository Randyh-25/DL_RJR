# Eksperimen ResNet-34 vs Plain-34
Mata Kuliah: IF25-40401 - Deep Learning  
Program Studi: Teknik Informatika - ITERA  

## Anggota Kelompok
- Muhammad Riveldo Hermawan Putra - 122140037
- Joshia Fernandes Sectio Purba - 122140170
- Randy Hendriyawan - 122140171

## Deskripsi Proyek
Proyek ini mengeksplorasi perbedaan performa antara Plain-34 (ResNet tanpa residual connection) dan ResNet-34 (dengan residual connection). Selain itu dilakukan juga eksperimen modifikasi lanjutan untuk meningkatkan performa model. Dataset yang digunakan adalah 5 Makanan Indonesia.

Tujuan utama:
- Mengamati masalah degradasi pada Plain-34.
- Membuktikan efektivitas residual connection pada ResNet-34.
- Mengeksplorasi minimal dua modifikasi lanjutan (opsional).

## Konfigurasi Hyperparameter
| Parameter        | Nilai                  |
|------------------|------------------------|
| Optimizer        | Adam (default)         |
| Learning Rate    | 0.001                  |
| Batch Size       | 16                     |
| Epoch            | 10                     |
| Loss Function    | CrossEntropyLoss       |

## Perbandingan Plain-34 vs ResNet-34
### Tabel Metrik (Epoch terakhir)
| Model      | Train Acc | Val Acc | Train Loss | Val Loss |
|------------|-----------|---------|------------|----------|
| Plain-34   | 72.15%    | 40.72%  | 0.89       | 1.95     |
| ResNet-34  | 91.23%    | 58.37%  | 0.29       | 1.35     |

### Grafik Kurva Training
![Curve](https://raw.githubusercontent.com/Randyh-25/DL_RJR/refs/heads/main/Accuracy.png)  

## Analisis Singkat
Residual connection pada ResNet-34 berhasil mengatasi masalah degradasi yang dialami oleh Plain-34.  
- Val Acc meningkat signifikan dari 40.72% → 58.37% (+17.65 pp, ≈+43% relatif).  
- ResNet-34 juga mencapai akurasi validasi lebih cepat (epoch-1 ResNet sudah melampaui performa terbaik Plain-34).  
- Hal ini membuktikan bahwa residual learning membantu optimisasi menjadi lebih stabil serta meningkatkan generalization.  

