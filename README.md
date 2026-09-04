
# 🤖 Resume AI

> An AI-powered resume management and optimization platform built with **Flask**, **Google Gemini**, and **ReportLab**.

Resume AI is a web application designed to help users manage and improve their resumes through AI-assisted analysis, ATS evaluation, resume management, and portfolio functionality.

---

## ✨ Features

### 📄 Resume Management

* Upload and manage resume files
* Organize resume-related information
* Work with resume content through a dedicated resume module
* Store uploaded files securely in the application upload directory

### 🤖 AI-Powered Analysis

* AI-assisted resume analysis
* Generate intelligent suggestions and improvements
* Uses the **Google Gemini API** for AI functionality
* Dedicated AI service layer for maintainable integration

### 🎯 ATS Analysis

The application includes a dedicated ATS analysis module to help evaluate resumes for applicant-tracking-system compatibility.

* Resume ATS evaluation
* Identify potential resume issues
* Improve resume structure and content
* Dedicated ATS service architecture

### 📊 Dashboard

A dedicated dashboard provides an application interface for accessing resume-related functionality and insights.

### 🌐 Portfolio

The application includes portfolio functionality, allowing users to manage and present professional information alongside their resume.

### 📑 PDF Generation

Resume-related documents can be processed through a dedicated PDF service powered by **ReportLab**.

### 🔐 Authentication

The project includes an authentication module for handling user access and protected functionality.

---

## 🛠️ Tech Stack

| Technology    | Purpose                   |
| ------------- | ------------------------- |
| Python        | Backend programming       |
| Flask         | Web application framework |
| Google Gemini | AI-powered functionality  |
| ReportLab     | PDF generation            |
| SQLite        | Local database            |
| python-dotenv | Environment configuration |
| Werkzeug      | Flask/WSGI utilities      |

---

## 🏗️ Project Architecture

```text
resume_ai/
│
├── database/
│   └── db.py
│
├── routes/
│   ├── ai.py
│   ├── ats.py
│   ├── auth.py
│   ├── dashboard.py
│   ├── portfolio.py
│   └── resume.py
│
├── services/
│   ├── ai_service.py
│   ├── ats_service.py
│   └── pdf_service.py
│
├── static/
│   ├── css/
│   ├── js/
│   └── assets/
│
├── templates/
│   ├── authentication pages
│   ├── dashboard pages
│   ├── resume pages
│   ├── ATS pages
│   └── portfolio pages
│
├── uploads/
│   └── uploaded resume files
│
├── app.py
├── config.py
├── database.db
├── requirements.txt
└── README.md
```

---

## 🔄 Application Flow

```text
             ┌─────────────────┐
             │      User       │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │  Flask Web App  │
             └────────┬────────┘
                      │
        ┌─────────────┼─────────────┐
        ▼             ▼             ▼
   ┌─────────┐   ┌─────────┐   ┌───────────┐
   │ Resume  │   │   ATS   │   │ Portfolio │
   │ Module  │   │ Module  │   │  Module   │
   └────┬────┘   └────┬────┘   └───────────┘
        │             │
        ▼             ▼
   ┌─────────────────────────┐
   │       Services Layer    │
   ├──────────┬──────────────┤
   │ AI       │ ATS          │
   │ Service  │ Service      │
   └────┬─────┴──────┬───────┘
        │            │
        ▼            ▼
   ┌─────────┐   ┌──────────┐
   │ Gemini  │   │ Database │
   │   API   │   │  SQLite  │
   └─────────┘   └──────────┘
```

---

## 📋 Requirements

Before running the project, make sure you have:

