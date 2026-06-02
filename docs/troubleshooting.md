# Troubleshooting Guide

This document provides solutions for common issues encountered while deploying and running the ATS Multi-Cloud AI Platform on AWS EC2 with Google Gemini API integration.

---

# 1. Unable to Access Streamlit Application

## Issue

The application starts successfully, but the browser displays:

```text
This site can't be reached
Connection Refused
ERR_CONNECTION_TIMED_OUT
```

## Root Cause

* Port 8501 is blocked in the EC2 Security Group.
* Streamlit is listening on localhost (127.0.0.1) instead of all network interfaces.

## Solution

Start Streamlit using:

```bash
streamlit run app.py --server.port 8501 --server.address 0.0.0.0
```

Verify Security Group:

```text
Type: Custom TCP
Port: 8501
Source: My IP or 0.0.0.0/0 (Lab Environment Only)
```

Verify process:

```bash
netstat -tulpn | grep 8501
```

---

# 2. Invalid Gemini API Key

## Issue

Application fails during AI analysis.

Error:

```text
API_KEY_INVALID
PermissionDenied
```

## Root Cause

* Invalid API key.
* Gemini API not enabled.
* Incorrect configuration in secrets file.

## Solution

Enable Gemini API:

```text
Google Cloud Console
→ APIs & Services
→ Library
→ Gemini API
→ Enable
```

Update Streamlit secrets:

```toml
GOOGLE_API_KEY = "YOUR_API_KEY"
```

Restart application:

```bash
pkill streamlit
streamlit run app.py
```

---

# 3. API Quota Exceeded

## Issue

Resume analysis fails intermittently.

Error:

```text
429 Resource Exhausted
```

## Root Cause

Gemini API quota has been exceeded.

## Solution

* Reduce request frequency.
* Implement retry logic.
* Upgrade API quota.

Example retry implementation:

```python
from tenacity import retry, wait_fixed

@retry(wait=wait_fixed(5))
def analyze_resume():
    pass
```

---

# 4. PDF Upload Fails

## Issue

Resume cannot be processed.

Error:

```text
Unable to read PDF
```

## Root Cause

* Corrupted PDF.
* Scanned image-based PDF.
* Unsupported format.

## Solution

* Upload text-based PDF files.
* Validate file before processing.
* Add OCR support for scanned resumes.

Recommended file size:

```text
Less than 10 MB
```

---

# 5. ModuleNotFoundError

## Issue

Application fails during startup.

Error:

```text
ModuleNotFoundError
```

## Root Cause

Required Python packages are missing.

## Solution

Activate virtual environment:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Verify packages:

```bash
pip list
```

---

# 6. Streamlit Stops After SSH Disconnect

## Issue

Application becomes unavailable after closing terminal.

## Root Cause

Streamlit process is attached to the current SSH session.

## Solution

Run application in background:

```bash
nohup streamlit run app.py &
```

Alternative:

```bash
tmux
```

or

```bash
screen
```

---

# 7. Out Of Memory (OOM) Error

## Issue

Application crashes while processing large resumes.

Error:

```text
Killed
```

or

```text
OOMKilled
```

## Root Cause

Large PDF files consume excessive memory.

## Solution

* Increase EC2 instance size.
* Limit upload size.
* Process PDFs page-by-page.

Example validation:

```python
if uploaded_file.size > 10 * 1024 * 1024:
    st.error("File exceeds size limit")
```

---

# 8. Git Push Rejected

## Issue

Unable to push code to GitHub.

Error:

```text
Updates were rejected because the remote contains work that you do not have locally.
```

## Solution

Pull latest changes:

```bash
git pull origin main --rebase
```

Push again:

```bash
git push origin main
```

---

# 9. Exposed API Keys in Repository

## Issue

Sensitive credentials accidentally committed to GitHub.

## Solution

Never commit:

```text
.streamlit/secrets.toml
.env
credentials.json
```

Update .gitignore:

```gitignore
.streamlit/
.env
```

Rotate compromised API keys immediately.

---

# 10. Security Best Practices

## Recommended

### AWS

* Restrict Security Groups.
* Use IAM least-privilege permissions.
* Enable CloudTrail auditing.

### Google Cloud

* Restrict API key usage.
* Enable API quotas.
* Monitor API consumption.

### Application

* Validate uploaded files.
* Sanitize user inputs.
* Store secrets securely.

Preferred production approach:

```text
AWS Secrets Manager
```

instead of storing credentials in local files.

---

# Quick Health Check Commands

Check running process:

```bash
ps -ef | grep streamlit
```

Check listening ports:

```bash
ss -tulpn
```

Check memory usage:

```bash
free -h
```

Check disk usage:

```bash
df -h
```

Check application logs:

```bash
tail -f nohup.out
```

---

# Conclusion

Most deployment issues are related to:

* Security Group configuration
* Streamlit network binding
* Gemini API authentication
* Dependency installation
* Resource limitations

Following the troubleshooting steps above should resolve the majority of deployment and runtime issues encountered during project setup.
