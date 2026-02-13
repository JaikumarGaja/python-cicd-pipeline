# 🛡️ Secure Python CI/CD Pipeline

![Build Status](https://github.com/JaikumarGaja/python-cicd-actions/actions/workflows/main.yml/badge.svg)

A robust "DevSecOps" pipeline that automatically validates Python code quality, security, and functionality on every commit.

## 📖 About the Project
This repository demonstrates a **Shift-Left Security** approach. Instead of finding bugs in production, this automated pipeline catches issues *before* they are merged. It uses **GitHub Actions** to act as a quality gatekeeper.

## ⚙️ The Pipeline Architecture
Every time code is pushed to the `main` branch, a Linux runner executes these 4 stages:

1.  **Environment Setup:** Provisions an Ubuntu container with Python 3.9.
2.  **Linting (Flake8):** Enforces PEP8 coding standards to ensure clean, readable code.
3.  **Security Scanning (Bandit):** Performs Static Application Security Testing (SAST) to detect vulnerabilities (e.g., hardcoded secrets, unsafe asserts).
    * *Configuration:* configured to exclude test files to prevent false positives.
4.  **Unit Testing (Pytest):** Runs the test suite to verify application logic.

## 🛠️ Tools Used
* **CI/CD:** GitHub Actions
* **Language:** Python 3.9
* **Linter:** `flake8`
* **Security Scanner:** `bandit`
* **Testing Framework:** `pytest`

## 🚀 How to trigger the Pipeline
1.  Clone the repo.
2.  Make a change to `app.py`.
3.  Push the code:
    ```bash
    git add .
    git commit -m "feat: updated app logic"
    git push origin main
    ```
4.  Go to the **Actions** tab in GitHub to watch the robots work!
