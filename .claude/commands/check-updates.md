Check if there are updates available for the agent system.

## Steps

1. Read the current local version from `.claude/VERSION` (first line only).

2. Fetch the latest remote version:
```bash
git fetch agents main --quiet 2>/dev/null
```

3. If the fetch succeeded, read the remote VERSION:
```bash
git show agents/main:.claude/VERSION 2>/dev/null
```

4. Compare the two versions:
   - If the remote version is newer → tell the user an update is available, show the changelog diff, and offer to run the update command for them.
   - If they are the same → tell the user they are up to date.
   - If fetch failed (no `agents` remote) → tell the user the agents remote is not configured and show how to add it.

5. If an update is available, offer to run:
```bash
git subtree pull --prefix=.claude agents main --squash
```

Do NOT run the update automatically — present the changes first and let the user decide.
