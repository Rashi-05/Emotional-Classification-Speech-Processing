# Emotional-Classification-Speech-Processing

# 🎧 Audio-Based Emotion Recognition Web App

A machine learning-powered web application that identifies emotions in speech audio clips. This project uses audio feature extraction and classification models to recognize human emotions such as **Angry, Calm, Fearful, Happy, Neutral, Sad, and Surprised**.

---

## 🌐 Live Demo

🔗 **Streamlit App**: https://2607-34-19-45-180.ngrok-free.app/

---

## 📁 Project Overview

```text
Emotion-Recognition/
├── app.py                   # Streamlit frontend
├── predict.py               # Audio prediction logic
├── train_model.py           # Full training pipeline (SVC/MLP + preprocessing)
├── requirements.txt         # Dependencies
├── README.md                # Documentation
│
├── model/                   # Saved models and scalers
│   ├── emotion_model.pkl
│   ├── scaler.pkl
│   ├── pca.pkl
│   └── label_encoder.pkl
│
└── test_audio/              # Sample input files
    └── sample.wav
