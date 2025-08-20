# Fraud Wallet Forecasting

This project explores **fraudulent wallet detection and forecasting** using Ethereum transaction data.  
The dataset structure is based on the [Real-CATS Kaggle dataset](https://www.kaggle.com/datasets/lvd312393/real-cats),  
but we experimented with a **subset of 250 wallets** for development and prototyping.

## 🚀 Workflow

### 1. Data Preparation
- Extract wallet-level transactions from JSONs (`normal_transactions.json`, `ERC_20_transactions.json`).
- Merge into a unified transaction dataset with labels (`fraud = 1`, `normal = 0`).
- For prototyping, we selected **250 wallets** (125 fraud, 125 normal).

### 2. Feature Engineering
- Convert transaction fields into numeric features (e.g., `value`, `gas`, `gasPrice`).
- Drop unused columns (e.g., `tokenName`, `tokenSymbol`, `contractAddress`).
- Handle missing `functionName` by filtering out empty rows.

### 3. Model Training
- Implemented a wallet-level **LSTM classifier** for sequential forecasting.
- Trained on **80% wallets**, validated on **20%**.
- Output metrics: **Accuracy, Precision, Recall, F1**.

### 4. Forecasting
- Given a wallet address, the model forecasts its **fraud risk score** based on historical transactions.
- Predictions are aggregated across multiple transactions.


