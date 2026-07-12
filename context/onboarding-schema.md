# Onboarding & Context Ingestion

## Process Overview
This stage addresses the first two steps in the Hackdonald flowchart: interpreting customer context and establishing the invoice/contract baseline. Rather than using an interactive chatbot, the system utilizes a **Requirements Agent** which relies on finalized contracts/questionnaires as structured input.

## Contract & Questionnaire Schema
When a customer onboarding form is processed, the agent extracts the parameters and constructs needed to direct the downstream web and app generation. The ingestion maps directly to the following 8 sections:

### Section 1: Account & Contact
- Extracts the business owner's full name, legal name, email, phone number, and preferred language to localize the app/website content.

### Section 2: Business Basics
- Identifies the business type (Default is Restaurant/Café/Food, but accommodates others).
- Parses the 1-3 sentence business description used for app store listings and website hero sections.
- Stores business hours, physical addresses, and social media links.

### Section 3: Design Gallery
- Maps the chosen design template from the pool.
- Extracts the primary brand color (hex code) and secondary/accent color.
- Ingests the logo (or notes if a simple text-logo needs to be generated).

### Section 4: Menu Content (The Core Application)
- **Data Source:** Identifies if the menu is uploaded (PDF/Word/Images), manually entered, or linked from an existing website.
- **Data Structure:** Parses repeatable fields: Item Name, Description, Price, Category (e.g., Starters, Mains), Photo, and Dietary Tags.
- **Scope:** Calculates total items to flag if bulk import scripts are needed, notes update frequency, and checks if prices should be displayed.

### Section 5: CMS & Maintenance
- Determines if the client will self-manage the menu via a simple web dashboard or if they require managed updates.
- Flags if additional tutorial content is needed for the admin panel.

### Section 6: App Functionality (Simple Core)
- Configures the feature flags for the app (Payments are explicitly excluded to keep the model simple).
- Flags include: Menu browsing (always-on), Business hours/location, Contact button, Map/directions, Social links, and Push notifications.
- Flags any custom "Other" requests that break the "simple app" model for manual review.

### Section 7: Domain & Publishing
- Extracts domain ownership details and DNS access for web deployment.
- Determines Apple Developer and Google Play Developer account status (flags for creation if missing).
- Notes if the app will be published under the client's name or a shared studio account.

### Section 8: Timeline
- Maps the target launch date and explicit out-of-scope items.

## Output
The output of this stage is a standardized, highly-detailed `context.json` file which defines the guardrails for the Template Engine, the Backend Provisioner, and the future Mobile App Coder Agent.
