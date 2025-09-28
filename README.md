# Aptitude System Web Application

This is a full-stack web application designed for administering aptitude tests, generating AI-powered performance reports, and providing an interactive quiz experience. It uses a **Flask backend** for APIs, a **React frontend** for UI, and integrates **Google Gemini AI** for summarizing test performance.

---

## Features

- **User Authentication**: Signup and login with hashed passwords.
- **Dataset Upload**: Upload CSV or Excel files containing questions.
- **Dynamic Quiz**: Questions are selected dynamically based on difficulty and topic.
- **Score Tracking**: Tracks correct answers, time per question, and average time.
- **AI Report Generation**: Generates PDF/Word reports with AI-powered analysis and motivational feedback.
- **Chatbot**: Integrated Gemini AI chatbot for guidance and support.
- **Multi-level Difficulty**: Supports progression from Very Easy → Easy → Moderate → Difficult levels.

---

## Tech Stack

- **Backend**: Flask, Flask-CORS, Flask-SQLAlchemy
- **Frontend**: React.js, React Router
- **Database**: SQLite (users.db)
- **AI Integration**: Google Gemini AI (`google-generativeai`)
- **Python Libraries**: pandas, openpyxl, matplotlib, seaborn, python-docx, python-dotenv, werkzeug

---

## Prerequisites

- Python 3.10+
- Node.js 18+
- pip or pipenv
- Virtual environment (recommended)

---

## Backend Setup (Flask)

1. Clone the repository:

```bash
git clone https://github.com/yourusername/aptitude-system.git
cd aptitude-system/backend

python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate

pip install -r requirements.txt

python app.py

npm install

npm start

aptitude-system/
├── backend/
│   ├── app.py                      # Flask backend
│   ├── ml_model/                   # Report generator module
│   │   ├── __init__.py
│   │   └── report_generator.py
│   ├── reports/                    # Generated PDF/Word reports
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── App.js
│   │   └── components/
│   │       ├── Login.js
│   │       ├── Signup.js
│   │       ├── UploadDataset.js
│   │       └── QuizPage.js
│   └── package.json
├── users.db                        # SQLite DB at project root
└── README.md
