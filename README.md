# Job Hunter Agent (n8n-powered) 🤖

An autonomous **AI job hunting agent built with n8n**, designed to automatically discover, evaluate, and rank job opportunities based on your resume.

> Let automation and LLMs fight LinkedIn’s algorithm for you.

---

## ✨ What This Agent Does

Every day at a scheduled time, this agent:

1. Loads your **latest resume from a local folder**
2. Collects **new job postings from the last 24 hours**
3. Parses job descriptions into structured requirements
4. Matches each role against your resume using **LLMs + rule-based logic**
5. Scores and ranks jobs with **explainable criteria**
6. Sends a **daily digest of the most relevant jobs**

All orchestration is handled by **n8n workflows**.

---

## 🧠 Why n8n?

* Visual, debuggable AI workflows
* Native scheduling (Cron)
* Easy API & LLM integration
* Ideal for autonomous agents
* Perfect for rapid iteration and demos

This project focuses on **agent behavior**, not glue code.

---

## 🏗️ Architecture Overview

```text
Cron Trigger (n8n)
   ↓
Resume Loader (Local File)
   ↓
Job Aggregation (Google / Email / X)
   ↓
JD Parsing (LLM)
   ↓
CV ↔ JD Matching (LLM + Rules)
   ↓
Scoring & Ranking
   ↓
Email / Notion / Slack Notification
```

---

## 📁 Project Structure

```text
workflows/   # n8n workflow JSON files
prompts/     # LLM prompt templates
config/      # Scoring rules & filters
data/        # Resume & job cache
docs/        # Setup & architecture notes
```

---

## 🚀 Roadmap

* [ ] Resume ingestion & caching
* [ ] Job aggregation workflows
* [ ] JD parsing prompt
* [ ] CV ↔ JD matching logic
* [ ] Explainable scoring
* [ ] Daily email digest
* [ ] Auto cover letter generation

---

## 📌 Disclaimer

This project is for **personal and educational use only**.
No aggressive scraping is performed.

---

## 🧑‍💻 Author

Built by someone who decided AI agents should apply to jobs instead of humans.
