# AI Lead Intent Score Assignment

## 🔗 Deployed Links

* **Frontend (GitHub Pages):** [https://Dharmik0712.github.io/AI-Lead-Intent-Score-Assignment2/](https://Dharmik0712.github.io/AI-Lead-Intent-Score-Assignment2/)
* **Backend (Render):** [https://ai-lead-score-backend.onrender.com](https://ai-lead-score-backend.onrender.com)

---

## 📁 Project Structure

```
AI-Lead-Intent-Score-Assignment/
├── backend/               # FastAPI backend application
│   ├── app.py             # Main FastAPI app with /score and /leads endpoints
│   ├── model_utils.py     # Logic for model prediction
│   ├── reranker.py        # Rule-based LLM reranker
│   ├── requirements.txt   # Python dependencies
│
├── data/
│   └── synthetic_leads.csv  # 10K+ synthetic lead data with patterns
│
├── model/
│   └── lead_score_model.pkl # Trained model file (XGBoost / GBC)
│
├── frontend/             # React + Tailwind frontend SPA
│   ├── src/
│   │   ├── components/
│   │   │   ├── LeadForm.jsx
│   │   │   ├── LeadTable.jsx
│   │   │   └── ScoreChart.jsx
│   │   ├── App.jsx
│   │   └── index.css
│   ├── vite.config.js
│   ├── package.json
│   └── ...
│
├── README.md             # You're here
└── report.pdf            # 3-page project summary (separate)
```

---

## 📦 Installation Instructions

### ✅ Backend (FastAPI)

```bash
cd backend
pip install -r requirements.txt
uvicorn app:app --reload
```

Backend runs on `http://localhost:8000`

### ✅ Frontend (React + Tailwind)

```bash
cd frontend
npm install
npm run dev
```

Frontend runs on `http://localhost:5173`

---

## 📌 Features

* 🎯 Lead form to input name, email, comment & consent
* ⚙️ FastAPI backend accepts JSON and scores intent
* 📈 ML Model: XGBoost / GradientBoostingClassifier
* 🤖 Re-ranker adjusts score based on keywords in comment
* 📊 Displays: Name, Email, Initial Score, Reranked Score, Comment
* 🧠 Bonus:

  * Reranked Score sorting
  * LocalStorage persistence
  * Chart.js graph of scores

---

## 🔍 ML Model Overview

* Trained on synthetic dataset of 10,000+ entries
* Features used:

  * Credit Score
  * Age Group
  * Income
  * Family Background
  * Number of Site Visits
* Model saved as `.pkl` and loaded in `model_utils.py`

---

## 🧠 Reranker Logic (LLM-Inspired)

Rule-based scoring based on comment sentiment:

* `urgent` → +15
* `immediate`, `important` → +10
* `not interested`, `spam` → -15
* Score bounded between 0–100

---

## ✅ Compliance

* Consent checkbox required before submitting form
* All data is synthetic; no real PII is collected or stored

---

## 🚀 Deployment Notes

* **Frontend:** GitHub Pages via `gh-pages` package
* **Backend:** Hosted on Render (free tier)

---

## 👤 Author

**Dharmik Sompura**
[GitHub](https://github.com/Dharmik0712)
[LinkedIn](https://www.linkedin.com/in/dharmik-sompura/)
