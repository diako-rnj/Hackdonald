# Hackdonald AI System Orchestration

## Overview
Hackdonald is an internal automation tool designed to orchestrate a system of AI agents that drastically simplifies the creation of websites and applications for business clients. Rather than acting as a customer-facing chatbot, the system operates asynchronously on structured inputs (such as a finalized contract) to produce a fully functional website and an underlying backend architecture prepared for future mobile application development.

## The Agentic Pipeline
The orchestration relies on a core **Orchestrator Agent** that manages state transitions between specialized sub-agents. 

### 1. Requirements & Sales Agent
- **Input:** Customer contract and invoice details.
- **Role:** Parses the contract to extract the selected category (Food, Healthcare, Beauty, Fashion, Accessories), the subscription bundle, and specific customization requirements.
- **Output:** A structured JSON object containing the technical requirements, allowed features, and selected bundles.

### 2. Backend & DevOps Agent
- **Input:** The structured technical requirements.
- **Role:** Provisions the simultaneous database schemas (e.g., PostgreSQL) and core backend APIs (e.g., Node.js/Express) that will serve the website and future mobile apps.
- **Output:** Database connection strings, API endpoints, and a deployed backend instance.

### 3. Frontend & Design Agent
- **Input:** The structured technical requirements and backend API documentation.
- **Role:** Queries the "Template Pool" to find the correct number of templates allowed by the customer's subscription tier. It then applies the context and customizations to generate a fully functional prototype.
- **Output:** A compiled, production-ready website frontend.

## Workflow Orchestration
1. **Trigger:** The process begins when an admin uploads a finalized customer contract/invoice into the system.
2. **Analysis:** The Requirements & Sales Agent standardizes the context.
3. **Parallel Execution:** The Orchestrator delegates tasks to the Backend Agent (to spin up databases) and the Frontend Agent (to pull templates) simultaneously.
4. **Integration:** Once the Backend Agent exposes the APIs, the Frontend Agent hooks the selected template into these APIs.
5. **Delivery:** The Orchestrator outputs the links to the finalized website prototype and the backend repository.
