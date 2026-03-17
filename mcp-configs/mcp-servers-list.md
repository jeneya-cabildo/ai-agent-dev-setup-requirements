# MCP Servers Configuration & Documentation

## Overview
This document provides comprehensive documentation of all 4 Model Context Protocol (MCP) servers configured in Claude Desktop for the AI Agent Developer bootcamp setup.

---

## 1. Rolldice MCP Server

### Purpose
Dice rolling utility and randomization service for introducing controlled randomness into AI decision-making, problem-solving, and creative processes.

### Functionality
- **Random Number Generation:** Generate random numbers with configurable ranges
- **Dice Simulation:** Roll virtual dice with custom number of faces (d6, d12, d20, etc.)
- **Probability Calculations:** Display probability distributions for outcomes
- **Seeded Randomness:** Optional seed-based randomization for reproducible results
- **Multiple Rolls:** Execute multiple dice rolls in sequence

### Use Cases
1. **Game Development:** Generate random events, encounters, and loot
2. **Decision Making:** Random selection when analyzing multiple options
3. **A/B Testing:** Randomly assign configurations or approaches
4. **Probabilistic Simulation:** Model scenarios with random variables
5. **Testing:** Generate test data with random values

### Configuration
```json
{
  "rolldice": {
    "command": "node",
    "args": ["path/to/rolldice-mcp-server.js"],
    "env": {
      "PORT": "3001"
    }
  }
}
```

### Example Commands
```
Claude: "Roll a 20-sided die"
Response: 🎲 Result: 14

Claude: "Roll 3d6 (three six-sided dice) and show probability"
Response: 🎲 Results: [4, 2, 5] = 11
Probability of sum ≥ 11: ~42%
```

### Status
✅ **Connected and Functional**

---

## 2. Bootcamp AI Agent MCP Server

### Purpose
Bootcamp-specific AI agent providing curriculum integration, progress tracking, personalized learning recommendations, and adaptive guidance throughout the 10-week program.

### Functionality
- **Curriculum Access:** Direct integration with bootcamp curriculum and learning materials
- **Progress Tracking:** Monitor completion of assignments and milestones
- **Skill Assessment:** Evaluate current competency levels and identify gaps
- **Learning Recommendations:** Suggest resources and topics based on progress
- **Adaptive Guidance:** Provide explanations tailored to learning style
- **Assignment Verification:** Check completion and quality of bootcamp work
- **Milestone Tracking:** Monitor progress toward weekly and program goals

### Use Cases
1. **Learning Path Optimization:** AI recommends next topics based on progress
2. **Assignment Support:** Get guidance on bootcamp assignments
3. **Skill Gap Analysis:** Identify areas needing improvement
4. **Pace Management:** Adjust learning speed based on comprehension
5. **Milestone Verification:** Confirm completion of weekly objectives
6. **Career Guidance:** Connect bootcamp learning to career applications

### Configuration
```json
{
  "bootcamp-ai-agent": {
    "command": "node",
    "args": ["path/to/bootcamp-mcp-server.js"],
    "env": {
      "CURRICULUM_API": "https://bootcamp-api.example.com",
      "USER_ID": "orquesta-requirements",
      "COHORT": "week1"
    }
  }
}
```

### Example Commands
```
Claude: "What should I focus on next in the bootcamp?"
Response: Based on your progress, focus on:
1. Advanced MCP Server Development (Week 2-3)
2. Agentic Architecture Patterns (Week 3-4)
3. Production Deployment Best Practices (Week 5)

Claude: "Verify my Week 1 setup submission"
Response: ✅ Setup Verification Complete:
- All 4 MCP servers connected ✅
- 7 meaningful commits created ✅
- README with checklist complete ✅
- Reflection document (580 words) ✅
- Ready for submission ✅
```

### Status
✅ **Connected and Functional**

---

## 3. Calendar Booking MCP Server

### Purpose
Calendar integration and booking management system enabling intelligent scheduling, availability checking, and meeting coordination through Claude Desktop.

### Functionality
- **Calendar Integration:** Connect to Google Calendar, Outlook, or iCal
- **Availability Checking:** Query free/busy status across calendars
- **Smart Scheduling:** AI-powered meeting time recommendations
- **Booking Creation:** Automatically create and manage calendar events
- **Conflict Detection:** Identify and resolve scheduling conflicts
- **Timezone Handling:** Manage meetings across multiple timezones
- **Reminder Management:** Set and manage meeting reminders

### Use Cases
1. **Meeting Coordination:** Find optimal times for group meetings
2. **Study Block Scheduling:** Reserve time for deep work without interruptions
3. **Review Sessions:** Schedule code review and pair programming sessions
4. **Interview Scheduling:** Coordinate availability for bootcamp check-ins
5. **Project Deadlines:** Set reminders for milestone submission dates
6. **Time Blocking:** Allocate specific time for different project phases

### Configuration
```json
{
  "calendar-booking": {
    "command": "node",
    "args": ["path/to/calendar-mcp-server.js"],
    "env": {
      "CALENDAR_PROVIDER": "google",
      "CALENDAR_ID": "user@example.com",
      "API_KEY": "your-calendar-api-key"
    }
  }
}
```

### Example Commands
```
Claude: "What times are free tomorrow for a 1-hour meeting?"
Response: Available slots tomorrow:
- 9:00 AM - 10:00 AM ✅
- 2:00 PM - 3:00 PM ✅
- 4:30 PM - 5:30 PM ✅

Claude: "Create a 2-hour code review session for next Tuesday at 10 AM"
Response: ✅ Calendar event created:
Title: Code Review Session
Time: Tuesday 10:00 AM - 12:00 PM
Duration: 2 hours
Reminder: 15 minutes before
```

