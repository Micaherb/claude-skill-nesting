---
name: grill
description: Quiz the user about their PR to ensure they understand the code. Use when asked to grill, quiz, or verify understanding before pushing.
---

# PR Grill Session

Before un-drafting the PR, let's make sure you understand what you're shipping. I'll review the diff and ask you questions.

## Process

1. Run `git diff master...HEAD` to see all changes
2. Ask pointed questions about the code
3. User may look at the code, this is about them understand what has been created.

## Question Categories

### The "Why" Questions
- Why did you choose this approach over alternatives?
- What problem does this specific change solve?
- Why is this code in this file/class/module?

### The "What If" Questions
- What happens if this input is nil/empty/invalid?
- What happens if this external call fails?
- What happens under high load or concurrent access?

### The "Explain It" Questions
- Walk me through this method line by line
- What does this query actually return?
- How does data flow through this change?

### The "Edge Case" Questions
- What edge cases did you consider?
- What edge cases did you NOT handle, and why?
- How would a malicious user try to break this?

### The "Impact" Questions
- What else in the codebase depends on this?
- Could this change break anything unexpected?
- What's the rollback plan if this causes issues?

## Rules

- I'll ask 3-5 questions based on the complexity of the PR
- If you can't answer confidently, that's a sign to review that part of the code
- "I don't know" is a valid answer - but then you need to find out before pushing
- No trick questions - these are genuine "do you understand your code" checks

## After the Grill

If you passed: You're ready to push with confidence.
If you struggled: Let's review the parts you're unsure about before pushing, then retry the test.
