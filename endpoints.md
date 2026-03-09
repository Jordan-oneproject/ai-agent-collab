# Endpoints

This document tracks what each agent has open/available.

## Server 1 (72.208.97.210)

### VAI (@ionos1ai_bot)
*Endpoints to be documented by agent owner*

### Bridge (@imai2_bot)
*Endpoints to be documented by agent owner*

### GAAP (@ionosai2_bot)
- **Platform**: https://gaap.pivotos.app
- **Server**: 108.175.11.224
- **Stack**: Node.js/Express + PostgreSQL 15 + Redis 7
- **API Base**: `https://gaap.pivotos.app/api` (port 3000 behind Nginx)
- **API Endpoints** (26 routes):
  - `POST /api/auth/login` — JWT authentication
  - `GET/POST /api/companies` — Multi-entity company management
  - `GET/POST /api/users` — User management (multi-company via join table)
  - `GET/POST /api/transactions` — Transaction CRUD
  - `GET/POST /api/intercompany` — Intercompany transaction tracking
  - `GET/POST /api/documents` — Document upload + OCR extraction
  - `GET/POST /api/chart-of-accounts` — GL account management (53 accounts)
  - `GET/POST /api/journal-entries` — Journal entry management
  - `GET/POST /api/tasks` — Workflow task tracking
  - `GET /api/reports/*` — Financial reports (trial balance, P&L, balance sheet)
  - `POST /api/gaap-transform` — GAAP transform pipeline (PDF→extract→map→adjust→output)
  - `POST /api/ai/chat` — AI chat (Qwen streaming, financial context)
  - `GET /api/consolidation` — Holding company consolidation
  - `GET /api/audit-log` — Audit trail
  - `GET /api/health` — Health check
- **Self-hosted LLM**: 3× Ollama instances (ports 11434-11436)
  - Qwen3:30B (complex reasoning/OCR)
  - Qwen2.5:14B (fast categorization/chat)
- **Database**: PostgreSQL 15 — 47 tables, 15 core + financial statements
- **Purpose**: GAAP-compliant accounting for 400-truck fleet (13 LLCs under one holding corp)

### ONEFLEET (@ionosai3_bot)
*Endpoints to be documented by agent owner*

---

## Server 2 (18.219.38.137)

### TMS (@oneaiteam_bot)
- **OneTMS Platform**: https://onetms.us (staging: 44.193.75.239)
- **Backend API**: /api/* (ASP.NET Core)
- **Highway API Integration**: Carrier lookup, onboarding, monitoring
- **FourKites**: Load tracking integration

### TSAP (@one_hr_bot / @TSAPlatform on X)
- **Platform**: https://tsap.ai
- **Server**: 44.199.195.85
- **API Endpoints**:
  - Carrier lookup
  - Safety scores
  - Inspection data
  - Network analysis (fraud/chameleon detection)
- **Social**: [@TSAPlatform](https://x.com/TSAPlatform)

### Middleware (@imai1_bot)
- **Workspace**: `/home/ubuntu/.openclaw/workspaces/integrations/`
- **Purpose**: Cross-agent integrations and collaboration tasks

---

## Port Summary

| Server | IP | Notable Ports |
|--------|-----|---------------|
| Server 1 | 72.208.97.210 | *TBD* |
| Server 2 | 18.219.38.137 | 5000 (TMS backend), 80/443 (nginx) |
| TSAP | 44.199.195.85 | 443 (tsap.ai) |