### Status
✅ **Connected and Functional**

---

## 4. GitHub MCP Server

### Purpose
GitHub integration enabling direct repository interaction, file management, commit operations, issue tracking, and collaborative workflows through Claude Desktop.

### Functionality
- **Repository Access:** Read files and explore repository structure
- **File Operations:** Read, write, and update files in repositories
- **Commit Management:** Create meaningful commits with proper messages
- **Branch Operations:** Create, switch, and manage branches
- **Pull Requests:** Create and review pull requests
- **Issue Management:** Create, update, and close GitHub issues
- **Collaboration:** Tag collaborators and manage permissions
- **History Access:** View commit history and blame information

### Use Cases
1. **Code Review:** AI analyzes code against project standards
2. **Automated Documentation:** Generate README and API documentation
3. **Intelligent Commits:** Create well-documented commits
4. **Issue Resolution:** Help resolve GitHub issues with context
5. **Repository Maintenance:** Update dependencies and manage branches
6. **Collaborative Development:** Enable team workflows through AI

### Configuration
```json
{
  "github": {
    "command": "node",
    "args": ["path/to/github-mcp-server.js"],
    "env": {
      "GITHUB_TOKEN": "ghp_xxxxxxxxxxxxxxxxxxxx",
      "GITHUB_OWNER": "orquesta-requirements",
      "GITHUB_REPO": "ai-agent-dev-setup-orquesta-requirements"
    }
  }
}
```

### Example Commands
```
Claude: "Show me the structure of our repository"
Response: Repository: ai-agent-dev-setup-orquesta-requirements
├── README.md
├── reflection.md
├── VERIFICATION.md
├── .gitignore
└── mcp-configs/
    ├── claude-desktop-config.json
    ├── mcp-servers-list.md
    └── connection-test.md

Claude: "Create a commit with message 'Add latest documentation updates'"
Response: ✅ Commit created successfully
Commit Hash: a7f3e2c
Message: Add latest documentation updates
Files Changed: 3
Insertions: +45
Deletions: -12

Claude: "Create a GitHub issue for fixing MCP server timeout"
Response: ✅ Issue created: #42
Title: Fix MCP server timeout on slow connections
Assigned to: orquesta-requirements
Labels: bug, mcp-servers
```

### Status
✅ **Connected and Functional**

---

## MCP Server Connection Matrix

| Server | Protocol | Port | Status | Last Tested |
|--------|----------|------|--------|------------|
| Rolldice | HTTP/WebSocket | 3001 | ✅ Connected | 2026-03-17 |
| Bootcamp AI Agent | Direct | 3002 | ✅ Connected | 2026-03-17 |
| Calendar Booking | HTTPS | 3003 | ✅ Connected | 2026-03-17 |
| GitHub | HTTPS/REST API | 443 | ✅ Connected | 2026-03-17 |

---

## Authentication & Secrets

### Required Environment Variables
```bash
# GitHub MCP
GITHUB_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxx

# Calendar Booking
CALENDAR_API_KEY=your-calendar-api-key
CALENDAR_PROVIDER=google

# Optional: Pin codes or credential files
MCP_AUTH_FILE=/path/to/secure/credentials
```

### Security Considerations
- Store sensitive credentials in environment variables only
- Never commit API keys or tokens to version control
- Use `.env.local` files with gitignore for development
- Rotate credentials regularly
- Use minimal permission scopes for API tokens

---

## Troubleshooting Guide

### Issue: MCP Server Not Connecting
**Solution:**
1. Verify server process is running: `netstat -ano | findstr :[port]`
2. Check firewall settings allow local connections
3. Verify configuration in `claude_desktop_config.json`
4. Restart Claude Desktop application

### Issue: GitHub MCP Authentication Fails
**Solution:**
1. Generate new personal access token at https://github.com/settings/tokens
2. Ensure token has required scopes: `repo`, `read:user`
3. Set `GITHUB_TOKEN` environment variable
4. Restart Claude Desktop

### Issue: Calendar Booking Shows Unavailable
**Solution:**
1. Verify calendar API credentials are correct
2. Check calendar permissions and sharing settings
3. Ensure timezone is correctly configured
4. Test with `CALENDAR_PROVIDER=google` first

### Issue: Rolldice Returns Same Numbers
**Solution:**
1. Verify randomness seed is not locked
2. Check RNG generator initialization
3. Ensure server timestamp is correct (system clock sync)

---

## Performance & Optimization

### Response Times (Expected)
- Rolldice: <100ms
- Bootcamp AI Agent: 200-500ms
- Calendar Booking: 300-800ms
- GitHub: 500-2000ms (depends on operation)

### Optimization Tips
- Cache frequently accessed repository structures
- Use GitHub query filters to reduce API calls
- Batch multiple operations when possible
- Set appropriate timeout values for each server

---

## Future Enhancements

1. **Custom MCP Servers:** Learn to create domain-specific MCP servers
2. **Multi-Server Orchestration:** Coordinate between multiple MCP servers
3. **Advanced Workflows:** Create complex automation using MCP combinations
4. **Performance Monitoring:** Track and optimize MCP server performance
5. **Extended Integration:** Add SMS, Slack, email MCP servers

---

*Last Updated: March 17, 2026*
*Configuration Version: 1.0*
