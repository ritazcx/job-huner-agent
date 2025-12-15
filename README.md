# Job Hunter Agent 🤖

An autonomous AI agent that **automatically discovers, evaluates, and ranks job opportunities** based on your resume — so you only apply to roles that truly match your background.

> Stop scrolling LinkedIn. Let an agent do the hunting.

---

## ✨ What This Agent Does

Every day at a scheduled time, the agent:

1. Loads your **latest resume** from a local folder
2. Searches for **new job postings from the last 24 hours**
3. Parses job descriptions into structured requirements
4. Matches each job against your resume using **LLMs + rule-based logic**
5. Scores and ranks jobs with **explainable criteria**
6. Sends you a **daily digest of the top-matching roles**

---

## 🧠 Core Features

* 📄 **Local Resume Parsing** (PDF → structured JSON, with caching)
* 🔍 **Multi-source Job Search**

  * Google Jobs
  * LinkedIn job alert emails
  * Twitter / X hiring posts
* 📑 **Hybrid JD Parser**

  * Rule-based extraction
  * LLM semantic understanding
* 🧠 **CV ↔ JD Matching Engine**

  * Skill overlap
  * Project similarity
  * Language & location constraints
* 📊 **Explainable Scoring System**
* 📬 **Daily Notifications**

  * Email (default)
  * Notion / Slack (optional)

---

## 🏗️ Architecture Overview

```text
Scheduler
   ↓
Resume Loader (Local)
   ↓
Job Aggregation
   ↓
JD Parser
   ↓
CV ↔ JD Matching Engine
   ↓
Scoring & Ranking
   ↓
Daily Notification
```

---

## 📁 Project Structure

```text
src/
├── resume_loader.py     # Load & parse resume
├── job_search/          # Job source integrations
├── jd_parser.py         # JD → structured requirements
├── matcher.py           # CV ↔ JD semantic matching
├── scorer.py            # Scoring & ranking logic
├── notifier/            # Email / Notion push
└── main.py              # Pipeline entry point
```

---

## ⚙️ Tech Stack

* Python
* LLM APIs (OpenAI / Claude, pluggable)
* PDF parsing (`pdfplumber`)
* Embeddings for semantic similarity
* Cron / launchd / GitHub Actions

---

## 🚀 Roadmap

* [ ] Resume parser
* [ ] Job aggregation
* [ ] JD parser
* [ ] Matching & scoring
* [ ] Daily email digest
* [ ] Automatic cover letter generation
* [ ] Resume bullet optimization

---

## 📌 Disclaimer

This project is for **personal and educational use**.
No aggressive scraping is performed.

---

## 🧑‍💻 Author

Built by a job seeker who got tired of fighting LinkedIn’s algorithm.
