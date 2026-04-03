# Implementation Plan — Meeting Notes Organizer

## Product Overview

**Product name:** Meeting Notes Organizer

**One-sentence idea:**  
A web app that turns raw meeting notes into structured summaries, decisions, and action items.

**End users:**  
Students, small teams, and professionals.

**Problem:**  
Unstructured meeting notes lead to missed decisions and forgotten tasks.

---

## Required Product Components

- **Backend:** processes input, calls LLM (Qwen), stores results  
- **Database:** stores notes and generated outputs  
- **Frontend:** web interface for input and viewing results  

---

## LLM Strategy (Free)

Instead of paid APIs, the project will use:

- **Qwen (open-source LLM)** via:
  - local inference (Ollama or similar), OR
  - free API endpoint (if available)

### Why Qwen:
- free
- no API cost
- good enough for summarization
- easy to integrate

---

## Version 1 Plan

### Goal
Build a working summarization pipeline.

### Core Feature
Input → Qwen → structured output

### Version 1 Scope

#### Frontend
- Text input (textarea)
- Submit button
- Output display:
  - summary
  - decisions
  - action items

#### Backend
- POST endpoint `/summarize`
- Send prompt to Qwen
- Parse structured response (prefer JSON)
- Return to frontend

#### Database
Table: `summaries`
- id
- input_text
- summary
- decisions
- action_items
- created_at

### Version 1 Deliverable
Working web app:
- user inputs text
- receives structured output
- result stored in DB

---

## Version 2 Plan

### Goal
Improve usability + deploy

### Improvements
- history of summaries
- view past results
- better formatting
- error handling

### Optional
- export to Markdown / PDF
- search

### Deployment
- Dockerize frontend + backend + DB
- Run on VM
- Ensure accessibility via browser

---

## Suggested Tech Stack

Frontend:
- React + Vite

Backend:
- FastAPI

Database:
- PostgreSQL

LLM:
- Qwen (via Ollama or API)

Infra:
- Docker + Docker Compose

---

## High-Level Steps

1. Setup project structure  
2. Setup PostgreSQL  
3. Implement backend API  
4. Integrate Qwen (local or API)  
5. Build frontend UI  
6. Connect frontend to backend  
7. Store results in DB  
8. Test Version 1  
9. Add history (Version 2)  
10. Dockerize  
11. Deploy on VM  

---

## Risks

### 1. LLM output inconsistency
Solution:
- enforce JSON output in prompt
- validate response

### 2. Local model performance
Solution:
- limit input size
- test with small texts

### 3. Integration complexity
Solution:
- start with mock responses
- then plug Qwen

---

## Version Summary

### Version 1
Basic summarization pipeline using Qwen

### Version 2
Improved UX + deployed product
