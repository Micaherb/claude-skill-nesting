---
name: simplify-pr
description: Review and simplify code before pushing a PR. Use when asked to simplify, clean up, or review changes before pushing.
---

# PR Simplification Review

Review the current branch's changes and help me simplify before I push. Focus on:

## Code Reduction
- Can any code be cut entirely? Look for dead code, unused variables, over-engineered abstractions
- Are there docstrings or comments that just repeat what the code says? Remove them
- Any redundant logic, duplicate checks, or unnecessary nil guards?
- Can conditionals be simplified or inverted to reduce nesting?

## Spec Review
- Are specs testing *behavior* or *implementation details*?
- Any specs that just test Rails/library functionality we don't own?
- Can multiple specs collapse into one with better assertions?
- Are we over-mocking things that could just use real objects?

## Design Simplification
- Could a minor change to how the feature works massively reduce complexity?
- Are we building for hypothetical future requirements instead of current needs?
- Any abstractions that only have one use case?

## Reviewability
- Is the diff easy to skim and understand the intent?
- Could files be reorganized so related changes are together?
- Any changes that should be split into a separate PR?

## Fresh Start?
- If your code is unsatisfactory, use the `fresh-start` skill to reset your changes and try again with your new context

Run `git diff master...HEAD` to see the changes, then give me specific recommendations with file paths and line numbers. Prioritize high-impact simplifications.
