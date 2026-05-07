# AI IT Help Desk Chatbot 🤖
**Multi-Agent System Design, Implementation, Testing & Scaling**

## 1. Project Overview & Problem Space
The **AI IT Help Desk ChatbotChatbot** transforms institutional support by automating high-frequency, low-complexity technical requests. Built as a digital "Product Owner," it streamlines workflows for three primary groups: **College Students** facing remote lockouts, **Faculty/Staff** hindered by repetitive hurdles, and **IT Departments** burdened by manual verification. By integrating **Multi-Agent Automation** and **Retrieval-Augmented Generation (RAG)**, the system provides 24/7 assistance, eliminating traditional service bottlenecks.

### 1.1 Target Users & Success Metrics
| User Group | Core Pain Points | Strategic Success Metric |
| :--- | :--- | :--- |
| **End Users & Students** | Frustrating wait times for basic access and remote login failures. | **≤ 5 Minute** resolution for credential and lockout issues. |
| **New Employees** | Confusion from fragmented onboarding and lack of 24/7 guidance. | **90% Completion Rate** for system setup on the first day. |
| **IT Department** | Operational drain caused by routine tickets instead of priorities. | **90% Reduction** in manual intervention for standard requests. |

---

## 2. System Architecture & Agent Roles
The system utilizes a modular **LangGraph** framework where specialized agents handle distinct stages of the support lifecycle.

### 2.1 Core Agent Framework
* **Intake Agent**: Primary point of contact. Interprets intent, classifies urgency, and routes requests.
* **Knowledge Agent**: Employs **RAG** with **Chroma DB** to provide policy-based answers and troubleshooting steps.
* **Workflow Agent**: Executes backend actions via **MCP (Model Context Protocol)** tools (e.g., password resets).
* **Escalation Agent**: Detects complex/unresolved cases and manages a seamless handoff to human IT technicians.

---

## 3. RAG Integration & Data Pipeline
The **Knowledge Agent** uses a Retrieval-Augmented Generation (RAG) framework to ensure responses are grounded in official institutional documentation rather than LLM "hallucinations."

### 3.1 Retrieval Architecture
* **Vector Database**: Uses **Chroma DB** for high-dimensional vector embeddings of IT manuals.
* **Processing**: Documents are chunked and embedded via OpenAI models to pinpoint specific troubleshooting steps.
* **Grounding**: Every response for VPN or Onboarding is injected with relevant document snippets to ensure accuracy.

| Source Type | Data Included | Agent Application |
| :--- | :--- | :--- |
| **IT Handbooks** | WiFi configuration, VPN setup, and MFA enrollment. | Connectivity troubleshooting. |
| **Onboarding Guides** | New hire checklists and software installation steps. | Employee system setup. |
| **System Logs** | Historical error patterns and diagnostic metadata. | Assisting the Workflow Agent. |

---

## 4. Technical Implementation (MCP Toolbox)
The system interacts with external IT infrastructure using the **Model Context Protocol (MCP)** to execute tools defined in the `final_ver_capstone.py` pipeline.

| Tool Name | Functionality | Logic |
| :--- | :--- | :--- |
| `mfa.verify_identity` | Identity Security | Executes security handshake before sensitive actions. |
| `idp.reset_password` | Account Recovery | Interfaces with Identity Provider to update user credentials. |
| `idp.unlock_account` | Access Restoration | Clears lockout flags in the user directory. |
| `logs.get_recent` | Diagnostics | Retrieves the last 15 network logs to diagnose VPN issues. |
| `itsm.create_ticket` | Ticketing | Generates a structured ticket for human review if RAG fails. |

---

## 5. Industry Awareness & Competitive Positioning
Our project is a **lightweight, open-source alternative** to expensive enterprise AI platforms.

| Feature | Glean | Moveworks | **Our Copilot (Prototype)** |
| :--- | :--- | :--- | :--- |
| **Primary Focus** | Enterprise Search | IT/HR Automation | **Targeted IT Recovery** |
| **Automation** | Search-first | High (Proprietary) | **High (Open-source MCP)** |
| **Deployment** | Weeks/Months | Months | **Rapid (LangGraph Pipeline)** |
| **Annual Cost** | $60,000+ | $100k - $200k+ | **Minimal (API Costs)** |
| **Target User** | Fortune 500 | Large Corporate | **Higher Ed & Small Depts** |

---

## 6. Testing, Scaling & Future Scope
### 6.1 Evaluation Strategy
* **Unit Testing**: Sandbox validation of every MCP tool function in the pipeline.
* **RAG Benchmarking**: Accuracy checks against a "Gold Dataset" of official IT manual snippets.
* **Escalation Logic**: Verification that the system routes to human technicians when resolution goals are not met.

### 6.2 Future Roadmap
* **Horizontal Scaling**: Utilizing LangGraph’s state management to handle hundreds of concurrent student sessions.
* **Advanced Diagnostics**: Future iterations will include `device.quarantine` tools for automated security response.

---

## 🚀 Getting Started
1.  **Clone the Repo**: `git clone [YOUR_REPO_URL]`
2.  **Dependencies**: `pip install langchain langchain-openai langgraph chromadb pypdf`
3.  **API Key**: Add your `OPENAI_API_KEY` to your environment.
4.  **Run**: `python final_ver_capstone.py`# AI IT Help Desk Copilot 🤖
**Multi-Agent System Design, Implementation, Testing & Scaling**
