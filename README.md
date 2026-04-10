# Skin-Disease-Prediction-System

# 🩺 Skin Disease Prediction System

A full-stack web application that uses **Machine Learning & Computer Vision** to classify skin diseases from uploaded images — delivering predictions in under **2 seconds** with **85–92% classification accuracy**.

Built with **Flask**, **TensorFlow/Keras**, and **OpenCV**.

---

## 📸 Demo

> Upload a skin image → Get an instant AI-powered prediction with confidence scores.

*(Add a screenshot here after running the app)*

---

## ✨ Features

- 🔍 **Real-time prediction** — results in < 2 seconds
- 📊 **Top-5 confidence scores** displayed visually
- 🖼️ **Drag & drop** image upload with live preview
- 🧠 **CNN-based model** trained on a large labeled dataset
- 🌐 **Clean web UI** — works on desktop and mobile
- ⚠️ Medical disclaimer included for responsible use

---

## 🦠 Supported Skin Conditions

| Disease | Description |
|---|---|
| Acne | Inflammatory skin condition |
| Eczema | Chronic itchy skin inflammation |
| Melanoma | Dangerous form of skin cancer |
| Psoriasis | Autoimmune scaly skin patches |
| Rosacea | Chronic facial redness |
| Seborrheic Keratosis | Non-cancerous skin growths |
| Tinea (Ringworm) | Fungal infection |
| Vitiligo | Loss of skin pigmentation |

> Update `utils/predictor.py → DISEASE_CLASSES` to match your model's training labels.

---

## 🗂️ Project Structure

```
skin-disease-prediction/
│
├── app.py                  # Flask application entry point
├── requirements.txt        # Python dependencies
├── .gitignore
│
├── model/
│   └── skin_model.h5       # ← Place your trained Keras model here
│
├── utils/
│   ├── __init__.py
│   └── predictor.py        # Model loading & inference logic
│
├── templates/
│   └── index.html          # Frontend HTML
│
└── static/
    ├── css/style.css        # Styling
    ├── js/main.js           # Frontend JS (upload, fetch, render)
    └── uploads/             # Temp storage for uploaded images
```

---

## ⚙️ Setup & Installation

### 1. Clone the repository

```bash
git clone https://github.com/RudranshShukla-Git/skin-disease-prediction.git
cd skin-disease-prediction
```

### 2. Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add your trained model

Place your Keras model file at:

```
model/skin_model.h5
```

> See `model/README.md` for export instructions and Git LFS setup for large files.

### 5. Run the app

```bash
python app.py
```

Open [http://localhost:5000](http://localhost:5000) in your browser.

---

## 🧠 Model Details

| Property | Value |
|---|---|
| Architecture | CNN (e.g., MobileNetV2 / ResNet50) |
| Input size | 224 × 224 px |
| Output | Softmax over N classes |
| Accuracy | ~85–92% on test set |
| Framework | TensorFlow / Keras |

> Update the architecture details above to match your actual model.

---

## 🔌 API Endpoint

### `POST /predict`

**Request:** `multipart/form-data` with field `file` (image)

**Response:**

```json
{
  "disease": "Eczema",
  "confidence": 91.3,
  "all_predictions": [
    { "disease": "Eczema",   "confidence": 91.3 },
    { "disease": "Psoriasis","confidence": 5.2  },
    ...
  ]
}
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python, Flask |
| ML Framework | TensorFlow / Keras |
| Image Processing | OpenCV, Pillow |
| Frontend | HTML5, CSS3, Vanilla JS |
| Deployment (optional) | AWS EC2 / Render / Railway |

---

## 🚀 Deployment (Optional)

### Render / Railway
Push to GitHub and connect your repo. Set the start command to:
```
gunicorn app:app
```

### AWS EC2
```bash
pip install gunicorn
gunicorn -w 2 -b 0.0.0.0:8000 app:app
```

---

## ⚠️ Disclaimer

This application is built for **educational and research purposes only**.  
It is **not a substitute for professional medical diagnosis**.  
Always consult a certified dermatologist for any skin-related concerns.

---

## 👤 Author

**Rudransh Shukla**  
B.Tech IT — PSIT Kanpur  
[LinkedIn](https://linkedin.com/in/rudransh-shukla-4353a22a3) · [GitHub](https://github.com/RudranshShukla-Git)

---

## 📄 License

This project is open source under the [MIT License](LICENSE).
