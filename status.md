# /status - Project Status at a Glance

Get a comprehensive status of the current repo: recent work, open issues, and what's next.

## Usage

```
/status
/status yesterday
/status week
```

## Instructions

When the user invokes `/status`, gather and display project status:

### 1. Get Recent Git Activity

```bash
# Last 24 hours of commits (default)
git log --oneline --since="24 hours ago" --author="$(git config user.email)"

# For "yesterday"
git log --oneline --since="yesterday" --until="today" --author="$(git config user.email)"

# For "week"
git log --oneline --since="1 week ago" --author="$(git config user.email)"
```

### 2. Get Open Issues Assigned to User

```bash
# Get current repo
repo=$(gh repo view --json nameWithOwner -q '.nameWithOwner')

# Get issues assigned to current user
gh issue list --assignee @me --repo "$repo" --limit 10
```

### 3. Get Open PRs

```bash
gh pr list --author @me --repo "$repo" --limit 5
```

### 4. Check for Local Changes

```bash
git status --short
```

### 5. Check for CLAUDE.md or TODO files

Look for project context:
- `CLAUDE.md` - Project instructions/context
- `TODO.md` or `TODO` - Project todos
- `.github/ISSUE_TEMPLATE` - Issue templates

## Output Format

Present a clean summary:

```
## Project Status: <repo-name>

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
- ?? src/new-file.ts (untracked)

### Next Steps
Based on the open issues and recent work, consider:
1. Continue work on #12 (login bug)
2. Review feedback on PR #15
```

## Notes

- If not in a git repo: "Not in a git repository. Navigate to a project first."
- If no recent activity: "No commits in the last 24 hours"
- Keep the output scannable and actionable
- Suggest logical next steps based on the data
