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
# ED-HACK Project: RMED Guide (End-to-End)

## 1️⃣ R — Run (Clone the Project)

1. Open **PowerShell** or terminal.
2. Navigate to where you want to clone the project:

```powershell
cd "C:\Users\Dhamodaran G\Desktop"
```

3. Clone the `final` branch:

```powershell
git clone -b final https://github.com/Dhamo07042006/ED-HACK.git
cd ED-HACK
```

**Learnings:**
- `git clone` downloads the project.
- `-b final` clones a specific branch.

---

## 2️⃣ M — Manage (Setup Virtual Environment & Dependencies)

### Step 2.1: Navigate to backend
```powershell
cd backend
```

### Step 2.2: Create a virtual environment
```powershell
python -m venv venv
```

**Learn:** Virtual environments isolate project dependencies.

### Step 2.3: Activate the environment
PowerShell:
```powershell
.\venv\Scripts\Activate.ps1
```
CMD:
```cmd
.\venv\Scripts\activate.bat
```

**Learn:** Ensures Python uses this virtual environment.

### Step 2.4: Install dependencies
```powershell
pip install --upgrade pip
pip install -r requirements.txt
```

**Learn:** `requirements.txt` contains all Python packages needed.

---

## 3️⃣ E — Execute (Database & Backend)

### Step 3.1: Create database tables
```powershell
python -c "from app import db, app; from app.models import User; with app.app_context(): db.create_all(); print('Tables created successfully')"
```

**Learn:**  
- `db.create_all()` creates tables based on SQLAlchemy models.  
- `app.app_context()` sets the Flask application context.

### Step 3.2: Start backend server
```powershell
flask run
```

- Default URL: `http://127.0.0.1:5000`  
- API endpoints like `/login` and `/signup` are now active.

---

## 4️⃣ D — Deploy (Frontend & API Integration)

### Step 4.1: Navigate to frontend
Open a **new terminal**:

```powershell
cd ../frontend
```

### Step 4.2: Install Node dependencies
```powershell
npm install
```

### Step 4.3: Start React frontend
```powershell
npm start
```

- Default URL: `http://localhost:3000`  
- Ensure all API fetch URLs in React point to the backend (`http://127.0.0.1:5000`).

**Example in Login.js:**

```javascript
const response = await fetch("http://127.0.0.1:5000/login", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ username, password })
});
```

---

## 5️⃣ Test the App

1. Open browser → `http://localhost:3000`  
2. Test login/signup features.  
3. If errors occur:
   - Backend not running → run `flask run`
   - Fetch URLs incorrect → use full backend URL
   - Database tables missing → run `db.create_all()`

---

## 6️⃣ Optional: Reset Database
```powershell
Remove-Item backend.db
python -c "from app import db, app; from app.models import User; with app.app_context(): db.create_all()"
```

**Learn:** Allows you to start fresh with an empty database.

---

## 7️⃣ Troubleshooting

| Error | Fix |
|-------|-----|
| `Import "pandas" could not be resolved` | Set VS Code interpreter to `venv\Scripts\python.exe` |
| `TypeError: Failed to fetch` | Ensure backend is running; check React fetch URLs |
| `sqlite3.OperationalError: no such table: user` | Run `db.create_all()` |
| Missing packages | Activate venv and run `pip install -r requirements.txt` |

---

## ✅ Key Takeaways (RMED)

- **R — Run:** Clone repo, select branch  
- **M — Manage:** Set up venv, install dependencies  
- **E — Execute:** Backend + database  
- **D — Deploy:** Frontend + API integration  

This guide covers **everything from cloning to running the full project**, so you can learn the workflow and replicate it for any similar Python + React project.
