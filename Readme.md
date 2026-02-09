# OrbitOne – AI Workforce Automation Platform for MSMEs

OrbitOne is an AI-first HR automation platform designed for SMEs and MSMEs.
It brings hiring, onboarding, attendance, payroll, task automation, and performance tracking into one unified system using a multi-agent AI architecture.

Instead of replacing HR teams, OrbitOne works as a digital HR assistant where AI agents automate repetitive workflows while HR retains full control through approval-based execution and audit logs.

***

## Table of Contents

1. [Problem Statement](#problem-statement)
2. [Solution Overview](#solution-overview)
3. [Key Features](#key-features)
4. [System Architecture](#system-architecture)
5. [Technology Stack](#technology-stack)
6. [Project Structure](#project-structure)
7. [Backend Setup](#backend-setup)
8. [Frontend Setup](#frontend-setup)
9. [Environment Variables](#environment-variables)
10. [API Overview](#api-overview)
11. [Feedback Learning Loop](#feedback-learning-loop)
12. [Future Scope](#future-scope)

***

## Problem Statement

Most MSMEs still manage HR operations using disconnected tools such as:

- Excel sheets for attendance and payroll
- WhatsApp for communication and follow-ups
- Emails for onboarding documents
- Paper records for compliance

This fragmented approach leads to:

- inconsistent data and duplicated work
- payroll delays and manual calculation errors
- slow and unstructured hiring and onboarding
- poor accountability and lack of traceability
- reduced productivity and employee satisfaction

OrbitOne solves this by providing one centralized AI-driven platform that automates routine HR workflows while ensuring human control over critical decisions.

***

## Solution Overview

OrbitOne acts as a unified HR operations controller for MSMEs.

The platform uses:

- a multi-agent AI system where each agent handles a specific HR function
- a central orchestrator that coordinates agents and prevents conflicts
- autonomous and semi-automatic execution modes
- a human-in-the-loop approval layer for critical actions
- complete activity logs for accountability and traceability

OrbitOne is designed to be affordable, easy to adopt, and expandable for different MSME needs.

***

## Key Features

- Multi-agent HR automation using 6 specialized AI agents
- Customizable agent instructions based on company policies
- Expandable system (new agents can be added anytime)
- Hiring and recruitment pipeline tracking (Mini ATS for MSMEs)
- Onboarding checklist automation and document tracking
- Task scheduling, reminders, follow-ups, and escalations
- Attendance and payroll workflow automation
- Performance evaluation summaries and KPI tracking
- Unified dashboard for HR operations and reports
- Audit logs with timestamps for every important action
- Human approvals for payroll, offers, onboarding completion, and evaluations

***

## System Architecture

OrbitOne follows a layered architecture:

### Frontend Layer

- HR dashboard for daily operations
- Recruitment pipeline views
- Employee lifecycle workflows
- Task tracking, approvals, and reports


### Backend Layer

- REST APIs for frontend communication
- Orchestrator logic for multi-agent coordination
- Workflow execution engine for tasks and reminders
- Authentication and role-based access control (RBAC)


### Multi-Agent Layer

- Agents generate recommendations, tasks, summaries, and insights
- Orchestrator merges outputs and prevents duplication


### Database Layer

- Stores employee records, attendance logs, payroll metadata
- Stores tasks, approvals, and workflow history
- Stores activity logs and reports

***

## Technology Stack

### Frontend

- React.js
- Vite
- TypeScript
- TailwindCSS / ShadCN UI
- Axios
- Recharts / Chart.js


### Backend

- Python + FastAPI


### Database

- MongoDB / MongoDB Atlas


### Optional

- Firebase Storage / AWS S3 (for employee documents)

***

## AI Agents Included

OrbitOne includes 6 specialized agents:

### 1) HR Analytics Agent

- Detects attendance trends, overtime patterns, and workforce issues.


### 2) Company News Summarizer Agent

- Summarizes circulars, HR announcements, and policy updates.


### 3) Notification and Task Automation Agent

- Converts workflows into tasks, reminders, follow-ups, and escalations.


### 4) Recruitment and Job Applications Agent

- Drafts job descriptions, shortlists candidates, tracks stages, schedules interviews.


### 5) Onboarding and Orientation Agent

- Generates onboarding checklists, tracks documents, assigns mentors, schedules training.


### 6) Performance Management Agent

- Tracks KPIs, generates evaluation summaries, supports monthly/quarterly review cycles.

***

## Project Structure

```
.
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── routers/
│   │   ├── models/
│   │   ├── services/
│   │   ├── agents/
│   │   ├── orchestrator/
│   │   ├── workflows/
│   │   ├── auth/
│   │   └── config.py
│   ├── requirements.txt
│   └── README_backend.md
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── api/
│   │   ├── store/
│   │   └── styles/
│   ├── public/
│   ├── vite.config.ts
│   └── package.json
│
├── docs/
│   ├── architecture.png
│   ├── workflow.png
│   └── screenshots/
│
├── .env.example
└── README.md
```


***

## Backend Setup

From the project root:

```bash
cd backend
python -m venv .venv
source .venv/bin/activate    # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
uvicorn app.main:app --reload
```


***

## Frontend Setup

From the project root:

```bash
cd frontend
npm install
npm run dev
```

Open the provided local URL in your browser to access the HR dashboard UI.

***

## Environment Variables

### Backend `.env`:

```
MONGODB_URI=
JWT_SECRET=
STORAGE_PROVIDER=local
```


### Frontend `.env`:

```
VITE_API_BASE_URL=http://localhost:8000
```


***

## API Overview

OrbitOne exposes REST APIs such as:

- **GET** `/employees` – List employees
- **POST** `/employees` – Add employee
- **GET** `/attendance` – View attendance logs
- **POST** `/payroll/generate` – Generate payroll draft
- **POST** `/approvals/submit` – Submit approval request
- **GET** `/tasks` – List tasks and reminders
- **POST** `/agents/{agent_name}/run` – Run a specific agent
- **GET** `/logs/activity` – View system activity logs

***

## Feedback Learning Loop

OrbitOne includes a continuous improvement mechanism:

1. **AI agent generates** an output (task, suggestion, report)
2. **HR reviews** the output
3. **If incorrect**, HR provides feedback and correction
4. **The agent is reinstructed** and improves future decisions
5. **System reliability increases** over time

This reduces repeated mistakes and builds trust in automation.

***

## Future Scope

OrbitOne is designed to expand into more production-grade features:

- WhatsApp, Gmail, Slack integration for real-world HR operations
- Biometric attendance system integration
- Compliance automation (PF, ESIC, leave policy reminders)
- Employee grievance and ticketing system
- Advanced workforce analytics and forecasting
- More agents for finance, compliance, and operations automation


