# Agent Collaboration Guidelines

This document outlines how AI agents can work together effectively across the infrastructure.

## 🤝 Messaging Protocols

### Telegram Bot Communication
All agents have Telegram bot handles for direct messaging:

| Agent | Telegram Handle | Best For |
|-------|-----------------|----------|
| VAI | @vai_agent_bot | General coordination |
| Bridge | @bridge_agent_bot | Integration requests |
| GAAP | @gaap_agent_bot | Financial data queries |
| ONEFLEET | @onefleet_agent_bot | Fleet/vehicle data |
| TMS | @tms_agent_bot | Transportation data |
| TSAP | @one_hr_bot | Safety/carrier lookups |
| Middleware | @middleware_agent_bot | Routing/API gateway |

### Message Format
When agents message each other:
1. **Context First**: Include relevant context from previous messages
2. **Clear Intent**: State what you need clearly
3. **Reference IDs**: Include transaction IDs or reference numbers
4. **Response Window**: Acknowledge receipt if processing takes time

### Example:
```
[FROM: TSAP] Request for carrier analysis
Carrier DOT: 1234567
Context: New onboarding client, needs safety verification
Reference: onboarding-2026-03-09-001
```

## 🌐 Workspace Sharing

### Shared Resources
- **GitHub Repository**: `Jordan-oneproject/ai-agent-collab` (this repo)
- **Documentation**: Keep this repo updated with endpoint changes
- **Tokens/Keys**: Store securely in `~/.github_token` or equivalent

### File Access Patterns
```
# Server 1 agents access:
/home/ubuntu/  # Local workspace

# Server 2 agents access:
/home/ubuntu/  # Local workspace
/home/ubuntu/transportation-platform  # TSAP codebase
```

### Cross-Server Communication
When agents need to coordinate across servers:
1. Use Telegram as the primary messaging bus
2. For data transfer, use shared APIs (documented in endpoints.md)
3. SSH between servers only when necessary for maintenance

## 📋 Task Collaboration Patterns

### Request-Response Flow
```
Agent A (Requester)          Agent B (Worker)
      |                            |
      |---- 1. Send Request ------>| (via Telegram)
      |                            |
      |<--- 2. Acknowledge --------| ("Working on it...")
      |                            |
      |<--- 3. Complete ----------| (Results + context)
      |                            |
      |---- 4. Confirm/Error ---->| (Acknowledge completion)
```

### Parallel Task Execution
For tasks that can be parallelized:
1. **Broadcast** the task to multiple agents
2. **Specify** what each agent should handle
3. **Aggregate** results through a coordinator (usually VAI or Bridge)
4. **Report** completion to the user

### Example:
```
[User Request]: "Analyze this carrier for onboarding"

[VAI to TSAP]: "Get safety scores and fraud analysis for DOT 1234567"
[VAI to TMS]: "Check if carrier exists in our system"
[VAI to GAAP]: "Verify credit worthiness"

[Wait for all responses]
[VAI to User]: Aggregated analysis report
```

## 🔐 Authentication & Security

### Bot Tokens
- Store tokens in `~/.<service>_token` files
- Never commit tokens to repositories
- Rotate tokens periodically

### API Communication
- Prefer HTTPS for all API calls
- Use SSH keys for server-to-server access
- Validate all inputs before processing

### Sensitive Data
- Don't log full API keys or tokens
- Sanitize personal information (PII) in logs
- Use secure channels for credentials

## 🐛 Error Handling

### When an Agent Fails
1. **Acknowledge** the failure to the requester
2. **Log** the error with context
3. **Retry** if appropriate (with backoff)
4. **Escalate** to human if needed

### Error Message Format:
```
[ERROR] Agent: TSAP
Task: Carrier lookup for DOT 1234567
Error: API timeout after 30s
Context: FMCSA API experiencing issues
Action: Retry in 60s or escalate to manual review
```

## 📊 Status Reporting

### Agent Health Checks
Agents should periodically report status:
- ✅ **HEARTBEAT_OK**: All systems operational
- ⚠️ **DEGRADED**: Working with limitations
- ❌ **DOWN**: Service unavailable

### Status Updates Include:
- Server load/memory
- API response times
- Queue depths (if applicable)
- Last successful operation timestamp

## 🚀 Best Practices

1. **Be Proactive**: Check on other agents during heartbeats
2. **Stay Updated**: Read this documentation periodically
3. **Communicate Changes**: Update endpoints.md when services change
4. **Share Knowledge**: Document lessons learned in this repo
5. **Respect Limits**: Don't spam other agents with requests
6. **Clean Up**: Remove temporary files after tasks complete

## 📝 Change Log

| Date | Change | Agent |
|------|--------|-------|
| 2026-03-09 | Initial collaboration docs | VAI |
| 2026-03-09 | Added TSAP endpoint details | TSAP |

---

**Remember**: We're a team. Communication and documentation make us effective!
