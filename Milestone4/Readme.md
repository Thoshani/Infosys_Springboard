
# ✨TextMorph: Text Summarization and Paraphrasing Platform

## Project Overview
TextMorph is an advanced AI-driven platform that transforms complex text into clear, accessible content through intelligent summarization and paraphrasing. Built with cutting-edge transformer models and secure authentication, it serves students, researchers, and professionals seeking to enhance text comprehension and communication.

---
## 🔗 Quick Links

| Category | Details |
|----------|---------|
| **📽️ Demo Video** | https://github.com/Lithicka-G/Infosys_Springboard/blob/main/Milestone4/Milestone%204%20Video.mp4 |
| **🧩 Source Code** | https://github.com/Lithicka-G/Infosys_Springboard/blob/main/Milestone4/Milestone4.ipynb |
| **🐳 Docker Support** | Yes |
| **🧠 AI Models** | Pegasus · BART · FLAN-T5 |

---
## 📑 Table of Contents

- Overview
- Key Features
- Installation
- Usage Guide
- Architecture
- Models & Loading
- Datasets & Evaluation
- Roadmap
- Screenshots
- Security & Privacy
- Team
- License

---
## 📘 About The Project
TextMorph transforms complex, lengthy text into clear summaries and readable paraphrases using adaptive AI models. It supports specialized domains like academic, medical, and legal content, and delivers accurate results through an intuitive interface—no machine learning background required. Optimized for both CPU and CUDA, it’s built for research, education, and enterprise use.
- Built as part of Infosys Springboard Internship Final Project
- Target users: Students, educators, researchers, bloggers, media professionals

#### Key Statistics:
- 86% of students already use AI in their studies.
- In the 2024 Global AI Student Survey (3,839 students, 16 countries), 86% said they use AI tools for coursework. Among the most common use-cases:
- 33% use AI to summarize documents
- 28% use AI to paraphrase a document

---
## 🎯 Problem Statement
 Millions of students, researchers, and professionals struggle with lengthy, technical, or poorly structured documents. Manually summarizing or paraphrasing complex content is time-consuming and requires strong linguistic skills.

TextMorph uses advanced AI to automatically:
- Improve readability while preserving key information
- Condense long documents into clear, concise summaries
- Rewrite content in simpler or more professional language
- Help users learn and understand complex material faster

---
## 🚀 Key Features

1)👤 User Features:

| Feature | Description |
|---------|-------------|
| Secure Login | JWT-based authentication with OTP recovery |
| Easy Input | Paste text or upload documents (PDF/txt) |
| Summarization | Adjustable length: Short/Medium/Long |
| Paraphrasing | Simple, Neutral, and Advanced tones |
| Readability Analysis | Real-time scoring with detailed metrics |
| Side-by-Side Compare | Original vs generated text view |
| Automatic History | Save and access previous operations |
| Feedback System | Rate results and provide comments |
| Document Support | PDF and text extraction for long documents |
| Custom Models | Fine-tuned models for specific domains |
| Data Augmentation | Expand training data for improved accuracy |
| Profile Management | Change password with security validation |

2)👨‍💼 Admin-only Features:

| Feature | Description |
|---------|-------------|
| Admin Limits | Strict limit of two super-admin accounts |
| Admin Access | Manage user accounts (add, remove, promote) |
| Usage Analytics | Charts and real-time insights on platform usage |
| Feedback Monitoring | Track model performance and user ratings |
| Global History | Full access with advanced search filters |
| Audit Logging | Track all critical user and system actions |
| Full Audit View | Complete input/output visibility across all operations |
| Workflow Monitoring | Track workflow patterns and platform performance |

