AI IT Help Desk Chatbot
Multi-Agent System Design, Tool Integration, Testing 

1. Problem Definition & Use Case:

The AI IT Help Desk Chatbot is designed to transform the efficiency of institutional support by automating high-frequency, low-complexity technical requests. The system functions as a digital Product Owner to streamline service workflows for three primary groups: College Students facing remote account lockouts, Faculty and Staff whose productivity is hindered by repetitive IT hurdles, and IT Departments burdened by manual credential verification . By integrating multi-agent automation and retrieval-augmented generation (RAG), the system aims to eliminate traditional support bottlenecks, providing users with immediate, 24/7 assistance while allowing human technicians to focus on critical infrastructure tasks. 

2. Target Users:

User Group
Problems
Success Metric
End Users & Students
Frustrating wait times for basic access and remote login failures.
<5 Minute resolution for credential and lockout issues.
New Employees
Confusion from fragmented onboarding steps and lack of after-hours guidance.
90% Completion Rate for all system setups on the first day.
IT Department
Operational drain caused by routine tickets instead of technical priorities.
90% Reduction in manual intervention for standard password requests.


3. Detailed Use Cases

Use Case 1: Password Reset & Account Lockout
Trigger: User is locked out or enters an incorrect password.
Actors: User, Intake Agent, Workflow Agent, MCP Client.
Process: User provides identity information; Workflow Agent uses mfa.verify_identity and idp.reset_password to automate the reset.
Success: New password created without human IT intervention.
Use Case 2: VPN & Network Connectivity
Trigger: Authentication errors or slow remote performance.
Actors: Intake Agent, Knowledge Agent (PDF troubleshooting), Workflow Agent (Log checks).
Inputs: User message and VPN status logs.
Output: Troubleshooting guidance or an automated ticket via itsm.create_ticket if unresolved.
Use Case 3: New Employee IT Onboarding
Trigger: New hire needs help setting up systems.
Process: Intake Agent classifies as onboarding_help; Knowledge Agent retrieves setup docs from Chroma DB.
Output: Structured, 24/7 guidance for account and software setup.
4. Implementation & Scaling

System Dependencies
Directory Services: User directory and Password reset portals.
Infrastructure: MFA systems, VPN clients, and Ticketing systems.
Data: IT support documentation and network logs.
Success Targets
Metric Category
Key Performance Indicator (KPI)
Target Goal
Response Speed
Resolution time for password/account access.
<5 Minutes
Automation
Reduction in manual IT password interventions
90% decrease
Efficiency
First-contact resolution rate for account issues.
>80% Rate
Volume
Reduction in overall password-related ticket volume.
30% Decrease
VPN Support
Manual IT intervention for basic VPN troubleshooting.
40% Reduction
Onboarding
Delivery time for initial IT setup guidance.
<2 Minutes
Onboarding
New hire IT setup completion on the first day.
>90% Rate
Satisfaction
Average user satisfaction score across all agents.
>4.5/5 Score


5. System Architecture & Agent Roles

The Copilot utilizes a specialized Multi-Agent framework where each agent is responsible for a distinct phase of the support lifecycle.
Agent
Primary Function
Key Responsibilities
Intake Agent
Classification & Routing
Acts as the primary point of contact for all technical requests .
Interprets user intent to classify issue type, category, and urgency .
Automates ticket creation and routes tasks to the appropriate downstream agent.
Knowledge Agent
Information Retrieval
Utilizes Retrieval Augmented Generation (RAG) with embeddings and vector databases .
Locates accurate context to provide documentation and troubleshooting steps .
Continuously refines response accuracy based on incoming data.
Workflow Agent
Task Execution
Performs automated actions like password resets and system diagnostic checks .
Integrates with internal APIs and follows predefined business logic .
Logs all actions and outcomes for auditing and tracking purposes.
Escalation Agent
Human Handoff
Detects complex or unresolved cases that require manual intervention .
Prioritizes tickets based on their severity and organizational impact .
Provides the human technician with full interaction history for a seamless handoff.


6. Technical Implementation & Tool Integration

The system is built on a LangGraph pipeline, utilizing a Mock Model Context Protocol (MCP) to allow agents to interact directly with external IT infrastructure through specialized tools.
Mock MCP Toolbox:
Tool Name
Functionality
Code Implementation Logic
mfa.verify_identity
Validates user identity via multi-factor prompts.
Executes security handshake before credential changes.
idp.reset_password
Triggers a secure password reset in the directory.
Interfaces with identity provider to update user credentials.
idp.unlock_account
Clears account lockout flags.
Resets failed login counters in the user directory.
logs.get_recent
Retrieves the last 10-15 network/VPN logs.
Scans system logs for authentication or timeout errors.
itsm.create_ticket
Generates a structured help desk ticket.
Formats user data and logs into a ticket for human review.


7. RAG Integration and Data Pipeline

The Knowledge Agent utilizes a Retrieval-Augmented Generation (RAG) framework to provide evidence-based solutions derived directly from official IT documentation.
Information Retrieval Architecture
Vector Database: The system uses Chroma DB as a centralized repository for high-dimensional vector embeddings of IT manuals and PDFs.
Document Processing: Technical manuals are chunked and converted into embeddings to ensure the agent can pinpoint specific troubleshooting steps.
Contextual Prompting: When a user asks a question, the system retrieves relevant document snippets and injects them into the LLM prompt to prevent "hallucinations".
Knowledge Sources:
Source Type
Data Included
Agent Application
IT Handbooks
WiFi configuration, VPN setup, and MFA enrollment.
Troubleshooting connectivity issues.
Onboarding Guides
New hire checklists, software installation, and HR tool access.
Guiding new employees through setup.
System Logs
Historical error patterns and diagnostic metadata.
Assisting the Workflow Agent in diagnostics.









5. Industry Awareness & Competitive Positioning

The AI IT Help Desk Chatbot is designed as a "lightweight" alternative to enterprise-grade AI platforms. While large-scale vendors offer broad integrations, this project focuses on high-impact, university-specific automation at a fraction of the cost and complexity.
Vendor Comparison Table:
Feature
Glean
Moveworks
Our AI Copilot (Prototype)
Primary Focus
Enterprise-wide Search & Knowledge Discovery.
IT, HR, and Employee Experience Automation.
Targeted IT Support & Account Recovery.
Automation
Search-first; limited direct system actions.
High; specialized Reasoning Engine for tasks.
High; tool-based automation via MCP.
Implementation
Weeks to Months (heavy IT involvement).
Months (vendor-managed services).
Rapid (Lightweight LangGraph Pipeline).
Deployment Cost
~$60,000+ Annual Minimum.
~$50k - $200k+ annually.
Minimal (Open-source / API-based).
Target User
Fortune 500 Enterprises.
Large Corporate IT Departments.
Higher Ed & Specialized Departments.


Scaling & Future Scope

The architecture is designed to grow alongside the institution’s needs.
Horizontal Scaling: Leveraging LangGraph’s state management to handle hundreds of concurrent student sessions.
Expanded Knowledge Base: Integrating additional departmental silos (e.g., Financial Aid or Registrar IT) into the Chroma Vector DB.
Advanced Diagnostics: Future iterations will include device.quarantine tools to handle security threats or malware detection automatically.

