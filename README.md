# 🧠 AI Resume Screening Web App

A Flask-based web app that uses machine learning and Google Gemini to screen resumes for specific roles, suggest improvements, and generate interview questions. It also tracks model performance via an interactive dashboard.

---

## 🚀 Features

- ✅ Resume category prediction using ML  
- 📁 PDF/DOCX resume uploads  
- 🤖 Google Gemini API integration:  
  - Generates interview questions (if resume fits)  
  - Gives suggestions for improvement (if not fit)  
- 📊 Dashboard with model accuracy & history tracking  
- 🧠 Model training using Random Forest Classifier  
- 🧾 History saved using SQLite (via SQLAlchemy)  

---

## 🗂️ Project Structure

NEW_ML/ │ ├── data/ │ └── cleaned_resumes.csv # Dataset for model training │ ├── model/ │ ├── train_model.py # Script to train and save model │ ├── resume_parser.py # Extracts text from resumes │ └── trained_model.pkl # Trained machine learning model │ ├── templates/ │ ├── index.html # Upload form page │ ├── result.html # Result page after analysis │ └── dashboard.html # Dashboard for history & accuracy │ ├── static/ │ └── (optional CSS, JS, assets) │ ├── app.py # Main Flask web app ├── models.py # Resume history model (SQLAlchemy) ├── .env # API key and env config └── README.md # This documentation file

