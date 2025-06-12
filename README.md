# Xandronyx.ML

> 🛡️ A machine learning-based Android malware detection system combining static analysis and intelligent threat identification.

**Xandronyx.ML** is a comprehensive toolkit for Android malware detection. It leverages multiple machine learning models to classify APK files using static analysis and includes a SHA-256-based malware hash checker with API support.

## 📁 Project Structure

```
Xandronyx.ML
    │
    ├── Android Malware Legit.csv                 # Malware dataset
    │
    ├── Cat Boost Classifier                      # CatBoost model folder
    │   ├── Cat Boost Classifier.ipynb            # Training notebook
    │   ├── Dataset Split                         # Data splits
    │   │   └── Cat Boost Classifier.pkl
    │   └── Model                                 # Saved model
    │       └── Cat Boost Classifier.cbm
    │
    ├── Ensembled Model                           # Ensemble model folder
    │   ├── Dataset Split                         # Data splits
    │   │   └── Ensembled Model.pkl
    │   ├── Ensembled Model.ipynb                 # Training notebook
    │   └── Model                                 # Saved model
    │       └── Ensembled Model.pkl
    │
    ├── Gradient Boosting Classifier              # Gradient boosting folder
    │   ├── Dataset Split                         # Data splits
    │   │   └── Gradient Boosting Classifier.pkl
    │   ├── Gradient Boosting Classifier.ipynb    # Training notebook
    │   └── Model                                 # Saved model
    │       └── Gradient Boosting Classifier.pkl
    │
    ├── Hash and Url Checker                      # Hash/URL tools
    │   ├── Hash and Url Checker.ipynb            # Checker notebook
    │   └── Sample APKs                           # Example APK files
    │       └── GlamLive.apk                      # Sample APK
    |
    ├── LICENSE                                   # License
    │
    ├── Logistic Regression                       # Logistic Regression folder
    │   ├── Dataset Split                         # Data splits
    │   │   └── Logistic Regression.pkl
    │   ├── Logistic Regression.ipynb             # Training notebook
    │   └── Model                                 # Saved model
    │       └── Logistic Regression.pkl
    │
    └── README.md                                 # This README
```

## 📦 Dataset

- **Primary Dataset**: [`Android Malware Legit.csv`](Android%20Malware%20Legit.csv), sourced from [Kaggle](https://www.kaggle.com/code/mohit55/android-malware-detection-99-24/input).
- **SHA-256 Signatures**: Retrieved from [MalwareBazaar](https://bazaar.abuse.ch/browse/tag/apk/) and used for static hash-based detection in the [Hash and Url Checker](/Hash%20and%20Url%20Checker/).


## ⚙️ Setup Instructions

### 1️⃣ Install Dependencies

Ensure you have **Python 3.8+** installed.  
Install required packages for machine learning models:
```bash
pip install pandas numpy scikit-learn catboost matplotlib seaborn joblib
```

Install additional tools for hash and URL analysis:
```bash
pip install requests python-dotenv zipfile36 python-magic
```

### 2️⃣ Opening and Running the Notebooks

You can open and run the `.ipynb` notebooks directly in your development environment. Each notebook contains step-by-step code blocks that can be executed interactively.

## 🚀 How to Use

### 1️⃣ Malware Hash + URL/Domain Analysis

1. Open [Hash and Url Checker.ipynb](./Hash%20and%20Url%20Checker/Hash%20and%20Url%20Checker.ipynb).
2. Run the cells in sequence.
3. You’ll be prompted to:
- Provide a path to an APK file
- Extract and analyze SHA-256 hash against MalwareBazaar
- Parse embedded URLs/domains
- Check malicious endpoints using URLhaus
- Summarize risks and analysis results  
> 🔐 Requires a [.env](.env) file with API_KEY for MalwareBazaar access.

### 2️⃣ **Machine Learning Classifiers**

To train and evaluate models, open and run the respective notebook:
  - [Cat Boost Classifier.ipynb](./Cat%20Boost%20Classifier/Cat%20Boost%20Classifier.ipynb)
  - [Gradient Boosting Classifier.ipynb](./Gradient%20Boosting%20Classifier/Gradient%20Boosting%20Classifier.ipynb)
  - [Logistic Regression.ipynb](./Logistic%20Regression/Logistic%20Regression.ipynb)
  - [Ensembled Model.ipynb](./Ensembled%20Model/Ensembled%20Model.ipynb)

> 📌 Ensure [Android Malware Legit.csv](Android%20Malware%20Legit.csv) is in the project root.

## 🛡️ Notes

- SHA-256 checks use signature matching only (no file unpacking or behavioral analysis).
- Domain/URL analysis is string-based and backed by public blacklists.

## 📄 License

This project is licensed under the [Apache License 2.0](LICENSE).