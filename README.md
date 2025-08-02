```markdown
# 📊 Bitbash Job Listing Web App

A full-stack web application for actuarial job listings. This project includes:
- A **Flask REST API** backend with SQLAlchemy + PostgreSQL
- A **React frontend** for listing, adding, editing, deleting, filtering, and sorting jobs
- A **Selenium-based scraper** that pulls jobs from [Actuary List](https://www.actuarylist.com)
- A clean, responsive UI and well-structured codebase
- A video walkthrough showcasing features, architecture, and challenges

---

## 🗂️ Project Structure

```

project-root/
├── backend/
│   ├── app.py
│   ├── models.py
│   ├── routes.py
│   ├── config.py
│   ├── scraper/
│   │   └── scrape\_jobs.py
│   ├── requirements.txt
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── App.js
│   │   ├── index.js
│   ├── package.json
├── README.md
└── .env.example

````

---

## 🚀 Getting Started

### 🔧 Backend Setup (Flask + PostgreSQL)

1. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
````

2. **Install dependencies**

   ```bash
   pip install -r backend/requirements.txt
   ```

3. **Set up database**

   * Create a PostgreSQL database named `bitbash_jobs`
   * Copy `.env.example` to `.env` and configure DB credentials

4. **Run backend server**

   ```bash
   python backend/app.py
   ```

   The API will run on: `http://localhost:5000`

---

### 🌐 Frontend Setup (React)

1. **Install frontend dependencies**

   ```bash
   cd frontend
   npm install
   ```

2. **Start development server**

   ```bash
   npm start
   ```

   React app runs on: `http://localhost:3000`

---

### 🤖 Scraper Setup (Selenium)

1. **Install ChromeDriver** (matching your browser version)

2. **Install dependencies**

   ```bash
   pip install selenium beautifulsoup4
   ```

3. **Run the scraper**

   ```bash
   python backend/scraper/scrape_jobs.py
   ```

   This will populate jobs into your database using SQLAlchemy.

---

## 🛠 Features Overview

### ✅ Backend (Flask API)

* `GET /jobs`: List all jobs

  * Supports filtering: `?location=...`, `?job_type=...`, `?tag=...`
  * Supports sorting: `?sort=posting_date_desc`
* `GET /jobs/<id>`: Retrieve single job
* `POST /jobs`: Create a new job
* `PUT /jobs/<id>`: Update a job
* `DELETE /jobs/<id>`: Delete a job

### 🧑‍💻 Frontend (React)

* Responsive Job Cards UI
* Add / Edit / Delete jobs
* Form validation and error handling
* Filtering by job type, tags, location
* Sorting by posting date
* Live updates after CRUD actions

### 🕷 Web Scraper (Selenium)

* Extracts job title, company, location, date, job type, and tags
* Supports scrolling/loading more jobs
* Inserts into DB via SQLAlchemy (avoids duplicates)
* Scripted for easy manual run

---

## 📹 Video Demo

📥 **\[→ Download Video from Drive Link Here ←]**

Includes:

* Feature walkthrough
* Architecture explanation
* Demo of full CRUD + filtering/sorting
* Scraper run
* Challenges faced

---

## ⚙️ Tech Stack

* **Frontend**: React, Axios, Bootstrap/Material UI
* **Backend**: Flask, SQLAlchemy, PostgreSQL
* **Scraper**: Selenium, BeautifulSoup
* **Tools**: ChromeDriver, dotenv, CORS, Flask-RESTful

---

## 📌 Assumptions & Decisions

* **Tags** stored as a comma-separated string
* **Posting date** is stored as a text string (can improve later)
* **No user authentication** implemented
* **Scraper** loads first \~50 jobs only for demo
* **Database** initialized using `db.create_all()` (no migrations)

---

## 📝 To-Do / Future Enhancements

* Use Alembic for DB migrations
* Convert posting dates to ISO format
* Paginate results in frontend
* Add unit tests for API
* Deploy app (Heroku/Vercel)

---

