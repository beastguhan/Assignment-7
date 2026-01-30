# Assignment-7
# 🚨 Simulated Production Incident & Root Cause Analysis (RCA)

This project simulates a **production-like incident** in a containerized application and demonstrates a structured **incident investigation and Root Cause Analysis (RCA)** process.

The goal is to replicate how DevOps / SRE engineers debug real incidents using logs, reproduction steps, and systematic analysis.

---

## 🎯 Objective

- Simulate an unstable production application
- Reproduce an intermittent failure
- Capture and analyze logs
- Identify the root cause
- Propose preventive and corrective actions
- Document the findings in an RCA report

---

## 🛠 Tech Stack

- Python (Flask)
- Docker
- Docker Compose
- Linux shell utilities

---

---

## 🐍 Application Overview

The application is a **deliberately buggy Flask app** that:
- Randomly throws unhandled exceptions
- Returns HTTP 500 errors intermittently
- Mimics real-world production instability

This behavior simulates issues such as:
- Unhandled exceptions
- Poor error handling
- Random application crashes

---

## 🚀 Running the Application

Start the application:
```bash
docker compose up -d

docker compose ps
Application URL:

http://localhost:5000

Incident Reproduction

Send repeated requests:

for i in {1..20}; do curl -s -o /dev/null -w "%{http_code}\n" http://localhost:5000; done

📊 Log Collection

Capture logs from the container:

docker compose logs buggy-app
🧠 Root Cause Analysis
Summary

The application failed intermittently due to unhandled exceptions triggered by random logic in the request handler.

Root Cause

Intentional random failure logic

No exception handling

No graceful fallback or retry mechanism

Impact

Unreliable service behavior

Failed user requests

Poor system resilience

🛠 Proposed Fix (Conceptual)

Add exception handling

Remove non-deterministic failure logic

Implement graceful error responses

Add monitoring and alerting

Improve test coverage

Example concept:

try:
    risky_operation()
except Exception:
    return "Temporary error, please retry", 503
