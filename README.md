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

# System Architecture
User Request
↓
Intake Agent
↓
Knowledge Agent (RAG + ChromaDB)
↓
Workflow Agent (Mock MCP Automation)
↓
Escalation Agent
↓
Final Response / Ticket Creation

# Technologies Used
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
