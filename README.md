# VoltStream-LSTM

**Predict household energy consumption 24 hours in advance using deep learning.**

---

## 📌 About This Project

VoltStream-LSTM is a machine learning project that predicts household electricity consumption 24 hours ahead. It analyzes historical power usage patterns and uses a Stacked LSTM neural network to forecast future energy demand with high accuracy.

### Why This Matters

- ✅ Helps households understand energy consumption trends
- ✅ Enables better energy management and cost reduction  
- ✅ Predicts peak usage hours for load balancing

---

## 🚀 Quick Setup

### Step 1: Clone the Repository

```bash
git clone https://github.com/vikram0678/VoltStream-LSTM.git
cd VoltStream-LSTM
```

### Step 2: Create Virtual Environment

**Windows:**
```Git bash
python -m venv voltstream-venv
source voltstream-venv/Scripts/activate

```

**Mac/Linux:**
```bash
python -m venv voltstream-venv
source voltstream-venv/bin/activate
```

### Step 3: Install Dependencies & Setup Kernel

```bash
pip install -r requirements.txt
pip install ipykernel
python -m ipykernel install --user --name voltstream-venv --display-name "VoltStream-LSTM"
```

### Step 4: Download Dataset

```bash
git lfs pull
```

### Step 5: Run in VS Code

1. Open VS Code
2. Navigate to `notebooks/voltstream-lstm.ipynb`
3. Click **Select Kernel** (top right)
4. Choose **VoltStream-LSTM**
5. Click **Run All**

**Done!** ✅

---

## 📁 Project Structure

```
VoltStream-LSTM/
├── data/
│   └── household_power_consumption.txt    # Dataset (Git LFS)
├── models/
│   └── trained_model.keras                # Saved LSTM model
├── notebooks/
│   └── voltstream-lstm.ipynb              # Training notebook
├── requirements.txt                       # Dependencies
├── .gitattributes                         # Git LFS config
└── README.md                              # This file
```

---

## 🧠 Model Details

### Architecture

| Component | Details |
|-----------|---------|
| **Type** | Stacked LSTM |
| **Units** | 50 → 30 |
| **Input** | 72 hours of historical data |
| **Output** | 24-hour forecast |
| **Optimizer** | Adam (lr: 0.0005) |
| **Dropout** | 0.3 (regularization) |

### Dataset

| Property | Value |
|----------|-------|
| **Source** | Individual Household Electric Power Consumption |
| **Records** | 2,075,259 (4 years) |
| **Frequency** | Hourly intervals |
| **File Size** | 124 MB (Git LFS) |

### Performance Metrics

| Metric | Value |
|--------|-------|
| **MAE** | 0.08 kW |
| **RMSE** | 0.12 kW |
| **Accuracy** | ~92% |
| **Train/Val/Test** | 70% / 15% / 15% |

----

## 🔧 Technical Features

**Temporal Engineering:**
- Hour of day (0-23)
- Day of week (0-6)
- Month of year (1-12)

**Lag Features:**
- 1-hour lag (immediate past)
- 24-hour lag (daily pattern)

**Data Processing:**
- Resampled from minute-level to hourly
- Standardized using MinMaxScaler
- Chronological split (no data leakage)
- 6-hour moving average for smoothing

<!-- --- -->

<!-- ## 📋 Requirements

```
Python 3.8+
TensorFlow 2.x
Keras
Pandas
NumPy
Scikit-learn
ipykernel
Git LFS
``` -->

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| **Kernel not showing** | Restart VS Code after kernel installation |
| **Git LFS not working** | Install from https://git-lfs.github.com and run `git lfs pull` |
| **Module error** | Ensure correct kernel is selected and venv is activated |
| **Dataset missing** | Run `git lfs pull` to download the 124 MB file |

---

##  How to Use

1. **Setup** → Follow Quick Setup above
2. **Run** → Open notebook and click "Run All"
3. **Train** → Model trains automatically with all cells
4. **Evaluate** → View MAE, RMSE, and accuracy metrics
5. **Predict** → Use trained model for new predictions

---

<!-- ## 📝 License

MIT License - Free to use, modify, and distribute

---

## 👤 Author

Created as a deep learning portfolio project

--- -->

**⚠️ Important:** Always activate the virtual environment and select the correct kernel before running!

<!-- **Last Updated:** February 2026 -->