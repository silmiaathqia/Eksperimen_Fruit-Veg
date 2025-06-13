# 🍎🥕 Eksperimen Fruit & Vegetable Dataset

Repositori otomatisasi preprocessing dataset buah dan sayuran menggunakan GitHub Actions.

## 📁 Struktur Repository

```
Eksperimen_Fruit&Veg/
├── .github/workflows/
│   └── preprocessing.yml          # ← This workflow file
├── preprocessing/
│   ├── automate_preprocessing.py  # ← Your preprocessing script
│   └── namadataset_preprocessing/ # ← Output directory
├── requirements.txt               # ← Python dependencies
└── README.md
```

## 🚀 Cara Penggunaan

### Setup Awal

1. **Clone repository:**
   ```bash
   git clone https://github.com/username/Eksperimen_Fruit-Veg.git
   cd Eksperimen_Fruit-Veg
   ```

2. **Setup Kaggle Credentials:**
   - Buka repository **Settings** → **Secrets and variables** → **Actions**
   - Tambahkan secrets berikut:
     - `KAGGLE_USERNAME`: Username Kaggle Anda
     - `KAGGLE_KEY`: API key dari file kaggle.json

3. **Upload file Anda:**
   - `automate_preprocessing.py` → `preprocessing/`
   - `Eksperimen_Fruit&Veg.ipynb` → `preprocessing/`

### Menjalankan Preprocessing

#### 🔄 Otomatis (Trigger saat Push)
```bash
git add preprocessing/
git commit -m "Update preprocessing code"
git push origin main
```

#### ⚡ Manual (GitHub Actions Interface)
1. Buka tab **"Actions"** di GitHub
2. Pilih **"Fruit & Vegetable Dataset Preprocessing"**
3. Klik **"Run workflow"**
4. Atur parameter:
   - **Target Size**: 224,224 (default)
   - **Apply Augmentation**: true/false
   - **Upload to Drive**: true/false (opsional)

## 📥 Mengunduh Hasil

Setelah workflow selesai:

### Via Artifacts:
1. Buka workflow run yang selesai
2. Download **"fruit-veg-preprocessed-dataset-XXXX"**
3. Extract ke folder `preprocessing/namadataset_preprocessing/`

### Via Releases (untuk push ke main):
1. Buka tab **"Releases"**
2. Download dataset dari release terbaru

## 📊 Output yang Dihasilkan

### Dataset Files
- `train/images.npy` & `train/labels.npy` - Data training
- `test/images.npy` & `test/labels.npy` - Data testing
- `validation/images.npy` & `validation/labels.npy` - Data validasi
- `metadata.json` - Informasi dataset lengkap
- `label_encoder.pkl` - Encoder untuk label mapping

### Reports
- `PREPROCESSING_SUMMARY.md` - Laporan hasil preprocessing
- `run_info.json` - Detail eksekusi workflow

## 🔧 Konfigurasi

### Workflow Parameters
- **Target Size**: Ukuran resize gambar (default: 224x224)
- **Apply Augmentation**: Aktifkan augmentasi untuk training data
- **Upload to Drive**: Upload hasil ke Google Drive (perlu setup credentials)

### Dataset Info
- **Total Classes**: 36 kategori (25 sayuran + 11 buah)
- **Image Format**: RGB, normalized [0,1]
- **Augmentation**: Horizontal flip, rotation, brightness adjustment

## 🏷️ Kategori yang Didukung

### 🍎 Buah (11):
Apple, Banana, Grapes, Kiwi, Lemon, Mango, Orange, Pear, Pineapple, Pomegranate, Watermelon

### 🥕 Sayuran (25):
Beetroot, Bell Pepper, Cabbage, Capsicum, Carrot, Cauliflower, Chilli Pepper, Corn, Cucumber, Eggplant, Garlic, Ginger, Jalapeño, Lettuce, Onion, Paprika, Peas, Potato, Radish, Soy Beans, Spinach, Sweetcorn, Sweet Potato, Tomato, Turnip

## 📈 Monitoring & Debugging

### Status Checks
- ✅ Workflow completion status
- 📊 Dataset validation checks
- 📁 File structure verification
- 🔍 Data shape consistency

### Troubleshooting
- Cek log di GitHub Actions untuk error details
- Pastikan Kaggle credentials sudah benar
- Verifikasi struktur folder sesuai ekspektasi

## 🤝 Kontribusi

1. Fork repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open Pull Request

## 📄 License

MIT License - Lihat LICENSE untuk detail lengkap.

---

## 🎯 **Langkah Setup:**

1. **Buat repository** `Eksperimen_Fruit&Veg` di GitHub
2. **Buat struktur folder** sesuai yang diminta
3. **Upload files:**
   - `.workflow/preprocessing.yml` (dari panduan di atas)
   - `preprocessing/automate_preprocessing.py` (file Anda)
   - `preprocessing/Eksperimen_Fruit&Veg.ipynb` (file Anda)
   - `requirements.txt`, `.gitignore`, `README.md`
4. **Setup Kaggle credentials** di GitHub Secrets
5. **Push ke main branch** untuk trigger otomatis

## ✨ **Fitur Workflow:**

- ✅ **Otomatis download** dataset dari Kaggle ke `namadataset_raw/`
- ✅ **Preprocessing lengkap** dengan hasil di `preprocessing/namadataset_preprocessing/`
- ✅ **Multi-trigger**: Push, PR, atau manual dengan parameter
- ✅ **Validation checks** untuk memastikan data integrity
- ✅ **Detailed reporting** dengan summary dan statistik
- ✅ **Artifact upload** untuk download hasil preprocessing
- ✅ **Release creation** otomatis untuk dataset di main branch
- ✅ **Google Drive integration** (opsional)

Workflow ini akan secara otomatis menjalankan preprocessing setiap kali ada perubahan pada folder `preprocessing/` dan menyimpan hasilnya sesuai struktur yang Anda inginkan.

---

*Generated with ❤️ by GitHub Actions*
