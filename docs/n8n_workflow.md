# n8n Workflow Design – Job Hunter Agent

This document describes the node-level design of the **Job Hunter Agent**, implemented as an n8n workflow running in Docker.

---

## 🧠 Workflow Overview

```text
Cron Trigger
   ↓
Read Resume (Local PDF)
   ↓
Extract Resume Text
   ↓
Resume → Structured JSON (LLM)
   ↓
Job Source (Google Jobs / API)
   ↓
Split Jobs
   ↓
JD Parser (LLM)
   ↓
CV ↔ JD Matcher (LLM)
   ↓
Scoring Function
   ↓
Sort & Top N
   ↓
Daily Email Digest
```

---

## 📦 Node Details

### 1. Cron Trigger

* Runs daily at 07:00
* Initiates the agent workflow

### 2. Read Binary File

* Reads resume from `/data/resume/CV_latest.pdf`
* Mounted via Docker volume

### 3. PDF Extract

* Extracts raw text from resume PDF

### 4. Resume Parser (LLM)

* Converts resume text into structured JSON
* Cached for reuse

### 5. Job Source

* Fetches job postings from the last 24 hours
* Uses API-based sources (no scraping)

### 6. Split In Batches

* Processes jobs one by one

### 7. JD Parser (LLM)

* Extracts structured requirements from job descriptions

### 8. CV ↔ JD Matcher

* Computes semantic similarity
* Produces explainable matching results

### 9. Scoring Function

* Weighted scoring based on:

  * Skill match
  * Experience match
  * Language constraints

### 10. Notification

* Sends daily digest via Email / Notion / Slack

---

## 🐳 Docker Notes

Ensure the following volume mapping exists:

```yaml
volumes:
  - ./data:/data
```

This allows n8n to access local resume and cache files.

---

## 🎯 Goal

This workflow is designed to:

* Minimize human job search effort
* Maximize application relevance
* Provide transparent, explainable job recommendations