* Python 3.10 or newer
* pip
* Git
* Google Gemini API key

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Santhoshsubramani22/resume_ai.git
cd resume_ai
```

### 2. Create a Virtual Environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### Linux / macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Environment Configuration

Create a `.env` file in the project root:

```env
SECRET_KEY=your-secret-key
GEMINI_API_KEY=your-gemini-api-key
```

### Configuration

The application reads the following configuration values:

| Variable         | Description                  |
| ---------------- | ---------------------------- |
| `SECRET_KEY`     | Flask application secret key |
| `GEMINI_API_KEY` | Google Gemini API key        |

The application limits uploaded files to **5 MB**.

> ⚠️ Never commit your real API key or production secret key to GitHub.

---

## ▶️ Run the Application

Start the Flask application with:

```bash
python app.py
```

The application runs locally at:

```text
http://127.0.0.1:5000
```

Open the URL in your browser.

---

## 🧠 AI Integration

Resume AI uses the Google Gemini API through a dedicated AI service.

The API key is configured through:

```env
GEMINI_API_KEY=your-api-key
```

The AI functionality is separated into:

```text
services/ai_service.py
```

This separation makes it easier to maintain or extend the AI functionality in the future.

---

## 🎯 ATS Analysis

The ATS functionality is organized into its own route and service modules:

```text
routes/ats.py
services/ats_service.py
```

This architecture allows ATS-related functionality to remain independent from the main resume and AI components.

---

## 📄 PDF Generation

PDF-related functionality is handled by:

```text
services/pdf_service.py
```

The project uses:

```text
ReportLab
```

for PDF generation.

---

## 🗄️ Database

The application uses a local SQLite database:

```text
database.db
```

Database-related functionality is organized under:

```text
database/
```

The database path is configured automatically through `config.py`.

---

## 📁 Uploads

Uploaded resume files are stored in:

```text
uploads/
```

The application automatically creates the configured upload directory when the Flask application starts.

Maximum upload size:

```text
5 MB
```

---

## 🧩 Flask Blueprints

The application uses Flask Blueprints to separate different areas of functionality.

### Authentication

```text
routes/auth.py
```

Handles authentication-related functionality.

### Dashboard

```text
routes/dashboard.py
```

Handles dashboard functionality.

### Resume

```text
routes/resume.py
```

Handles resume-related functionality.

### AI

```text
routes/ai.py
```

Handles AI-related functionality.

### ATS

```text
routes/ats.py
```

Handles ATS analysis functionality.

### Portfolio

```text
routes/portfolio.py
```

Handles portfolio functionality.

---

## 📦 Dependencies

The current project uses the following packages:

```text
Flask==3.0.2
Werkzeug==3.0.1
python-dotenv==1.0.1
reportlab==4.1.0
google-genai==2.14.0
```

Install them with:

```bash
pip install -r requirements.txt
```

---

## 🔒 Security Recommendations

For production deployment:

* Use a strong randomly generated `SECRET_KEY`
* Keep `GEMINI_API_KEY` in environment variables
* Never commit `.env` files
* Do not expose API keys in frontend code
* Restrict uploaded file types
* Validate uploaded files before processing
* Run Flask behind a production WSGI server
* Use HTTPS
* Regularly update dependencies
* Avoid committing generated databases or sensitive uploads

---

## 🧪 Development

During development, the application can be started using:

```bash
python app.py
```

The current Flask configuration runs the application in debug mode for local development.

For production environments, use an appropriate WSGI server and production configuration.

---

## 🗺️ Roadmap

Potential future improvements include:

* [ ] Advanced ATS scoring
* [ ] Resume keyword optimization
* [ ] Job-description matching
* [ ] Multiple resume templates
* [ ] More export formats
* [ ] Resume version history
* [ ] Enhanced portfolio customization
* [ ] User profile management
* [ ] Improved analytics dashboard
* [ ] Cloud deployment support
* [ ] Automated testing
* [ ] Production-ready authentication and security

---

## 🤝 Contributing

Contributions are welcome!

### 1. Fork the repository

```bash
git clone https://github.com/Santhoshsubramani22/resume_ai.git
```

### 2. Create a feature branch

```bash
git checkout -b feature/your-feature
```

### 3. Make your changes

Implement and test your changes locally.

### 4. Commit your changes

```bash
git add .
git commit -m "Add your feature"
```

### 5. Push your branch

```bash
git push origin feature/your-feature
```

### 6. Open a Pull Request

Create a pull request describing your changes.

---

## 📜 License

Please refer to the repository for the applicable project license.

---

## 👨‍💻 Author

**Santhosh Subramani**

GitHub:

```text
https://github.com/Santhoshsubramani22
```

Repository:

```text
https://github.com/Santhoshsubramani22/resume_ai
```

---

## ⭐ Support

If you find this project useful:

* ⭐ Star the repository
* 🍴 Fork the project
* 🐛 Report bugs through GitHub Issues
* 💡 Suggest new features
* 🤝 Contribute improvements

---

## 📌 Project Summary

**Resume AI** is a Flask-based resume platform combining:

```text
Resume Management
        +
AI Assistance
        +
ATS Analysis
        +
Portfolio Management
        +
PDF Generation
        +
Authentication
        +
SQLite Database
```

The modular architecture makes the project suitable for further development into a complete AI-powered career and resume management platform.

You can paste this directly into `README.md`. I kept the claims aligned with the repository’s actual Flask structure, configuration, routes, services, and dependencies. ([GitHub][2])

[1]: https://github.com/Santhoshsubramani22/resume_ai "GitHub - Santhoshsubramani22/resume_ai · GitHub"
[2]: https://github.com/Santhoshsubramani22/resume_ai/blob/main/app.py "resume_ai/app.py at main · Santhoshsubramani22/resume_ai · GitHub"
