# HEARTBEAT.md

## Periodic Checks (rotate through, 2-4 times per day)

### Email Check
- Run: `himalaya envelope list -a personal --page-size 5`
- Alert if: urgent/important unread emails

### Calendar Check  
- Run: `gog calendar events --max 5`
- Alert if: events in next 24h

### GitHub Check
- Run: `gh api notifications --jq '.[].subject.title' 2>/dev/null | head -5`
- Alert if: new notifications

### System Health
- Check disk: `df -h / | tail -1`
- Check memory: `free -h | head -2`
- Alert if: disk >85% or memory >90%

## Rules
- Track last check times in memory/heartbeat-state.json
- Late night (23:00-08:00 IST) → HEARTBEAT_OK unless urgent
- Don't repeat checks done <30 min ago
- If nothing new → HEARTBEAT_OK
