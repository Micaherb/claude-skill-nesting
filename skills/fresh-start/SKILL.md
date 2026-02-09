---
name: fresh-start
description: Discard current implementation and rewrite cleanly using lessons learned. Use when code works but is messy, or when asked to start over, reset and rewrite, or try a cleaner approach.
---

# Fresh Start - Learn and Reset

The current implementation works (or partially works) but isn't clean. Before throwing it away, capture what we learned, then start fresh.

## Step 1: Capture Learnings

Review the current implementation and document:

1. **What worked** - Approaches that solved the problem correctly
2. **What didn't** - Dead ends, failed approaches, things that seemed right but weren't
3. **Gotchas discovered** - Edge cases, unexpected behaviors, tricky parts of the codebase
4. **Key insights** - "Aha" moments about how the system works
5. **Simpler path** - Now that we understand it, what's the most direct solution?

Write these learnings as a brief summary before proceeding.

## Step 2: Reset the Code

Ask the user which reset approach they want:
- **Hard reset**: `git checkout master -- <files>` or `git reset --hard master` (lose all changes)
  - NOTE: If your current branch is based off a different base branch, use that base instead. Please double check your base branch before re-checking out.
- **Stash first**: `git stash` (preserve changes just in case)
- **New branch**: Create fresh branch from master

## Step 3: Implement Clean

With learnings in mind, implement the solution again:
- Take the most direct path now that we know what works
- Avoid the dead ends we already explored
- Write it simply the first time - no exploratory code
- Apply gotchas we discovered upfront

## Key Principle

The first implementation was *research*. This implementation is *production*.
