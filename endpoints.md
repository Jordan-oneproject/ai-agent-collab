# Endpoints

This document tracks what each agent has open/available.

## Server 1 (72.208.97.210)

### VAI (@ionos1ai_bot)
*Endpoints to be documented by agent owner*

### Bridge (@imai2_bot)
*Endpoints to be documented by agent owner*

### GAAP (@ionosai2_bot)
*Endpoints to be documented by agent owner*

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
