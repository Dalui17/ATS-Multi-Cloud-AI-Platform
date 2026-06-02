<h1 align="center">🚀 ATS Multi-Cloud AI Platform</h1>

<p align="center">
AI-Powered Applicant Tracking System (ATS) deployed on AWS and integrated with Google Gemini AI for intelligent resume analysis, skill matching, keyword extraction, and candidate evaluation.
</p>

<p align="center">
<img src="https://img.shields.io/badge/AWS-EC2-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white">
<img src="https://img.shields.io/badge/Google%20Cloud-Gemini%20AI-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white">
<img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/Streamlit-App-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white">
<img src="https://img.shields.io/badge/Multi--Cloud-AWS%20%2B%20GCP-8A2BE2?style=for-the-badge">
</p>

---

## 🌟 Project Highlights

✅ Multi-Cloud Integration (AWS + Google Cloud)

✅ AI-Powered Resume Analysis using Google Gemini

✅ Intelligent Skill Matching & Candidate Evaluation

✅ Automated Keyword Extraction

✅ Real-Time Resume Processing

✅ AWS EC2 Deployment

✅ Recruiter-Friendly Assessment Report

✅ End-to-End Cloud-Based AI Solution

---

## 🎯 Business Problem

Recruiters and hiring managers often spend hours manually screening resumes against job descriptions.

Common challenges:

- Manual candidate evaluation
- Time-consuming resume screening
- Missing qualified candidates
- Skill gap identification
- Inconsistent assessment process

---

## 💡 Solution

The ATS Multi-Cloud AI Platform automates the recruitment screening process using Generative AI.

The application:

- Uploads candidate resumes (PDF)
- Extracts resume content
- Analyzes job descriptions
- Identifies relevant skills
- Calculates job match percentage
- Detects missing skills
- Generates AI-powered recommendations
- Produces recruiter-ready evaluations

---

## ☁️ Multi-Cloud Architecture

<p align="center">
  <img src="architecture/multicloud-architecture.png" width="100%">
</p>

### Architecture Overview

| Component | Purpose |
|------------|------------|
| AWS EC2 | Hosts ATS Application |
| Streamlit | User Interface |
| PyPDF | Resume Text Extraction |
| Google Gemini API | AI Evaluation Engine |
| Google Cloud | AI Processing Layer |
| Recruiter Dashboard | Candidate Assessment Results |

### Cloud Responsibilities

#### AWS

- Application Hosting
- Resume Processing
- User Interaction
- Runtime Environment

#### Google Cloud

- Generative AI Processing
- Candidate Evaluation
- Skill Extraction
- Match Percentage Analysis

---

## 🔄 Request Flow

<p align="center">
  <img src="architecture/request-flow.png" width="100%">
</p>

---

## ⚙️ ATS Workflow

<p align="center">
  <img src="architecture/ats-workflow.png" width="100%">
</p>

---

## 🛠 Technology Stack

| Category | Technology |
|-----------|-----------|
| ☁️ Cloud Platform | AWS EC2 |
| 🤖 AI Engine | Google Gemini |
| 🐍 Programming Language | Python |
| 🎨 Frontend | Streamlit |
| 📄 Resume Processing | PyPDF |
| 🔐 Authentication | API Key |
| 🌐 Version Control | Git & GitHub |
| 💻 Operating System | Ubuntu Linux |

---

## 📂 Repository Structure

```text
ATS-Multi-Cloud-AI-Platform/
│
├── app/
│   ├── app.py
│   ├── index.html
│   ├── requirements.txt
│   └── packages.txt
│
├── architecture/
│   ├── multicloud-architecture.png
│   ├── request-flow.png
│   └── ats-workflow.png
│
├── screenshots/
│   ├── 02-gemini-api-enabled.png
│   ├── 03-api-key-created.png
│   ├── 04-streamlit-running.png
│   ├── 05-ats-homepage.png
│   └── 06-final-result.png
│
├── docs/
│   └── troubleshooting.md
│
└── README.md
```

---

## 📸 Application Screenshots

### 🔹 Google Gemini API Enabled

<p align="center">
  <img src="screenshots/02-gemini-api-enabled.png" width="90%">
</p>

### 🔹 Gemini API Key Configuration

<p align="center">
  <img src="screenshots/03-api-key-created.png" width="90%">
</p>

### 🔹 Streamlit Application Startup

<p align="center">
  <img src="screenshots/04-streamlit-running.png" width="90%">
</p>

### 🔹 ATS Homepage

<p align="center">
  <img src="screenshots/05-ats-homepage.png" width="90%">
</p>

### 🔹 AI Candidate Evaluation

<p align="center">
  <img src="screenshots/06-final-result.png" width="90%">
</p>

---

## 📋 Prerequisites

- AWS Account
- Google Cloud Account
- Gemini API Enabled
- Ubuntu EC2 Instance
- Python 3.x
- Git

---

## 🚀 Deployment Guide

### Step 1 — Connect to EC2

```bash
sudo -i
```

### Step 2 — Install Dependencies

```bash
apt update
apt install python3-pip python3-venv git -y
```

### Step 3 — Clone Repository

```bash
git clone https://github.com/Dalui17/ATS-Multi-Cloud-AI-Platform.git

cd ATS-Multi-Cloud-AI-Platform/app
```

### Step 4 — Create Virtual Environment

```bash
python3 -m venv .venv

source .venv/bin/activate
```

### Step 5 — Install Required Packages

```bash
pip install -r requirements.txt
```

### Step 6 — Configure Gemini API

```bash
mkdir -p .streamlit

vi .streamlit/secrets.toml
```

Add:

```toml
GOOGLE_API_KEY="YOUR_API_KEY"
```

### Step 7 — Run Application

```bash
streamlit run app.py --server.port 8501 --server.address 0.0.0.0
```

### Step 8 — Configure Security Group

Allow:

```text
Custom TCP
Port: 8501
Source: My IP
```

### Step 9 — Access Application

```text
http://PUBLIC_IP:8501
```

---

## 🔐 Security Considerations

- Never commit API keys
- Restrict Security Group access
- Rotate compromised credentials
- Use environment variables where possible
- Apply least-privilege principles

---

## ⚡ Challenges & Learnings

### Multi-Cloud Integration

Established secure communication between AWS-hosted applications and Google Gemini AI services.

### Resume Parsing

Handled different PDF formats and extraction scenarios.

### AI Prompt Engineering

Designed prompts to generate consistent candidate evaluations and recommendations.

### Cloud Networking

Configured Security Groups, ports, and public access securely.

### Production Deployment

Managed deployment and runtime configuration on AWS EC2.

---

## 🚀 Future Enhancements

- Docker Containerization
- Kubernetes Deployment
- Terraform Infrastructure as Code
- GitHub Actions CI/CD
- AWS Secrets Manager
- Prometheus Monitoring
- Grafana Dashboards
- Recruiter Analytics Dashboard

---

## 👨‍💻 Author

**Anirban Dalui**

Cloud & DevOps Engineer

AWS Certified Solutions Architect Associate

Azure DevOps Engineer Expert

---

## ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.
