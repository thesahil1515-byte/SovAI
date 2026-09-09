# SovAI

## Sovereign On-Premise Agentic AI Workbench for Confidential Industrial Work

SovAI is a secure, on-premise AI workbench designed for organizations that need to work with confedential industrial data without sending sensitive information to external cloud AI services. 

## Problem 

Industrial organization handle sensitive documents, technical reports, manual and operational data. Using cloud-based AI tools can create privacy, security and data-sovereignty concerns. 

## Solution 

SovAI provides controlled local AI environment where organizations can securely process their confedential data using open-weight AI models and agentic workflows.

## Core Features 

- On-Premises & Privacy-Focused Ai.
- Agentic AI workflows.
- Open-Weight AI Models.
- Secure Knowledge Base.
- Confidential Document Processing.
- Retrieval-Augmented Generation (RAG).
- No Mandatory Cloud Dependency.

## High-level Workflow 

User ---> Upload Confidential Data ---> Secure Knowledge Base ---> Local AI Modals ---> AI Agents ---> Response/Insights.

## Target Users 

- Manufacturing industries. 
- Defence and Aerospace Organizations. 
- Research institutions.
- Engineering organizations.
- Enterprises handling confidential information.

## Technology Stack 

- Python 
- Open weight LLMs
- RAG
- Vector Database 
- Agentic AI 
- Local/ On-premise Deployment 

## Project Status 

Prototype under development for Smart India Hackathon # Sovereign On-Premise Agentic AI Workbench (MRPL PS #26117)

**Problem Statement Title**: Sovereign On-Premise Agentic AI Workbench using Open-Weight Multimodal LLMs for Confidential Industrial Work  
**Target Organization**: Mangalore Refinery and Petrochemicals Limited (MRPL)  
**Theme**: Smart Automation | Category: Software  

---

## 1. Executive Summary & Problem Context
In refineries, PSUs, and defense establishments, routine engineering tasks involve strictly confidential IP:
- Piping & Instrumentation Diagrams (P&IDs)
- Ultrasonic thickness (UT) inspection logs and remaining life calculations
- Hydrocracker, crude distillation, and boiler operating parameters
- Board approval notes, vendor pricing, and shutdown schedules

These sensitive assets cannot be processed via public cloud AI assistants (ChatGPT, Claude, Codex) due to severe security and sovereignty violations. This workbench provides a **100% self-hosted, air-gapped agentic solution** running entirely on an organization's on-premise GPU workstation or server. It enforces zero WAN egress, supports dynamic multi-model routing across open-weight models, executes multi-step agentic plans with a local Python sandbox, and delivers production-grade deliverables (**Word `.docx` Approval Notes**, **Excel `.xlsx` Calculation Workbooks**, and slide briefings).

---

## 2. Key Architecture Pillars

### A. Dynamic Model Orchestrator & Router
- **Multi-Model Fleet**: Connects locally to Ollama (`http://127.0.0.1:11434`) hosting:
  - `qwen2.5-coder:1.5b`: High-precision code generation, engineering formulas (ASME B31.3, API 570), and Python sandbox scripts.
  - `llama3.2:1b`: Strategic reasoning, document synthesis, and official MRPL approval note drafting.
  - `moondream:latest`: Multimodal vision model for P&ID schematics, corrosion inspection photographs, and equipment tag recognition.
- **Dynamic Task Classifier**: Automatically inspects the prompt, uploaded attachments, and domain keywords to select the best model without user friction.

### B. Autonomous Agentic Execution Loop
- **Multi-Step Goal Planner**: Decomposes requests into structured sub-tasks.
- **Local Tool Suite**:
  - `sandbox.py`: Safe, isolated Python subprocess runner with timeout enforcement and security checks.
  - `rag.py`: 100% in-process BM25 retrieval engine querying pre-indexed refinery SOPs, API 570, and ASME standards.
  - `vision.py`: Visual feature extraction, equipment tag locator (e.g. `FCV-102`, `PT-405`), and hazard identification.
  - `doc_parser.py`: Multi-format parser for PDF inspection reports, Word docs, Excel logs, and images.
  - `deliverables.py`: Programmatically generates formal MRPL Word documents (`.docx`), styled Excel calculation workbooks (`.xlsx`), and briefings.

### C. Live Sovereignty & Air-Gap Proof Monitor
- Real-time packet telemetry tracking all loopback socket activity.
- Zero-outbound WAN enforcement.
- Exportable **Cryptographic Air-Gap Compliance Certificate** (SHA-256 hashed) for security audits and judge evaluations.

---

## 3. Pre-Packaged Demo Scenarios (1-Click in UI)

| Scenario | Input | Autonomous Model | Tool Chain | Output Deliverable |
| :--- | :--- | :--- | :--- | :--- |
| **Scenario A** | Scanned UT inspection report of Hydrocracker Feed Line | `llama3.2:1b` (Reasoning) | `doc_parser` → `rag` → `deliverables` | Formal MRPL Note for Approval (`.docx`) |
| **Scenario B** | API 570 / ASME B31.3 Minimum Pipe Thickness Calc | `qwen2.5-coder:1.5b` (Coder) | `rag` → `sandbox` → `deliverables` | Verified Engineering Calc Sheet (`.xlsx`) |
| **Scenario C** | Multimodal P&ID Diagram Inspection | `moondream:latest` (Vision) | `vision` → `rag` → `reasoning_llm` | P&ID Tag & Safety Hazard Audit |

---

## 4. Quick Start & Execution Guide

### Prerequisites
- macOS (Apple Silicon Metal) or Linux with Ollama installed.
- Python 3.10+ (tested on Python 3.14).

### Running the Workbench
```bash
# 1. Clone/Navigate to workspace
cd /Users/pranjalsinghbisht/Documents/sovai

# 2. Launch the workbench
./run.sh
```
Open your browser to:
```
http://127.0.0.1:8000
```

### Running Automated Test Suite
```bash
python3 -m unittest discover tests
```
All 10 tests verify routing, sandbox safety, document generators, and air-gap network assertions.


## Team 

Team SovAI.
