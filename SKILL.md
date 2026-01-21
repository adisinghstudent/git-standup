---
name: git-standup
description: Get instant project status - recent commits, open issues, PRs, and suggested next steps
skills:
  - status
---

# git-standup

Claude Code skill for instant project status at a glance.

## /status

Get a comprehensive view of where you left off in any project.

```
/status           # Status for last 24 hours
/status yesterday # What you did yesterday
/status week      # Weekly summary
```

### What it shows

- **Recent commits** - Your git activity in the time period
- **Open issues** - Issues assigned to you in this repo
- **Open PRs** - Your pull requests awaiting review
- **Local changes** - Uncommitted work
- **Next steps** - Suggested actions based on context

### Example Output

```
## Project Status: my-app

### Recent Activity (last 24h)
- abc1234 Fix authentication bug
- def5678 Add user profile endpoint

### Open Issues (assigned to you)
- #12 [bug] Login fails on mobile

### Next Steps
1. Continue work on #12 (login bug)
```

## Requirements

- Claude Code CLI
- GitHub CLI (`gh`) for issue/PR info
- Git repository