---
## 🧩 Architecture
📌 Architecture Diagram
![Architecture Diagram](https://github.com/user-attachments/assets/ab796282-3ce1-4933-a393-d01f57cdeee1)

📌ER Model Diagram
<img width="6468" height="3489" alt="er diagram" src="https://github.com/user-attachments/assets/e9155251-1d81-460a-9b7c-30c2998de01f" />

---

## 🤖 Models Used

| Model | Purpose | Purpose |
|-------|---------|-----------|
| Pegasus | High-quality abstractive summarization |	Summarization & ParaphrasingT |
| BART | Balanced summarization & rewriting | Summarization & Paraphrasing |
| FLAN-T5 | Paraphrasing & complexity control | Summarization & Paraphrasing |
| Custom Model FLAN-T5 | Domian-Specific NLP tasks | Data Augmentation & Model Tuning |

**Supports model versioning:** custom

---
## 🛠 Tech Stack
<img width="1536" height="1024" alt="Tech Stack" src="https://github.com/user-attachments/assets/37c7b29d-c19e-4b16-b81b-27f530dfc56d" />

---
## 📂 Project Structure

```bash
TextMorph/
│
├── README.md
├── app.py
├── requirements.txt
├── Dockerfile
│
├── models/
│   └── drive_models/
│       ├── flan_t5_medical/
│       ├── flan_t5_news/
│       ├── flan_t5_academic/
│       └── flan_t5_legal/
│
├── assets/
│   └── screenshots/
│
└── docs/
    ├── architecture.png
    ├── er_diagram.png
    └── README_FULL.html
```

---
## ⚙️ Installation & Setup

### Google Colab (Recommended for GPU):
Upload Files to Google Colab:
- Go to Google Colab
- Create a new notebook
- Upload login.py to your Colab environment
- Upload requirements.txt (or create it as shown below)

### Install Dependencies:

```python
# Run this cell in Colab
!pip install streamlit bcrypt pyjwt pandas pypdf nltk transformers qrcode[pil] torch --quiet
!pip install --upgrade transformers --quiet
!pip install pyngrok==7.0.0 --quiet
```
Mount Google Drive (for domain models):

```python
from google.colab import drive
drive.mount('/content/drive')
```

### Configuration
#### 1. Ngrok Authtoken Setup
How to get Ngrok Authtoken:
- Go to ngrok.com
- Sign up for a free account
- Go to Your Authtoken
- Copy your authtoken (looks like: 2abc123def456...)

Update in code:
```python
ngrok.set_auth_token("your-actual-ngrok-authtoken-here")
```

#### 2. JWT Secret Key
Create a strong secret key:
- Use any random string (minimum 32 characters)
- Example: "my_super_secure_jwt_secret_key_2024!"
- Or generate one: https://www.jwt.io/

- Update in code:
```python
SECRET_KEY = "your-strong-secret-key-here-min-32-chars"
```

#### 3. SMTP Email Configuration
How to get Gmail App Password:
- Go to your Google Account: https://myaccount.google.com/
- Enable 2-Factor Authentication
- Go to Security → App passwords
- Generate app password for "Mail"
- Copy the 16-character app password

Update in code:
```python
EMAIL_CONFIG = {
    'smtp_server': 'smtp.gmail.com',
    'smtp_port': 587,
    'sender_email': 'your-email@gmail.com',  # Your actual Gmail
    'sender_password': 'abcd efgh ijkl mnop',  # 16-char app password
    'timeout': 30
}
```
#### Requirements File
Create requirements.txt with this content:

```txt
streamlit==1.28.0
bcrypt==4.0.1
PyJWT==2.8.0
pandas==2.0.3
pypdf==3.17.0
nltk==3.8.1
transformers==4.35.0
torch==2.1.0
qrcode[pil]==7.4.2
scikit-learn==1.3.0
matplotlib==3.7.2
seaborn==0.12.2
wordcloud==1.9.2
pyngrok==7.0.0
```

#### Default Admin Account
- Email: Admin@gmail.com
- Password: Admin123

***Note: This account is automatically created when you first run the application.***

#### Run the Application in Colab
- Clcik Run all in the colab and click on the Streamlit Url at the end to open the app in Streamlit.
- Make sure the runtime is set to GPU
- It will take around 2-3 minutes to load all models in streamlit

---
## 📝 Usage Guide

1. **Register/Login** – Secure JWT authentication
2. **Input Text** – Paste or upload documents (PDF/txt)
3. **Select Task** – Choose summarization or paraphrasing style
4. **Generate & Compare** – View side-by-side results instantly
5. **Save & Rate** – Store in history and provide feedback
   
---
## 📊 Datasets & Evaluation

Evaluation Datasets:

| Dataset | Domain |
|---------|--------|
| ArXiv | Scientific writing |
| CNN/DailyMail | Journalistic content |
| PubMed | Medical literature |
| BillSum | Legal documents |

Evaluation Metrics:

| Metric | Purpose |
|--------|---------|
| ROUGE | Summary quality vs reference |
| BLEU | Output accuracy measurement |
| Lexical Diversity | Vocabulary richness analysis |
| Readability Metrics | Clarity and comprehension scoring |

---
## 🔧 Technical Challenges and Solutions

| Area | Challenge | Solution |
|------|------------|-----------|
| Authentication | Token expiration and session management | Implemented JWT refresh and secure session state in Streamlit |
| Model Integration | High memory usage from PEGASUS and BART | Added model caching and selective loading mechanisms |
| Performance | Slow inference on CPU | Optimized batch processing and added progress indicators |
| Ngrok Stability | Tunnel drops and port conflicts | Implemented auto-reconnect and dynamic port allocation |
| Readability Accuracy | Noise from special characters | Added robust text cleaning and normalization |
| UI/UX Layout | Streamlit’s limited layout control | Utilized columns, expanders, and custom CSS for structure |

---
## 📸 Screenshots
### Login Page
<img width="1917" height="912" alt="Screenshot 2025-11-27 161518" src="https://github.com/user-attachments/assets/498ff27c-73e6-4353-b00d-f4a261c4c408" />

### User Page
<img width="1914" height="909" alt="Screenshot 2025-11-27 161741" src="https://github.com/user-attachments/assets/78648f12-f38d-43cd-8272-8ae9f9cf0285" />

### Admin Page
<img width="1918" height="908" alt="Screenshot 2025-11-27 162730" src="https://github.com/user-attachments/assets/5b37f9b9-faec-46dd-b5a7-26bb4fec7c59" />

---
## 👥 Team

| Name | Contribution | GitHub |
|------|--------------|--------|
| Lithicka G | Login part, Authentication, Admin dashboard (Global activity), History in User Login| https://github.com/Lithicka-G |
| Vijendra Cherupally | User Login (Data Augmentation and Model Testing part), Docker, Readme | https://github.com/vijayendracherupally |
| Immadisetti Tejo Thoshani | User Login (Paraphrasing), User Profile | https://github.com/Thoshani |
| Jaagruthi Musinada | User Login( Summarization), User Feedback and PPT | https://github.com/Jaagruthi-Musinada |
| Aakanksha Sainath Jadhav | Admin Dashboard ( User Management, Analytics and Insights) | https://github.com/aakankshajadhav412-alt |

---
## 📜 License
This project is open source and freely available under the MIT License, allowing anyone to use, modify, distribute, and share the software for any purpose, with proper attribution to the original authors.
