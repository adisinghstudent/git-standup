# git-standup

Claude Code skill for instant project status: recent commits, open issues, and what's next.

## The `/status` Skill

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
- #8 [feature] Add dark mode

### Open PRs
- #15 Add user authentication (ready for review)

### Local Changes
- M src/auth.ts (modified)

### Next Steps
1. Continue work on #12 (login bug)
2. Review feedback on PR #15
```

## Installation

```bash
# Install via npx
npx add-skill git-standup

# Or manually copy status.md to ~/.claude/skills/
```

## Requirements

- [Claude Code](https://claude.ai/claude-code) CLI
- [GitHub CLI](https://cli.github.com/) (`gh`) for issue/PR info
- Git repository

## License

MIT
