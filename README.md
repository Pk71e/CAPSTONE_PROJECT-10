# CAPSTONE_PROJECT-10
intensity_classifier

# Emotion Intensity Classification (Anger, Happiness, Sadness)

This project builds an NLP-based machine learning model to classify customer text reviews into emotional intensities: **anger**, **happiness**, and **sadness**.

## 📁 Project Structure

```
intensity-analysis/
├── data/
│   ├── angriness.csv
│   ├── happiness.csv
│   └── sadness.csv
├── intensity_analysis.ipynb
├── intensity_classifier.pkl
├── README.md
└── report/
    └── final_report.pdf
```

## ⚙️ Installation

1. Clone the repository or extract the zip file.
2. Create a virtual environment (optional but recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   ```
3. Install the required packages:
   ```
   pip install -r requirements.txt
   ```

## 🚀 Running the Project

1. Open the notebook:
   ```
   jupyter notebook intensity_analysis.ipynb
   ```

2. Follow the steps in the notebook to:
   - Load and clean the data
   - Train and evaluate the model
   - Tune hyperparameters
   - Save the final model

3. The final model is saved as `intensity_classifier.pkl` and can be used in a Flask API.

## 🧪 Model Performance

- Uses Multinomial Naive Bayes + TF-IDF
- Accuracy > 81% on test data
- Includes classification report and confusion matrix

## 📦 Deployment Plan

The model can be deployed using a Flask or FastAPI REST API for real-time predictions. Example snippet:

```python
from flask import Flask, request, jsonify
import joblib

app = Flask(__name__)
model = joblib.load('intensity_classifier.pkl')

@app.route('/predict', methods=['POST'])
def predict():
    text = request.json['text']
    prediction = model.predict([text])[0]
    return jsonify({'emotion': prediction})
```

## 📝 Author

Developed as part of a customer review emotion analysis project.
