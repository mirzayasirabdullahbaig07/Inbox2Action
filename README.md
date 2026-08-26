# ⚡ Inbox2Action: Enterprise Taskmaster Agent

[![Deployed on Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://inbox2action.streamlit.app/)
[![Powered by Google GenAI](https://img.shields.io/badge/Google%20GenAI-SDK-blue?logo=googlecloud)](https://cloud.google.com/)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Hackathon](https://img.shields.io/badge/All%20Things%20Agentic-Hackathon%202026-orange)](#)

> **Submission for the All Things Agentic Hackathon — Taskmaster Track**  
> **Live App URL:** [inbox2action.streamlit.app](https://inbox2action.streamlit.app/)

---

## 📌 Table of Contents
- [Overview](#-overview)
- [Problem & Solution](#-problem--solution)
- [The Team](#-the-team)
- [System Architecture](#-system-architecture)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [Local Setup & Spin-Up Instructions](#-local-setup--spin-up-instructions)
- [Google Cloud Deployment (Cloud Run)](#-google-cloud-deployment-cloud-run)
- [Project Directory Structure](#-project-directory-structure)
- [License & Acknowledgments](#-license--acknowledgments)

---

## 📌 Overview

**Inbox2Action** is an autonomous, next-generation Taskmaster Agent operating inside an enterprise command center. Designed for the **Taskmaster Track** of the **All Things Agentic Hackathon**, it eliminates administrative friction by ingesting raw, unstructured inbound communications (customer emails, invoice receipts, critical bug reports), extracting actionable parameters, formulating step-by-step resolution plans, and generating ready-to-send responses in seconds.

---

## 💡 Problem & Solution

### The Problem
Modern enterprise teams are inundated with unstructured operational noise: support requests, bug reports, invoice approvals, and client sync requests. Manually parsing these messages, identifying priorities, determining next steps, and drafting responses creates massive administrative lag and human bottlenecking.

### The Solution
Instead of requiring continuous step-by-step human prompts like static chatbots, **Inbox2Action** acts autonomously:
1. **Parses** raw input to extract entities (priority, category, action items, target deadlines).
2. **Formulates** an end-to-end execution plan without human intervention.
3. **Drafts** context-aware, professional communications ready for immediate dispatch.
4. **Displays** real-time execution telemetry and throughput analytics via interactive dashboards.

---

## 👥 The Team

* 👑 **Mirza Yasir Abdullah Baig** — *Team Leader* (`@mirzayasirabdullahbaig`)
* 🤖 **Hamna Munir** — *AI Engineer* (`@hamnamunir27`)
* 🗄️ **Lipon Islam** — *Data Engineer* (`@liponislam752`)
* ☁️ **Dhairya Sindhwani** — *Google Cloud Expert* (`@dhairya-sindhwani`)
* 📊 **Utkarsh Raj** — *Data Scientist* (`@utkarshraj1306`)
* ⚙️ **Sibabalwe Gagadu** — *MLOps Engineer* (`@sibabalodeyi`)

---

## 🏗️ System Architecture

             ┌────────────────────────────────────────────────────────┐
             │                 INBOUND TASK PAYLOAD                   │
             │   (Raw Email / Bug Report / Unstructured Text)         │
             └───────────────────────────┬────────────────────────────┘
                                         │
                                         ▼
             ┌────────────────────────────────────────────────────────┐
             │              STREAMLIT COMMAND CENTER                  │
             │        (User Interface & Ingestion Portal)             │
             └───────────────────────────┬────────────────────────────┘
                                         │
                                         ▼
             ┌────────────────────────────────────────────────────────┐
             │             GOOGLE GENAI SDK INTERFACE                 │
             │          (Authentication & Payload Transport)          │
             └───────────────────────────┬────────────────────────────┘
                                         │
                                         ▼
             ┌────────────────────────────────────────────────────────┐
             │                GEMINI 2.5 FLASH MODEL                  │
             │  • Context Extraction    • System Policy Evaluation    │
             │  • Action Plan Generation• Response Drafting           │
             └───────────────────────────┬────────────────────────────┘
                                         │
                                         ▼
             ┌────────────────────────────────────────────────────────┐
             │              EXECUTION & TELEMETRY ENGINE              │
             │  • Priority Parsing    • Plotly Analytics Dashboard    │
             │  • Draft Email         • Google Cloud Telemetry Trace │
             └───────────────────────────┬────────────────────────────┘
                                         │
                                         ▼
             ┌────────────────────────────────────────────────────────┐
             │            GOOGLE CLOUD RUN CONTAINER HOST             │
             │  (Fully Containerized Docker Deployment on Google Cloud)│
             └────────────────────────────────────────────────────────┘

---

## ✨ Key Features

1. **Autonomous Entity Parsing:** Leverages `gemini-2.5-flash` to extract critical task metadata (Priority, Category, Deadlines, Action Items) automatically.
2. **Interactive Enterprise Command Center:** A wide-layout UI providing top-level operational metrics, hourly ingestion bars, and real-time radar telemetry traces.
3. **Automated Communications:** Crafts precise, professional draft replies formatted in clean Markdown.
4. **Environment Security:** Loads API keys dynamically via `.env` with fallbacks for seamless setup.
5. **Cloud-Ready Containerization:** Includes a lightweight `Dockerfile` configured for Google Cloud Run deployment.

---

## 🛠️ Tech Stack

* **Core AI Engine:** Google GenAI SDK (`google-genai`), Gemini 2.5 Flash (`gemini-2.5-flash`)
* **Frontend & Dashboard:** Streamlit
* **Analytics & Visualization:** Plotly Express, Plotly Graph Objects, Pandas
* **Environment Management:** `python-dotenv`
* **Containerization & Deployment:** Docker, Google Cloud Run, Streamlit Community Cloud

---
