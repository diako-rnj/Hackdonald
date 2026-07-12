# Hackdonald AI Orchestrator

## Overview
Hackdonald is an internal AI orchestration system designed to automate the end-to-end creation of websites and backend architectures for businesses (primarily restaurants, cafés, and food services). 

The goal of this project is to eliminate the manual bottleneck in web and app development by using specialized AI agents to process structured customer onboarding forms (such as contracts and questionnaires) and automatically generate production-ready code.

## How It Works
Instead of relying on a customer-facing chatbot, the Hackdonald Orchestrator acts asynchronously on a standardized 8-section onboarding form. The architecture is broken down into three core agent roles:

1. **Requirements & Sales Agent:** Ingests the customer form to extract business details, design preferences, and the core menu content.
2. **Backend & DevOps Agent:** Provisions a headless PostgreSQL database and Node.js REST/GraphQL APIs based on the extracted requirements. The backend is designed to be "simultaneous", meaning it is immediately ready to support future iOS and Android mobile applications.
3. **Frontend & Design Agent:** Selects a conceptual React/Next.js template based on the customer's subscription tier, applies their branding, and wires the frontend to the backend APIs to generate a fully functional website prototype.

## Documentation
The architectural blueprint for this system is divided into two categories:

### Main Architecture (`main/`)
- `main/architecture-overview.md`
- `main/frontend-engine.md`
- `main/backend-infrastructure.md`

### Context & Inputs (`context/`)
- `context/onboarding-schema.md`
- `context/llm-master-prompt.md` (A ready-to-use prompt to initialize the Orchestrator on any LLM)
