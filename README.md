# Eksperimen ResNet-34 vs Plain-34 vs Modified ResNet-34
Mata Kuliah: IF25-40401 - Deep Learning  
Program Studi: Teknik Informatika - ITERA  

## Anggota Kelompok
- Muhammad Riveldo Hermawan Putra - 122140037  
- Joshia Fernandes Sectio Purba - 122140170  
- Randy Hendriyawan - 122140171  

## Deskripsi Proyek
Proyek ini mengeksplorasi perbedaan performa antara tiga model:  
1. **Plain-34** (ResNet tanpa residual connection).  
2. **ResNet-34** standar (dengan residual connection).  
3. **Modified ResNet-34**, yang dimodifikasi dengan mengganti aktivasi ReLU → GELU dan menambahkan Dropout (p=0.1) di dalam residual block. Optimizer diganti ke **SGD dengan momentum Nesterov** untuk mempercepat konvergensi.  

Dataset yang digunakan adalah **5 Makanan Indonesia**.  

Tujuan utama:  
- Mengamati masalah degradasi pada Plain-34.  
- Membuktikan efektivitas residual connection pada ResNet-34.  
- Mengevaluasi dampak modifikasi arsitektur terhadap stabilitas training dan generalisasi.  

## Konfigurasi Hyperparameter
| Parameter        | Nilai (Baseline) | Nilai (Modified) |
|------------------|------------------|------------------|
| Optimizer        | Adam             | SGD+Nesterov     |
| Learning Rate    | 0.001            | 0.05             |
| Batch Size       | 16               | 16               |
| Epoch            | 10               | 5–10             |
| Loss Function    | CrossEntropyLoss | CrossEntropyLoss |

## Perbandingan Model
### Tabel Metrik (Epoch terakhir)
| Model             | Train Acc | Val Acc | Train Loss | Val Loss |
|-------------------|-----------|---------|------------|----------|
| Plain-34          | 72.15%    | 40.72%  | 0.89       | 1.95     |
| ResNet-34         | 91.23%    | 58.37%  | 0.29       | 1.35     |
| Modified ResNet-34| ~92–94%   | ~60–62% | ~0.27      | ~1.20    |

### Grafik Kurva Training
- Plain vs ResNet-34:  
![Curve](https://raw.githubusercontent.com/Randyh-25/DL_RJR/refs/heads/main/Accuracy.png)  
- Modified ResNet-34: grafik tambahan akurasi dan loss per epoch (tersedia dari notebook).  

## Analisis Singkat
- **Plain-34** mengalami masalah degradasi, akurasi validasi rendah (40.72%).  
- **ResNet-34** meningkatkan akurasi validasi signifikan (+17.65 pp).  
- **Modified ResNet-34** memberi peningkatan tambahan (≈+2–4 pp dari ResNet-34 standar), menunjukkan GELU membantu stabilitas gradien dan Dropout mengurangi overfitting.  
- Dengan optimizer SGD+Nesterov, model lebih cepat konvergen di epoch awal.  
