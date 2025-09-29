# Eksperimen ResNet-34 vs Plain-34
Mata Kuliah: IF25-40401 - Deep Learning  
Program Studi: Teknik Informatika - ITERA  

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
| Batch Size       | 32                     |
| Epoch            | 20                     |
| Loss Function    | CrossEntropyLoss       |

## Perbandingan Plain-34 vs ResNet-34
### Tabel Metrik (Epoch terakhir)
| Model      | Train Acc | Val Acc | Train Loss | Val Loss |
|------------|-----------|---------|------------|----------|
| Plain-34   | 72.15%    | 40.72%  | 0.89       | 1.95     |
| ResNet-34  | 91.23%    | 58.37%  | 0.29       | 1.35     |

### Grafik Kurva Training
**Loss Curve**  
![Loss Curve](assets/loss_curve.png)  

**Accuracy Curve**  
![Accuracy Curve](assets/acc_curve.png)  

## Analisis Singkat
Residual connection pada ResNet-34 berhasil mengatasi masalah degradasi yang dialami oleh Plain-34.  
- Val Acc meningkat signifikan dari 40.72% → 58.37% (+17.65 pp, ≈+43% relatif).  
- ResNet-34 juga mencapai akurasi validasi lebih cepat (epoch-1 ResNet sudah melampaui performa terbaik Plain-34).  
- Hal ini membuktikan bahwa residual learning membantu optimisasi menjadi lebih stabil serta meningkatkan generalization.  

## Struktur Repositori
```
├── models/
│   ├── plain34.py
│   ├── resnet34.py
│   └── modifications/
├── checkpoints/
│   ├── best_plain34_model.pth
│   ├── best_resnet34_model.pth
├── notebooks/
│   └── ResNet_vs_Plain34_Analysis.ipynb
├── assets/
│   ├── loss_curve.png
│   └── acc_curve.png
├── README.md
└── requirements.txt
```

## Peran dan Kontribusi AI Assistant
Sebagian kode dan dokumentasi dibantu menggunakan ChatGPT/GitHub Copilot, khususnya:
- Template analisis perbandingan Plain-34 vs ResNet-34.
- Pembuatan fungsi plotting kurva loss/accuracy.
- Draft README.md.

Semua hasil dari AI telah diverifikasi, dimodifikasi, dan diuji oleh tim untuk memastikan akurasi dan pemahaman penuh terhadap implementasi.

## Anggota Kelompok
- Nama 1 (NIM)
- Nama 2 (NIM)
- Nama 3 (NIM)

## Catatan Pengumpulan
- Source code lengkap tersedia di repositori ini.
- Laporan PDF dikompilasi dari LaTeX sesuai template IF ITERA.
- Tautan GitHub/Colab disertakan pada laporan akhir.
