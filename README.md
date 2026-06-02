# 🚀 ATS Multi-Cloud AI Platform

> AI-Powered Applicant Tracking System (ATS) deployed on AWS and integrated with Google Gemini AI for intelligent resume analysis, keyword extraction, skill matching, and candidate evaluation.

## Badges

```markdown
![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazonaws)
![Google Cloud](https://img.shields.io/badge/Google_Cloud-Gemini_AI-blue?style=for-the-badge&logo=googlecloud)
![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-Web_App-red?style=for-the-badge&logo=streamlit)
![AI](https://img.shields.io/badge/Generative_AI-Gemini-success?style=for-the-badge)
![MultiCloud](https://img.shields.io/badge/Multi_Cloud-AWS+GCP-purple?style=for-the-badge)
```

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

```markdown
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

```markdown
![Request Flow](architecture/request-flow.png)
```

## ⚙️ ATS Workflow

```markdown
![Workflow](architecture/ats-workflow.png)
```

## 📸 Application Screenshots

Add screenshots from the screenshots folder.

## 📋 Prerequisites

- AWS Account
- Google Cloud Account
- Gemini API Enabled
- Ubuntu EC2 Instance
- Python 3.x

## 🚀 Deployment Guide

### Step 1 – Launch EC2

```bash
sudo -i
```

### Step 2 – Install Dependencies

```bash
apt update
apt install python3-pip python3-venv git -y
```

### Step 3 – Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/ATS-Multi-Cloud-AI-Platform.git
cd ATS-Multi-Cloud-AI-Platform/app
```

### Step 4 – Create Virtual Environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### Step 5 – Install Packages

```bash
pip install -r requirements.txt
```

### Step 6 – Configure Gemini API

```bash
mkdir -p .streamlit
vi .streamlit/secrets.toml
```

```toml
GOOGLE_API_KEY = "YOUR_API_KEY"
```

### Step 7 – Start Application

```bash
streamlit run app.py --server.port 8501 --server.address 0.0.0.0
```

### Step 8 – Open Security Group

Port 8501 (Custom TCP)

### Step 9 – Access Application

```text
http://PUBLIC_IP:8501
```

## 🔐 Security Considerations

- Never commit API keys
- Restrict Security Groups
- Use least privilege access

## ⚡ Challenges & Learnings

- Cross-Cloud Integration
- API Authentication
- PDF Parsing
- Networking

## 🚀 Future Enhancements

- Docker
- Kubernetes
- Terraform
- CI/CD
- Prometheus
- Grafana

## 👨‍💻 Author

Anirban Dalui
