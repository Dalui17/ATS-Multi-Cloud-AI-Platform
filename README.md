# 🚀 ATS Multi-Cloud AI Platform

> AI-Powered Applicant Tracking System (ATS) deployed on AWS and integrated with Google Gemini AI for intelligent resume analysis, keyword extraction, skill matching, and candidate evaluation.

<p align="center">

<img src="https://img.shields.io/badge/AWS-EC2-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white">

<img src="https://img.shields.io/badge/Google_Cloud-Gemini_AI-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white">

<img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white">

<img src="https://img.shields.io/badge/Streamlit-App-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white">

<img src="https://img.shields.io/badge/Multi_Cloud-AWS+GCP-8A2BE2?style=for-the-badge">

</p>




## 💼 Business Problem

Recruiters and hiring managers often spend significant time manually reviewing resumes and comparing candidate profiles against job descriptions.

## 🎯 Solution

- Extracts text from uploaded resumes
- Analyzes job descriptions
- Matches skills against requirements
- Identifies missing keywords
- Generates candidate evaluations
- Calculates match percentage

## ☁️ Multi-Cloud Architecture

``
![Architecture](architecture/multicloud-architecture.png)
```

## 🏗 Architecture Overview

AWS Responsibilities:
- EC2 Compute
- Streamlit Hosting
- Resume Processing

Google Cloud Responsibilities:
- Gemini AI Processing
- Resume Evaluation
- Skill Extraction

## 🛠 Technology Stack

| Layer | Technology |
|---------|---------|
| Cloud | AWS |
| AI | Google Gemini |
| Compute | EC2 |
| Language | Python |
| Framework | Streamlit |
| PDF Processing | PyPDF |

## 📂 Repository Structure

```text
ATS-Multi-Cloud-AI-Platform/
├── app/
├── architecture/
├── screenshots/
├── docs/
└── README.md
```

## 🔄 Request Flow

![Request Flow](architecture/request-flow.png)

## ⚙️ ATS Workflow

![Workflow](architecture/ats-workflow.png)
```



## 📋 Prerequisites

- AWS Account
- Google Cloud Account
- Gemini API Enabled
- Ubuntu EC2 Instance
- Python 3.x

## 🚀 Deployment Guide

### Step 1 – Launch EC2

```
sudo -i
```

### Step 2 – Install Dependencies

```
apt update
apt install python3-pip python3-venv git -y
```

### Step 3 – Clone Repository

```
git clone https://github.com/YOUR_USERNAME/ATS-Multi-Cloud-AI-Platform.git
cd ATS-Multi-Cloud-AI-Platform/app
```

### Step 4 – Create Virtual Environment

```
python3 -m venv .venv
source .venv/bin/activate
```

### Step 5 – Install Packages

```
pip install -r requirements.txt
```

### Step 6 – Configure Gemini API

```
mkdir -p .streamlit
vi .streamlit/secrets.toml
```

```
GOOGLE_API_KEY = "YOUR_API_KEY"
```

### Step 7 – Start Application

```
streamlit run app.py --server.port 8501 --server.address 0.0.0.0
```

### Step 8 – Open Security Group

Port 8501 (Custom TCP)

### Step 9 – Access Application

```
http://PUBLIC_IP:8501
```

---
## 📸 Application Screenshots

<h2>📸 Application Screenshots</h2>

<h3>🔹 ATS Homepage</h3>

<p align="center">
  <img src="screenshots/05-ats-homepage.png" width="100%">
</p>

<h3>🔹 AI Candidate Evaluation</h3>

<p align="center">
  <img src="screenshots/06-final-result.png" width="100%">
</p>
----

## 🔐 Security Considerations

- Never commit API keys
- Restrict Security Groups
- Use least privilege access

## ⚡ Challenges & Learnings

- Cross-Cloud Integration
- API Authentication
- PDF Parsing
- Networking


## 👨‍💻 Author

Anirban Dalui

---

## ⭐ Support

If you like this project, give it a ⭐ on GitHub
