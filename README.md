
# Audio-Based Emotion Recognition Web App

A machine learning-powered web application that identifies emotions in speech audio clips. This project uses audio feature extraction and classification models to recognize human emotions such as **Angry, Calm, Fearful, Happy, Neutral, Sad, and Surprised**.

---

## Live Demo

**Streamlit App**:  https://058d-34-19-45-180.ngrok-free.app/
---

## Project Overview

```text
Emotion-Recognition/
├── app.py                   # Streamlit frontend
├── predict.py               # Audio prediction logic
├── notebook.ipynb            # Full training pipeline 
├── requirements.txt         # Dependencies
├── README.md                # Documentation
│
├── model/                   # Saved models and scalers
    ├── emotion_model.pkl
    ├── scaler.pkl
    ├── pca.pkl
    └── label_encoder.pkl

```
---

## Objective

To build an interactive tool that:

• Accepts a user-uploaded `.wav` or `.mp3` file  
• Automatically extracts and processes key audio features using Librosa  
• Predicts the emotion present in the audio using a pre-trained machine learning model  
• Presents the result in a clean and user-friendly web interface powered by Streamlit

## Methadology

1. **Feature Extraction**  
   Audio files are processed using Librosa to extract:  
   • MFCCs  
   • Chroma Features  
   • Mel Spectrogram  
   • Spectral Contrast  
   • Tonnetz Features  
   **Output:** 193-dimensional feature vector per audio sample.
   
2. **Preprocessing**  
   Audio features are transformed through:  
   • MinMax Scaling to normalize feature values  
   • PCA to reduce noise and dimensionality (retaining 98% variance)
3. **Classification**  
   Two classifiers were trained and evaluated:  
   • MLP (Multi-layer Perceptron) – deep neural net with dropout and regularization  
   • SVC (Support Vector Classifier) – with tuned hyperparameters for improved performance
   
The best results were achieved using SVC after removing underperforming emotion classes (like 'Disgust').

## 📊 Model Performance

| Metric         | Value        |
|----------------|--------------|
| Test Accuracy  | **80.75%**    |
| Macro F1-score | **80.9%**    |
| Macro Recall  | **80.6%**    |
| Best Model     | SVC (after PCA & Scaling)
| Classes        | Angry, Calm, Fearful, Happy, Neutral, Sad, Surprised

> The class "Disgust" was dropped due to overlap and low separability, improving model generalization.

## Tech Stack

• Python 3.x  
• Librosa – for audio feature extraction  
• scikit-learn – for ML models, scaling, and PCA  
• TensorFlow / Keras – for MLP model implementation  
• Streamlit – to build the interactive web app  
• Ngrok – for deployment (e.g., via Colab tunnels)

## Setup Instructions

Clone the repository and navigate to the project directory:

```bash
git clone https://github.com/yourusername/Emotion-Recognition.git
cd Emotion-Recognition

```
## Install Dependencies

Install the required Python packages using:

```bash
pip install -r requirements.txt

```
## 🚀 Run the App (Local + Public URL)

To launch the Streamlit app locally and expose it via LocalTunnel:

```bash
!streamlit run app.py & npx localtunnel --port 8501
