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


# ================================
# ED-HACK End-to-End Project Runing Guide
# ================================

# 1️⃣ Set working directory
$ProjectRoot = "C:\Users\Dhamodaran G\Desktop\ED-HACK"
$BackendDir = "$ProjectRoot\backend"
$FrontendDir = "$ProjectRoot\frontend"

# 2️⃣ Clone repo (final branch)
if (!(Test-Path $ProjectRoot)) {
    git clone -b final https://github.com/Dhamo07042006/ED-HACK.git $ProjectRoot
} else {
    Write-Host "Repo already exists. Pulling latest changes..."
    cd $ProjectRoot
    git pull origin final
}

# 3️⃣ Navigate to backend
cd backend

# 4️⃣ Remove old virtual environment if exists
if (Test-Path ".\venv") {
    Write-Host "Removing old virtual environment..."
    Remove-Item -Recurse -Force .\venv
}

# 5️⃣ Create new virtual environment
python -m venv venv

# 6️⃣ Activate virtual environment
Write-Host "Activating virtual environment..."
& .\venv\Scripts\Activate.ps1

# 7️⃣ Upgrade pip
python -m pip install --upgrade pip

# 8️⃣ Install Python dependencies
pip install -r requirements.txt

# 9️⃣ Create database tables
Write-Host "Creating database tables..."
python -c "from app import db, app; from app.models import User; with app.app_context(): db.create_all(); print('Tables created successfully')"

# 🔟 Start Flask backend
Write-Host "Starting Flask backend on http://127.0.0.1:5000..."
Start-Process powershell -ArgumentList "flask run" -NoNewWindow

# 1️⃣1️⃣ Start React frontend
cd frontend

# Install frontend dependencies if node_modules missing
if (!(Test-Path ".\node_modules")) {
    Write-Host "Installing frontend dependencies..."
    npm install
}

Write-Host "Starting React frontend on http://localhost:3000..."
Start-Process powershell -ArgumentList "npm start" -NoNewWindow

Write-Host "✅ ED-HACK RMDE script completed!"

