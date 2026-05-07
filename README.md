# IT Support Multi-Agent System
An AI-powered IT Support System built using LangGraph, ChromaDB, RAG (Retrieval-Augmented Generation), and a Mock MCP Client to automate common IT support workflows such as password resets, VPN troubleshooting, and employee onboarding support.

# Project Overview
This system simulates a real-world enterprise IT support environment using multiple AI agents that collaborate to classify requests, retrieve knowledge from internal documentation, automate workflow actions, and escalate unresolved incidents.
The project combines:

* Multi-Agent Orchestration
* Retrieval-Augmented Generation (RAG)
* Vector Databases
* Workflow Automation
* Mock MCP Tool Integration
* Escalation Routing

Features
Multi-Agent AI Workflow
LangGraph Agent Orchestration
Retrieval-Augmented Generation (RAG)
ChromaDB Vector Database
PDF Knowledge Base Retrieval
Mock MCP Workflow Automation
Ticket Escalation Simulation
Structured IT Troubleshooting Flows
System Architecture
User Request
    ↓
Intake Agent
    ↓
Knowledge Agent (RAG + ChromaDB)
    ↓
Workflow Agent (Mock MCP Client)
    ↓
Escalation Agent
    ↓
Final Response / Ticket Creation

Technology Stack:
Technology
Purpose
Python
Core development language
Google Colab
Development environment
LangGraph
Multi-agent orchestration
LangChain
LLM + RAG framework
OpenAI API
LLM + embeddings
ChromaDB
Vector database
PyPDFLoader
PDF ingestion
Mock MCP Client
Simulated tool integrations


Agent Roles
Intake Agent
Responsible for:
Classifying user requests
Detecting request type
Routing requests between agents
Example intents:
reset_password
unlock_account
vpn_issue
onboarding_help
Knowledge Agent
Responsible for:
Retrieving troubleshooting documentation
Querying ChromaDB vector database
Generating contextual IT support responses
The Knowledge Agent uses:
OpenAI embeddings
ChromaDB
PDF retrieval pipelines
Workflow Agent
Responsible for:
Simulating IT workflow automations
Calling Mock MCP tools
Performing automated support actions
Examples:
Password reset simulation
Account unlock simulation
VPN log inspection
Ticket creation
Escalation Agent
Responsible for:
Escalating unresolved issues
Creating support tickets
Routing requests to human IT technicians
Retrieval-Augmented Generation (RAG)
The system uses ChromaDB as a vector database to store embedded chunks from uploaded IT support documents.
Uploaded PDF Documents
Corporate VPN Access Policy
Password Reset Runbook
IT Onboarding Guide for New Employees
RAG Workflow
User Question
    ↓
Knowledge Agent
    ↓
ChromaDB Retrieval
    ↓
Relevant PDF Chunks Retrieved
    ↓
LLM Generates Contextual IT Support Response

Mock MCP Client
A Mock MCP (Model Context Protocol) Client was implemented to simulate enterprise IT system integrations.
Supported Mock Tools

Tool Name
Purpose
mfa.verify_identity
Simulates MFA verification
idp.reset_password
Simulates password reset
idp.unlock_account
Simulates account unlock
logs.get_recent
Simulates VPN log retrieval
itsm.create_ticket
Simulates ticket creation
itsm.create_incident
Simulates incident escalation


The Mock MCP Client demonstrates standardized tool interaction between AI agents and enterprise systems.
Use Cases
1. Password Reset & Account Lockout Resolution
Workflow + MCP + Automation
Features
Password reset simulation
Account unlock simulation
MFA verification
Escalation support
Objectives
Reduce repetitive IT workload
Improve support response speed
Automate identity-related workflows
User forgets password
    ↓
Intake Agent classifies request
    ↓
Workflow Agent verifies identity
    ↓
Mock MCP resets password
    ↓
Escalation Agent creates ticket if needed

2. VPN & Network Connectivity Troubleshooting
RAG + Workflow + Escalation
Features
VPN troubleshooting retrieval
Log inspection simulation
Ticket escalation
Objectives
Reduce VPN troubleshooting time
Improve ticket quality
Support remote employees
User reports VPN issue
    ↓
Knowledge Agent retrieves VPN troubleshooting steps
    ↓
Workflow Agent simulates log inspection
    ↓
Escalation Agent creates support ticket if unresolved

3. New Employee IT Onboarding Support
RAG-Based Self-Service Support
Features
Onboarding documentation retrieval
Guided setup instructions
Self-service onboarding assistance
Objectives
Reduce repetitive onboarding questions
Improve onboarding completion rate
Provide 24/7 onboarding support
New employee asks onboarding question
    ↓
Knowledge Agent retrieves onboarding documentation
    ↓
System returns structured setup guidance

Future Improvements
Potential future enhancements include:
Real MCP Server Integration
Docker Deployment
Jira/GitHub Ticketing Integration
Web-Based Frontend UI
Real Authentication APIs
Persistent User Memory
Multi-User Support
Enterprise Logging & Observability

Lessons Learned
This project demonstrates:
Multi-agent orchestration
RAG architecture design
Vector database implementation
Enterprise workflow automation
AI-assisted IT support systems
MCP-based tool integration concepts





