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

yaml
Copy
Edit

---

## 🛠️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/resume-screening-app.git
cd resume-screening-app
2. Install Dependencies
bash
Copy
Edit
pip install -r requirements.txt
If you don't have a requirements.txt, use:

bash
Copy
Edit
pip install flask flask_sqlalchemy python-dotenv pandas scikit-learn google-generativeai python-docx PyMuPDF
3. Configure API Key
Create a .env file in the root folder:

ini
Copy
Edit
GEMINI_API_KEY=your_gemini_api_key_here
Get your key from https://ai.google.dev

4. Train the Model
Run the training script:

bash
Copy
Edit
cd model
python train_model.py
This uses data/cleaned_resumes.csv and saves trained_model.pkl in the model/ folder.

5. Run the App
bash
Copy
Edit
cd ..
python app.py
Visit: http://127.0.0.1:5000

📊 Dashboard
Navigate to /dashboard or click "View Dashboard" on the homepage.

It displays:

Upload history (filename, selected/predicted role)

Whether the model prediction fit the selected role

Model accuracy percentage

🤖 How the Model Works
Uses TfidfVectorizer + RandomForestClassifier

Trained on cleaned text labeled by role/category

Compares predicted vs user-selected role

🔮 Gemini API Integration
Used for:

Generating interview questions (if resume fits)

Giving resume improvement suggestions (if not fit)

Example Prompts:

"Provide 5 interview questions for a Software Engineer role."

"Suggest improvements for a resume applying to a Data Scientist role."

🧪 Sample Resume (Optional)
You can upload any of your resumes in PDF or DOCX format.
To test, you can create a dummy resume for roles like:

Software Engineer

Data Scientist

Machine Learning Engineer

DevOps Engineer

📌 Environment Notes
.env → holds Gemini API key

trained_model.pkl → saved ML model

resume_history.db → created with SQLAlchemy

resume_parser.py → extracts text from resume files

💡 Future Improvements
Add interactive charts to dashboard

Export analysis as downloadable PDF reports

Add login/authentication for users

Improve resume text extraction with OCR fallback

🙌 Credits
Built with ❤️ using:

Flask

Scikit-learn

Google Gemini API

PyMuPDF, python-docx

Bootstrap 5