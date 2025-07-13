# 💳 Credit Card Fraud Detection

This project provides a lightweight and interactive system for detecting fraudulent credit card transactions using a machine learning model deployed via [Streamlit](https://streamlit.io/). It leverages geolocation data, transaction metadata, and trained encoders to classify transactions as legitimate or fraudulent.

---

## 🚀 Features

- 🌍 Uses geodesic distance between cardholder and merchant location
- 🧠 Pre-trained LightGBM model for fraud detection
- 🎯 Label encoders for categorical data
- 📊 Web UI using Streamlit for easy interaction
- 💾 No database needed—everything runs locally
- ✅ Validated input with error handling

---

## 🗂️ Project Structure

```
credit_card_fraud_detection-main/
├── app.ipynb                # Notebook version of the app
├── app.py                   # Main Streamlit application
├── fraud_detection_model.jb # Pre-trained ML model (LightGBM)
├── label_encoders.jb        # Encoded mappings for categorical variables
├── requirements.txt         # Python dependencies
└── .gitignore               # Git ignored files
```

---

## 🧠 Model Details

- **Model Type**: LightGBM Classifier
- **Target Variable**: Binary classification (Fraudulent = 1, Legitimate = 0)
- **Features Used**:
  - Merchant Name
  - Category
  - Transaction Amount
  - Haversine Distance (user ↔ merchant)
  - Transaction Time: Hour, Day, Month
  - Gender
  - Hashed Credit Card Number

---

## 📦 Setup Instructions

### ✅ 1. Clone the Repository

```bash
git clone https://github.com/your-username/credit_card_fraud_detection.git
cd credit_card_fraud_detection-main
```

### ✅ 2. Create & Activate Virtual Environment (Optional but Recommended)

```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

### ✅ 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the App

Use the command below to launch the Streamlit web interface:

```bash
streamlit run app.py
```

Fill in the transaction details and click **"Check For Fraud"** to receive a prediction.

---

## 📈 How It Works

- Uses `geopy` to calculate the distance between user and merchant locations.
- Preprocesses user input using trained encoders (`label_encoders.jb`).
- Hashes credit card numbers for privacy (hash modulo 100).
- Predicts transaction status using the saved LightGBM model.

---

## ⚠️ Limitations

- Input categories not seen during training are set to `-1` (unknown).
- Model performance depends on training data quality (not included).
- Credit card number is only hashed—not encrypted or validated.

---

## 👨‍💻 Dependencies

Major libraries used (see `requirements.txt` for full list):

- `streamlit`
- `scikit-learn`
- `pandas`
- `lightgbm`
- `geopy`
- `joblib`

---

## 📜 License

This project is intended for **educational and demonstration** purposes only.

---

## 🙏 Acknowledgments

Inspired by common real-world fraud detection workflows using `scikit-learn` and `LightGBM`. UI powered by Streamlit.

