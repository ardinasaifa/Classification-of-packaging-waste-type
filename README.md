**Klasifikasi Jenis Sampah Kemasan Menggunakan Machine Learning dan Deep Learning**

Proyek ini bertujuan untuk mengklasifikasikan lima jenis sampah kemasan (botol plastik, botol kaca, kaleng, kardus, dan plastik snack) berdasarkan citra gambar menggunakan metode Machine Learning (SVM dan Random Forest) serta Deep Learning (CNN). 

**Dataset** <br>
Sumber: Pengambilan gambar mandiri dan kaggle <br>
Total: 500 gambar (100 gambar per jenis sampah) <br>
Format gambar: berwarna, dengan variasi resolusi <br>

**Preprocessing dan Ekstraksi Fitur** <br>
Untuk model machine learning, dilakukan ekstraksi fitur dari citra gambar: <br>
Color Histogram: 12 fitur <br>
Hu Moments: 7 fitur <br>
Haralick Texture (GLCM): 13 fitur <br>
Uniform Local Binary Pattern (LBP): 60 fitur <br>
Total fitur: 92 fitur <br>

Untuk model deep learning (CNN), preprocessing dilakukan dengan: <br>
1. Resize gambar ke ukuran 224x224 piksel <br>
2. Rescaling nilai piksel ke rentang [-1, 1] <br>
3. Selain itu, fitur juga diekstraksi menggunakan model pretrained InceptionV3 yang menghasilkan 2048 fitur. <br>

**Model yang Digunakan** <br>
- Support Vector Machine (SVM) <br>
- Random Forest <br>
- Convolutional Neural Network (CNN) <br>
Evaluasi dilakukan pada data training dan testing dengan pembagian 80:20 untuk model machine learning, serta 60:20:20 untuk CNN (training, validation, testing). Masing-masing model diuji dengan dan tanpa hyperparameter tuning. <br>

**Hasil Eksperimen**
1. Machine Learning (split data 80:20) 
   - Algoritma Random Forest mencapai akurasi 82%
   - Algoritma Support Vector Machine mencapai akurasi 72%
2. Deep Learning (split data 60:20:20)
   - Algoritma CNN mencapai akurasi pada data test 93% dengan hyperparameter tuning, maks epoch 9/15 <br>
