# Implementation Plan — Meeting Notes Organizer

## Product Overview

**Product name:** Meeting Notes Organizer

**One-sentence idea:**  
A web app that turns raw meeting notes into structured summaries, decisions, and action items.

**End users:**  
Students, small teams, and professionals who need to quickly summarize meeting notes and extract actionable tasks.

**Problem:**  
People often take messy, unstructured meeting notes that are hard to review later, which leads to missed decisions and forgotten action items.

---

## Required Product Components

The product will include all required components, each with a useful function:

- **Backend:** receives meeting notes, calls the LLM API, processes and stores results.
- **Database:** stores the original input and generated structured output.
- **End-user-facing client:** a web application where users can submit notes and view results.

---

## Version 1 Plan

### Goal
Build one core feature well: converting raw meeting notes into a structured result.

### Core Feature
The user pastes meeting notes into a web form, and the system generates:

- a short summary,
- key decisions,
- action items.

### Why this is the best Version 1 feature
This is the most valuable user-facing feature and also the simplest one to implement reliably. It creates a functioning product, not just a prototype.

### Version 1 Scope

#### Frontend
- Single-page web interface
- Text area for pasting meeting notes
- Submit button
- Display section for:
  - summary
  - decisions
  - action items

#### Backend
- API endpoint to accept raw notes
- Call LLM API with a structured prompt
- Parse response into a stable format
- Return processed result to frontend

#### Database
Store:
- original meeting notes
- generated summary
- generated decisions
- generated action items
- creation timestamp

### Version 1 Deliverable
A working web app that allows a user to paste meeting notes, generate structured output, and save the result in the database.

### Version 1 Review with TA
After completion, Version 1 should be shown to the TA for feedback. Feedback points should be recorded and used in Version 2.

---

## Version 2 Plan

### Goal
Extend and polish Version 1, address TA feedback, and deploy the product.

### Planned Improvements
Version 2 will build on the core functionality by adding useful features around the generated output.

### Version 2 Scope

#### Functional Improvements
- View history of previously generated meeting summaries
- Open and review past results
- Improve the formatting and consistency of generated output
- Improve error handling and validation

#### Optional Feature Extensions
Depending on time and TA feedback:
- export result as Markdown or PDF
- search or filter previous summaries
- better UI/UX polish

#### Deployment
- Dockerize all services
- Deploy on a VM
- Make the latest version accessible to use

### Version 2 Deliverable
A deployed, documented, containerized product with improved functionality and better usability.

---

## Suggested Technical Stack

### Frontend
- React + Vite

### Backend
- FastAPI (Python)

### Database
- PostgreSQL

### Deployment
- Docker
- Docker Compose
- Ubuntu 24.04 VM

### LLM Integration
- OpenAI-compatible API
- Backend sends meeting notes to the model
- Model returns structured output in a predictable format

---

## High-Level Development Steps

### Step 1 — Project Setup
- Create repository structure
- Initialize frontend, backend, and database setup
- Configure Docker Compose
- Add environment variables

### Step 2 — Database Setup
- Create table for meeting note entries
- Connect backend to PostgreSQL
- Test read/write operations

### Step 3 — Core Backend Logic
- Implement API endpoint for summarization
- Add LLM API integration
- Enforce structured response format

### Step 4 — Frontend MVP
- Build simple input/output interface
- Connect frontend to backend API
- Display generated results clearly

### Step 5 — Persistence
- Save generated results to database
- Confirm stored records can be retrieved

### Step 6 — Version 1 Testing
- Test empty input, long input, and invalid responses
- Fix bugs
- Prepare for TA review

### Step 7 — Version 2 Enhancements
- Add history page or list view
- Improve output quality and UI
- Address TA feedback

### Step 8 — Deployment
- Dockerize frontend and backend
- Configure production environment
- Deploy to VM
- Verify the app works from outside the VM

---

## Version Summary

### Version 1
A functioning web app that transforms meeting notes into:
- summary
- decisions
- action items

and stores the result in the database.

### Version 2
An improved and deployed version that:
- adds history and usability improvements,
- addresses TA feedback,
- is accessible online.

---

## Repository Notes

The GitHub repository should later include:
- MIT License
- README.md
- screenshots
- deployment instructions
- Docker setup
- source code for all services  - summary
  - decisions
  - action items

#### Backend
- API endpoint to accept raw notes
- Call LLM API with a structured prompt
- Parse response into a stable format
- Return processed result to frontend

#### Database
Store:
- original meeting notes
- generated summary
- generated decisions
- generated action items
- creation timestamp

### Version 1 Deliverable
A working web app that allows a user to paste meeting notes, generate structured output, and save the result in the database.

### Version 1 Review with TA
After completion, Version 1 should be shown to the TA for feedback. Feedback points should be recorded and used in Version 2.

---
## Suggested Technical Stack

### Frontend
- React + Vite

### Backend
- FastAPI (Python)

### Database
- PostgreSQL

### Deployment
- Docker
- Docker Compose
- Ubuntu 24.04 VM

### LLM Integration
- OpenAI-compatible API
- Backend sends meeting notes to the model
- Model returns structured output in a predictable format

---

## High-Level Development Steps

### Step 1 — Project Setup
- Create repository structure
- Initialize frontend, backend, and database setup
- Configure Docker Compose
- Add environment variables

### Step 2 — Database Setup
- Create table for meeting note entries
- Connect backend to PostgreSQL
- Test read/write operations

### Step 3 — Core Backend Logic
- Implement API endpoint for summarization
- Add LLM API integration
- Enforce structured response format

### Step 4 — Frontend MVP
- Build simple input/output interface
- Connect frontend to backend API
- Display generated results clearly

### Step 5 — Persistence
- Save generated results to database
- Confirm stored records can be retrieved

### Step 6 — Version 1 Testing
- Test empty input, long input, and invalid responses
- Fix bugs
- Prepare for TA review

### Step 7 — Version 2 Enhancements
- Add history page or list view
- Improve output quality and UI
- Address TA feedback

### Step 8 — Deployment
- Dockerize frontend and backend
- Configure production environment
- Deploy to VM
- Verify the app works from outside the VM

---

## Version Summary

### Version 1
A functioning web app that transforms meeting notes into:
- summary
- decisions
- action items

and stores the result in the database.

---

## Repository Notes

The GitHub repository should later include:
- MIT License
- README.md
- screenshots
- deployment instructions
- Docker setup
- source code for all services
