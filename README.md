# 🏥 Disease Predictor – AI Medical Assistant

An intelligent medical diagnosis system powered by machine learning that predicts possible diseases and provides treatment recommendations based on patient‑reported symptoms.

🌐 **Live Demo:** [https://disease-predictor-omega.vercel.app](https://disease-predictor-omega.vercel.app)

![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)
![Backend](https://img.shields.io/badge/Backend-FastAPI-blue)
![Frontend](https://img.shields.io/badge/Frontend-React-blue)
![Python](https://img.shields.io/badge/Machine%20Learning-Python-yellow)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 🌟 Features

### 🤖 AI‑Powered Diagnosis
- Supports **41 diseases**
- Recognizes **132 symptoms**
- Trained Support Vector Classifier (SVC)
- Predicts instantly from symptom input

### 📋 Comprehensive Medical Information
- Disease descriptions and precautions  
- Medication and diet recommendations  
- Exercise guidelines  

### 🎨 Modern UI/UX
- Medical‑themed responsive design  
- Symptom chips and quick selectors  
- Loading animations and progress feedback  

### 🔒 Responsible Use
- Clear medical disclaimer  
- Informational only — encourages professional consultation  

---

## 🏗️ Architecture

```
Disease-Predictor/
├── backend/
│   ├── main.py              # FastAPI API server
│   ├── requirements.txt     # Python dependencies
│   ├── models/svc.pkl       # Trained ML model
│   └── datasets/            # CSV datasets for symptoms, precautions, etc.
└── frontend/
    ├── src/App.js           # Main React component
    ├── public/images/       # UI assets (icons, avatars)
    ├── package.json         # Node dependencies
    └── build/               # Production build
```

---

## 🚀 Quick Start

### 🔧 Prerequisites
- **Python 3.8+**  
- **Node.js 14+**  
- **npm** or **yarn**

### 🧠 Backend Setup

```bash
git clone <repository-url>
cd backend
python -m venv venv
source venv/bin/activate      # (Windows: venv\Scripts\activate)
pip install -r requirements.txt
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

Backend local → **http://localhost:8000**  
Production → **https://backend-it21.onrender.com**

---

### 💻 Frontend Setup

```bash
cd frontend
npm install
npm start
```

Frontend local → **http://localhost:3000**  
Production → **https://disease-predictor-omega.vercel.app**

---

## 🌐 API Endpoints

| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/` | GET | Welcome page |
| `/health` | GET | Health check |
| `/symptoms` | GET | Available symptoms |
| `/diseases` | GET | Supported diseases |
| `/predict` | POST | Predicts disease from symptoms |
| `/disease-info/{name}` | GET | Detailed disease info |

**Sample Request**
```bash
curl -X POST https://backend-it21.onrender.com/predict \
 -H "Content-Type: application/json" \
 -d '{"symptoms": ["headache", "fever", "cough"]}'
```

**Sample Response**
```json
{
  "predicted_disease": "Common Cold",
  "description": "The common cold is a viral infection...",
  "precautions": ["Rest", "Hydrate", "Use humidifier"],
  "medications": ["Acetaminophen", "Ibuprofen"],
  "diet": ["Warm liquids", "Fruits with Vitamin C"],
  "workout": ["Light stretching"]
}
```

---

## 🧠 Machine Learning Model

- **Algorithm**: Support Vector Classifier (SVC)  
- **Features**: 132 symptom variables  
- **Training**: Binary encoded symptom vectors  
- **Deployment**: Serialized (`svc.pkl`) for FastAPI inference  

---

## 🔧 Configuration

**Backend CORS:**
```python
allow_origins = [
    "http://localhost:3000",
    "https://disease-predictor-omega.vercel.app"
]
```

**Frontend API URL:**
```javascript
const API_BASE_URL = "https://backend-it21.onrender.com";  // production
```

---

## ☁️ Deployment Guide

### Backend on Render
```bash
cd backend
pip freeze > requirements.txt
```

1. Sign in to [Render](https://render.com) → **New Web Service**  
2. Connect your GitHub repository  
3. Build: `pip install -r requirements.txt`  
4. Start: `uvicorn main:app --host 0.0.0.0 --port 8000`  
5. Deploy 🎉  

### Frontend on Vercel / Netlify
```bash
cd frontend
npm run build
```
Deploy the `build/` folder via Vercel or Netlify.

---

## ⚙️ Environment Variables

```bash
# Backend
PORT=8000
CORS_ORIGINS=http://localhost:3000,https://disease-predictor-omega.vercel.app

# Frontend
REACT_APP_API_URL=https://backend-it21.onrender.com
```

---

## 🔒 Medical Disclaimer

This project is for **educational and informational purposes only**.  
It is not a substitute for professional medical advice, diagnosis, or treatment.  

- Not an FDA‑approved medical device  
- Always consult a qualified healthcare provider  
- In emergencies, contact local emergency services  

---

## 👩‍💻 Authors

- **Alizay Nasir** — Backend Development & ML Model  
- **Hafiz Hamza Ahmed** — Frontend Development & UI/UX  

---

## 📝 License

Licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

**Made with ❤️ for better healthcare accessibility**  
*This tool assists — it does not replace — professional medical consultation.*
