# Goal: Hackdonald AI Agent Orchestration Architecture

The goal is to design an automated system of AI agents that coordinates the end-to-end process of building websites and applications for businesses. This system maps directly to the workflow provided in the "Hackdonald" flowchart.

Given the complexity of the orchestration system, I propose breaking down the architecture into **four separate markdown files** to ensure clarity and modularity.

## Proposed Markdown Documents

### 1. `01-system-orchestration.md`
**Focus:** The high-level AI agent pipeline and orchestrator.
- Definition of the **Orchestrator Agent** which oversees the entire lifecycle.
- How the system handles the transition of state from one specialized AI agent to the next.
- Communication protocols between agents.

### 2. `02-onboarding-and-sales.md`
**Focus:** Step 1 & 2 from the flowchart (Categories, Context, Invoicing, Contracts).
- **Requirements Agent:** Logic for gathering the customer's business category (Food, Healthcare, Beauty, etc.) and capturing specific context/customizations.
- **Sales & Billing Agent:** Logic for mapping customer needs to specific options, calculating costs, and generating an automated invoice and contract based on their subscription bundle.

### 3. `03-template-engine-and-prototyping.md`
**Focus:** Step 3 from the flowchart (Template Pool, Prototypes).
- **Frontend/Design Agent:** The mechanism for maintaining a "template pool".
- Logic for filtering and offering templates based on the customer's subscription tier.
- The automated process of compiling the selected template and customizations into a fully functional website ready for exhibition/preview.

### 4. `04-backend-and-infrastructure.md`
**Focus:** Step 4 from the flowchart (Databases, Backend Services, App preparation).
- **Backend/DevOps Agent:** How the system provisions the required simultaneous databases.
- Automated deployment of backend services that power both the website and future applications, as dictated by the customer's bundle.

---

## Open Questions
Before I generate these detailed markdown files, I have a few questions to ensure the architecture aligns with your vision:

> [!WARNING]
> Please review the following architectural decisions.

1. **Agent Interaction:** Should the system be designed so that customers chat directly with an AI (e.g., a chatbot for gathering requirements), or will the customer fill out traditional forms that the AI agents then process asynchronously?
2. **Tech Stack Constraints:** Are there specific technologies you want the AI agents to default to when building these websites and backends (e.g., React/Next.js for templates, Node.js/PostgreSQL for backends), or should the architecture remain technology-agnostic at this stage?
3. **Application Scope:** The diagram mentions "Before making the application we must note that website and apps are all backed by the simultaneous databases". Should the design documents include the workflow for generating mobile apps as well, or just focus on the database/backend preparedness for them?

---
Once you approve this structure and provide any answers to the questions above, I will proceed to create the detailed markdown files in your workspace.
