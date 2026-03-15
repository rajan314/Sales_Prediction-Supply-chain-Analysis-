# 📈 Sales Prediction & Supply Chain Analysis

A deep learning project that uses an **LSTM (Long Short-Term Memory)** neural network to forecast monthly sales demand, supporting smarter supply chain decisions.

---

## 🧠 Overview

This project demonstrates how to build a time series forecasting model using LSTM to predict future sales from historical data. The model is trained on synthetic monthly sales data and can be adapted for real-world supply chain and demand forecasting scenarios.

---

## 🗂️ Project Structure

```
Sales_Prediction-Supply-chain-Analysis/
└── project43.ipynb     # Main Jupyter/Colab notebook
```

---

## ⚙️ Tech Stack

| Category        | Tools / Libraries                          |
|-----------------|--------------------------------------------|
| Language        | Python 3                                   |
| Deep Learning   | TensorFlow / Keras (LSTM, Dense layers)    |
| Data Processing | NumPy, Pandas, Scikit-learn (MinMaxScaler) |
| Visualization   | Matplotlib                                 |
| Platform        | Google Colab                               |

---

## 📊 Dataset

- **Type:** Synthetic monthly sales data
- **Period:** January 2021 – December 2021 (12 months)
- **Values:** `[200, 220, 250, 240, 280, 300, 350, 370, 400, 420, 450, 480]`
- **Pattern:** Upward trend simulating real-world demand growth

---

## 🔄 Workflow

### Step 1 — Data Generation
Generate synthetic monthly sales data and visualize the trend.

### Step 2 — Preprocessing
- Normalize data using `MinMaxScaler` (range: 0 to 1)
- Create time-windowed sequences with `time_step = 3` (use 3 prior months to predict the next)
- Reshape input for LSTM format: `(samples, time_steps, features)`

### Step 3 — Train/Test Split
- 80% training data, 20% test data

### Step 4 — Model Architecture
```
LSTM(units=50) → Dense(units=1)
```
- Optimizer: Adam (lr = 0.001)
- Loss: Mean Squared Error (MSE)
- Epochs: 100, Batch size: 1

### Step 5 — Evaluation
- Inverse-transform predictions back to original scale
- Evaluate using **Mean Squared Error (MSE)**

### Step 6 — Visualization
Plot actual vs. predicted sales on the test set.

### Step 7 — Future Prediction
Predict the next month's sales using the last 3 data points.

---

## 📉 Results

| Metric | Value |
|--------|-------|
| Mean Squared Error (MSE) | ~215.67 |
| Predicted Next Month Sales | ~524.54 |

---

## 🚀 Getting Started

### Run on Google Colab
Click the badge at the top of `project43.ipynb` to open directly in Colab — no setup required.

### Run Locally

**1. Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/Sales_Prediction-Supply-chain-Analysis-.git
cd Sales_Prediction-Supply-chain-Analysis-
```

**2. Install dependencies**
```bash
pip install numpy pandas matplotlib scikit-learn tensorflow
```

**3. Launch the notebook**
```bash
jupyter notebook project43.ipynb
```

---

## 📌 Key Concepts

- **LSTM** — A type of recurrent neural network designed to learn long-term dependencies in sequential data
- **Time Step** — Number of past observations used to predict the next value
- **MinMaxScaler** — Normalizes data to a fixed range, improving model convergence
- **MSE** — Measures average squared difference between predicted and actual values

---

## 🔮 Future Improvements

- Use real-world supply chain / retail datasets
- Add multiple features (e.g., promotions, seasonality, holidays)
- Experiment with stacked LSTM layers or GRU
- Implement early stopping and dropout for regularization
- Build an interactive dashboard for forecasting visualization

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 🙋‍♂️ Author

Built with ❤️ —Rajan Singh
