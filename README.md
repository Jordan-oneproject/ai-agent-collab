# AI Agent Collaboration Documentation

This repository documents the AI agents, their locations, endpoints, and collaboration protocols across the infrastructure.

## 🗺️ Agent Map

### Server 1 (72.208.97.210)
| Agent | Purpose | Telegram Handle | Notes |
|-------|---------|-----------------|-------|
| **VAI** | General assistant | @vai_agent_bot | Main coordination agent |
| **Bridge** | Integration layer | @bridge_agent_bot | Connects various services |
| **GAAP** | Accounting/Finance | @gaap_agent_bot | Financial operations and reporting |
| **ONEFLEET** | Fleet management | @onefleet_agent_bot | Vehicle and logistics tracking |

### Server 2 (18.219.38.137)
| Agent | Purpose | Telegram Handle | Notes |
|-------|---------|-----------------|-------|
| **TMS** | Transportation Management System | @tms_agent_bot | Core TMS platform |
| **TSAP** | Transportation Safety Intelligence | @one_hr_bot | Carrier vetting, fraud detection |
| **Middleware** | System integration layer | @middleware_agent_bot | API gateway and routing |

### Additional Agent Details

#### TSAP (@one_hr_bot)
- **Platform:** https://tsap.ai
- **Server:** 44.199.195.85
- **Purpose:** Transportation safety intelligence — carrier vetting, chameleon carrier detection, fraud network analysis, FMCSA data
- **Social:** @TSAPlatform on X
- **Endpoints:** TSAP API (carrier lookup, safety scores, inspection data, network analysis)

## 📁 Repository Structure

```
ai-agent-collab/
├── README.md           # This file - Agent map and overview
├── endpoints.md        # API endpoints and service ports
└── collaboration.md    # Collaboration protocols and guidelines
```

## 🚀 Quick Start

1. Check `endpoints.md` for available services and APIs
2. Review `collaboration.md` for messaging protocols
3. Contact agents via their Telegram handles for coordination

## 📞 Support

For issues or questions about this documentation, contact the main coordination agent.
