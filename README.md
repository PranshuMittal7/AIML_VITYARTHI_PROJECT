# 🛡️ Spam Detector AI – Project Documentation

A complete machine-learning based SMS classification system that identifies messages as **Spam** or **Ham** using NLP preprocessing, TF-IDF vectorization, and a trained Support Vector Machine (SVM) model.

---

## 📌 Overview

This project provides a clean, modular, production-grade spam detection system:

* A **Streamlit UI** for real-time predictions
* A full **NLP preprocessing pipeline**
* An **SVM model** wrapped in a scikit-learn pipeline
* **Analytics** such as pie-charts and word clouds
* **History logging** for previous queries
* **Unit tests** for preprocessing and model prediction

The system automatically trains itself if the model file is missing.

---

## ✨ Features

### **1. Real-Time Classification**

* Input email/SMS text and receive instant **Spam (1)** or **Ham (0)** predictions
* Displays a probability-based **confidence score**
* Beautiful gradient-themed UI with animations and custom CSS
* Automatically logs predictions to `history.csv` fileciteturn1file4

### **2. NLP Preprocessing**

Implemented in `preprocessing.py` fileciteturn1file6:

* Lowercasing
* Word tokenization
* Alphanumeric filtering
* Stopword removal
* Punctuation removal
* Stemming using Porter Stemmer

### **3. Model Training and Prediction**

Found in `model.py` fileciteturn1file5:

* Loads SMS dataset from `data/spam.csv`
* Maps labels (ham → 0, spam → 1)
* Creates `transformed_text` using the preprocessing pipeline
* Splits dataset into train/test
* Uses a **TF-IDF + SVM (sigmoid kernel)** pipeline
* Trains model and saves it to `model.pkl`
* Provides a simple `predict_message()` interface

### **4. Analytics Dashboard**

Implemented in `analytics.py` fileciteturn1file2:

* Pie-chart of spam/ham distribution
* Word cloud of most common spam words
* Frequency table of top 30 words

### **5. Query History System**

Implemented in `history.py` fileciteturn1file4:

* Saves every prediction with timestamp, message, confidence
* Loads and sorts history for the UI table

### **6. Unit Tests**

Tests located in the `tests/` directory:

* `test_model.py` validates spam/ham predictions based on example inputs fileciteturn1file0
* `test_preprocessing.py` checks cleaning logic and token transformation behavior fileciteturn1file1

---

## 📂 Project Structure

```
VITYARTHIPROJECT/
├── data/
│   └── spam.csv
│
├── src/
│   ├── analytics.py
│   ├── app.py
│   ├── history.py
│   ├── model.py
│   └── preprocessing.py
│
├── tests/
│   ├── __init__.py
│   ├── test_model.py
│   └── test_preprocessing.py
│
├── model.pkl           # auto-created after training
├── history.csv         # auto-created after predictions
├── README.md
├── requirements.txt
└── statement.md
```

---

## 🚀 Running the Application

### **1. Install Dependencies**

```bash
pip install -r requirements.txt
```

### **2. Launch the Streamlit App**

```bash
streamlit run src/app.py
```

The app will auto-train a model if `model.pkl` is missing.

---

## 🧪 Running Tests

Run all tests:

```bash
python -m unittest discover tests
```

Covers preprocessing and spam prediction logic.

---

## 📊 Dataset

The project uses the classic SMS Spam Collection dataset (`spam.csv`).

Columns used:

* `label` (ham/spam)
* `text` (SMS message)

---

## 👨‍💻 Developer

**Pranshu K. Mittal** – VITYARTHI Project

---

## 📄 License

This project is for academic and educational use.
