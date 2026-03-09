# Agent Endpoints Documentation

This document lists all exposed ports, APIs, and services for each agent.

## Server 1 (72.208.97.210)

### VAI
| Service | Port | Protocol | Description |
|---------|------|----------|-------------|
| API | TBD | HTTP/HTTPS | General assistant API |
| Telegram Bot | N/A | Telegram API | @vai_agent_bot |

### Bridge
| Service | Port | Protocol | Description |
|---------|------|----------|-------------|
| API | TBD | HTTP/HTTPS | Integration gateway |
| Telegram Bot | N/A | Telegram API | @bridge_agent_bot |

### GAAP
| Service | Port | Protocol | Description |
|---------|------|----------|-------------|
| API | TBD | HTTP/HTTPS | Accounting/Finance API |
| Telegram Bot | N/A | Telegram API | @gaap_agent_bot |

### ONEFLEET
| Service | Port | Protocol | Description |
|---------|------|----------|-------------|
| API | TBD | HTTP/HTTPS | Fleet management API |
| Telegram Bot | N/A | Telegram API | @onefleet_agent_bot |

---

## Server 2 (18.219.38.137)

### TMS
| Service | Port | Protocol | Description |
|---------|------|----------|-------------|
| Web UI | TBD | HTTPS | Transportation Management System dashboard |
| API | TBD | HTTP/HTTPS | TMS core API |
| Telegram Bot | N/A | Telegram API | @tms_agent_bot |

### TSAP
| Service | Port | Protocol | Description |
|---------|------|----------|-------------|
| Platform | 443 | HTTPS | https://tsap.ai - Main web platform |
| API | TBD | HTTPS | TSAP API endpoints |
| Carrier Lookup | TBD | HTTPS | Carrier vetting and lookup |
| Safety Scores | TBD | HTTPS | Safety score retrieval |
| Inspection Data | TBD | HTTPS | FMCSA inspection data |
| Network Analysis | TBD | HTTPS | Fraud network analysis |
| Telegram Bot | N/A | Telegram API | @one_hr_bot |
| Social | N/A | X/Twitter | @TSAPlatform |

**TSAP Server:** 44.199.195.85

### Middleware
| Service | Port | Protocol | Description |
|---------|------|----------|-------------|
| API Gateway | TBD | HTTP/HTTPS | System integration layer |
| Routing | TBD | HTTP/HTTPS | Request routing and load balancing |
| Telegram Bot | N/A | Telegram API | @middleware_agent_bot |

---

## 🔒 Security Notes

- All HTTPS endpoints should use valid SSL certificates
- API keys/tokens should be stored securely (e.g., `~/.github_token`)
- Internal services may be firewalled between servers
- Telegram bots use Bot API with secure tokens

## 📝 TODO

- [ ] Document exact ports for each service
- [ ] Add authentication methods for each endpoint
- [ ] Document rate limits
- [ ] Add health check endpoints
- [ ] Document WebSocket endpoints if any
