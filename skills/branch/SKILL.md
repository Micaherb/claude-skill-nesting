---
name: branch
description: Create and name git branches following conventions. Use when starting new work, creating a branch, or asked to work on a new feature/fix.
---

# Branch Naming and Creation Conventions

## Branch Naming

Use these prefixes based on the type of work:

| Type | Prefix | Example |
|------|--------|---------|
| New feature | `feature/` | `feature/add-contact-export` |
| Bug fix | `fix/` | `fix/login-redirect-loop` |
| Honeybadger fix | `hb/` | `hb/nil-error-contact-show` |
| Refactoring | `refactor/` | `refactor/extract-email-service` |
| Chore/dependency | `chore/` | `chore/upgrade-rails-7` |

**Description format:**
- Lowercase only
- Use hyphens between words (not underscores)
- Keep it short but descriptive (3-5 words max)
- No ticket IDs in branch name (those go in commits/PRs)

## Before Starting New Work

**Step 1: Check for uncommitted changes**
```bash
git status
```
If there are uncommitted changes, ask the user what to do:
- Commit them first
- Stash them (`git stash`)
- Discard them (confirm first!)

**Step 2: Determine the base branch**

Check the current branch:
```bash
git branch --show-current
```

**If on `master`:**
1. Pull latest: `git pull origin master`
2. Create branch: `git checkout -b <prefix>/<description>`

**If NOT on `master`:**
Ask the user which approach they want:
1. **Continue on current branch** - Keep working here
2. **Branch from current** - Create new branch with current as base (for related work)
3. **Branch from master** - Switch to master, pull, then create new branch (for unrelated work)

**Step 3: Create the branch**
```bash
# Always pull the base branch first
git pull origin <base-branch>

# Create and switch to new branch
git checkout -b <prefix>/<description>
```

## Edge Cases

**Working on someone else's branch:**
```bash
git fetch origin
git checkout -b <their-branch> origin/<their-branch>
```

**Need to switch branches with uncommitted work:**
```bash
git stash
git checkout <other-branch>
# ... do work ...
git checkout <original-branch>
git stash pop
```

**Branch already exists locally:**
```bash
git checkout <branch-name>
git pull origin <branch-name>
```
