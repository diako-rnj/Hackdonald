# Backend & Database Infrastructure

## Process Overview
Parallel to the frontend generation, the **Backend & DevOps Agent** ensures that the underlying architecture is robust, scalable, and capable of supporting multiple client types. The system relies on standard backend technologies (e.g., Node.js and PostgreSQL) to ensure reliability.

## Simultaneous Database Provisioning
The Hackdonald flowchart specifies that "website and apps are all backed by the simultaneous databases." 
This means the architecture is inherently decoupled (Headless):
- **Database Layer:** A new PostgreSQL instance/schema is provisioned for the client.
- **Data Modeling:** Based on the features in the contract (e.g., an e-commerce store needs `Users`, `Products`, `Orders` tables), the agent runs the necessary database migrations.

## Backend Services
The backend is generated as an API-first service (REST or GraphQL).
- It provides the endpoints required by the website prototype.
- It includes authentication, business logic, and third-party integrations (like payment gateways) mapped from the invoice.

## Readiness for Mobile Expansion
Crucially, because the backend and database are decoupled from the React/Next.js frontend, the infrastructure is immediately ready for expansion.
- The APIs built for the website act as the exact same APIs needed for future iOS and Android applications.
- When the customer is ready to expand, a future **Coder Agent** can simply consume these existing endpoints to generate native mobile applications, adhering to the "simultaneous databases" architecture.
