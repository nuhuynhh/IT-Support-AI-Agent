# AI IT Help Desk Copilot 🤖
**Multi-Agent System Design, Tool Integration & Implementation**

## 1. Project Overview
The **AI IT Help Desk Copilot** transforms institutional support by automating high-frequency, low-complexity technical requests. Built on a **LangGraph** multi-agent architecture, the system acts as an automated service layer for students, faculty, and IT departments.

### Target User Profiles & KPIs
| User Group | Core Pain Points | Strategic Success Metric |
| :--- | :--- | :--- |
| **End Users & Students** | Remote lockouts and long wait times. | **≤ 5 Min** resolution for access issues. |
| **New Employees** | Fragmented onboarding and setup steps. | **90% Completion** on Day 1. |
| **IT Department** | Resource drain from repetitive tickets. | **90% Reduction** in manual resets. |

---

## 2. System Architecture
The system utilizes a modular multi-agent framework where specialized agents handle different stages of the support lifecycle.

### Agent Framework
* **Intake Agent**: Classifies intent (Issue type, urgency) and routes to downstream agents.
* **Knowledge Agent**: Employs **RAG (Retrieval-Augmented Generation)** to query a **Chroma Vector DB** for policy-based answers.
* **Workflow Agent**: Executes backend actions via **MCP (Model Context Protocol)** tools (e.g., password resets).
* **Escalation Agent**: Detects complex cases and hands off to human technicians with full context.

---

## 3. Technical Implementation
The pipeline is implemented in Python using the following tech stack:
- **Orchestration**: LangGraph (Stateful Multi-Agent Workflows)
- **Memory/Vector DB**: ChromaDB
- **LLM**: OpenAI GPT-4o
- **Protocol**: Model Context Protocol (MCP) for tool execution

### Integrated Tools (Workflow Agent)
| Tool Name | Action | Logic |
| :--- | :--- | :--- |
| `mfa.verify_identity` | Identity Security | Multi-factor verification before sensitive actions. |
| `idp.reset_password` | Automation | Securely updates credentials in the directory. |
| `logs.get_recent` | Diagnostics | Retrieves the last 15 VPN/Network logs for analysis. |
| `itsm.create_ticket` | Escalation | Generates a structured ticket for human IT review. |

---

## 4. Industry Awareness
Our project is positioned as a **lightweight, open-source alternative** to high-cost enterprise solutions.

| Feature | Glean | Moveworks | **Our Copilot (Prototype)** |
| :--- | :--- | :--- | :--- |
| **Primary Focus** | Enterprise Search | HR/IT Automation | **Targeted IT Recovery** |
| **Automation** | Search-first | High (Proprietary) | **High (Open-source MCP)** |
| **Deployment** | Months | Months | **Days/Weeks** |
| **Annual Cost** | $60k+ | $100k+ | **Minimal (API Costs)** |

---

## 5. Scaling & Future Scope
- **Horizontal Scaling**: Leveraging LangGraph state management to handle concurrent user sessions.
- **Deep Integration**: Expanding the toolset to include automated device quarantine and software license provisioning.
- **Multi-Modal Support**: Future support for image-based troubleshooting (e.g., photos of hardware errors).

---

## 🚀 How to Run the Demo
1. Clone the repository: `git clone <repo-url>`
2. Install dependencies: `pip install -r requirements.txt`
3. Add your `OPENAI_API_KEY` to the environment variables.
4. Run the Gradio UI: `python final_ver_capstone.py`# AI IT Help Desk Copilot 🤖
**Multi-Agent System Design, Tool Integration & Implementation**

## 1. Project Overview
The **AI IT Help Desk Copilot** transforms institutional support by automating high-frequency, low-complexity technical requests. Built on a **LangGraph** multi-agent architecture, the system acts as an automated service layer for students, faculty, and IT departments.

### Target User Profiles & KPIs
| User Group | Core Pain Points | Strategic Success Metric |
| :--- | :--- | :--- |
| **End Users & Students** | Remote lockouts and long wait times. | **≤ 5 Min** resolution for access issues. |
| **New Employees** | Fragmented onboarding and setup steps. | **90% Completion** on Day 1. |
| **IT Department** | Resource drain from repetitive tickets. | **90% Reduction** in manual resets. |

---

## 2. System Architecture
The system utilizes a modular multi-agent framework where specialized agents handle different stages of the support lifecycle.

### Agent Framework
* **Intake Agent**: Classifies intent (Issue type, urgency) and routes to downstream agents.
* **Knowledge Agent**: Employs **RAG (Retrieval-Augmented Generation)** to query a **Chroma Vector DB** for policy-based answers.
* **Workflow Agent**: Executes backend actions via **MCP (Model Context Protocol)** tools (e.g., password resets).
* **Escalation Agent**: Detects complex cases and hands off to human technicians with full context.

---

## 3. Technical Implementation
The pipeline is implemented in Python using the following tech stack:
- **Orchestration**: LangGraph (Stateful Multi-Agent Workflows)
- **Memory/Vector DB**: ChromaDB
- **LLM**: OpenAI GPT-4o
- **Protocol**: Model Context Protocol (MCP) for tool execution

### Integrated Tools (Workflow Agent)
| Tool Name | Action | Logic |
| :--- | :--- | :--- |
| `mfa.verify_identity` | Identity Security | Multi-factor verification before sensitive actions. |
| `idp.reset_password` | Automation | Securely updates credentials in the directory. |
| `logs.get_recent` | Diagnostics | Retrieves the last 15 VPN/Network logs for analysis. |
| `itsm.create_ticket` | Escalation | Generates a structured ticket for human IT review. |

---

## 4. Industry Awareness
Our project is positioned as a **lightweight, open-source alternative** to high-cost enterprise solutions.

| Feature | Glean | Moveworks | **Our Copilot (Prototype)** |
| :--- | :--- | :--- | :--- |
| **Primary Focus** | Enterprise Search | HR/IT Automation | **Targeted IT Recovery** |
| **Automation** | Search-first | High (Proprietary) | **High (Open-source MCP)** |
| **Deployment** | Months | Months | **Days/Weeks** |
| **Annual Cost** | $60k+ | $100k+ | **Minimal (API Costs)** |

---

## 5. Scaling & Future Scope
- **Horizontal Scaling**: Leveraging LangGraph state management to handle concurrent user sessions.
- **Deep Integration**: Expanding the toolset to include automated device quarantine and software license provisioning.
- **Multi-Modal Support**: Future support for image-based troubleshooting (e.g., photos of hardware errors).

---

## 🚀 How to Run the Demo
1. Clone the repository: `git clone <repo-url>`
2. Install dependencies: `pip install -r requirements.txt`
3. Add your `OPENAI_API_KEY` to the environment variables.
4. Run the Gradio UI: `python final_ver_capstone.py`


