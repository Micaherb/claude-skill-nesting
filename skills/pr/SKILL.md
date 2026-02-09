---
name: pr
description: Create a pull request. Use when asked to create a PR, open a PR, publish a PR, or make a pull request.
---

# PR Creation Guidelines

## Guidelines

- PR SHOULD BE PUBLISHED AS A DRAFT WITH NOT REVIEWERS/ASSIGNEES
- Keep your description short and simple
- Basecamp/Trello/HB link should always be present. If you were not given one, **bold the filler text** so the human reviewer will notice and add it.
- Typically we only need to QA on desktop web. Only check other platforms if:
  - **Mobile web** - User-facing FRONTEND changes
  - **API** - Specifically altered API endpoints
  - **Native apps** - Changes that affect iOS/Android apps or frontend
- Screenshots can be added via the `wealthbox:screenshot` skill

## PR Template

Use this exact format for the PR body:

```markdown
#### What does this PR do? (required)
[Brief description of the change]

#### Link to Basecamp to-do, Trello card, New Relic or Honeybadger (required)
[URL or **ADD LINK** if not provided]

#### What platforms should be included in QA?
- [x] Desktop web
- [ ] Mobile web
- [ ] iOS native app
- [ ] Android native app
- [ ] API
- [ ] N/A

#### QA steps
- [ ] Visit the app
- [ ] [Step 2]
- [ ] [Step 3]

#### Screenshots (if appropriate)
[Screenshots or N/A]
```

## Filling Out the Template

1. **What does this PR do?** - Simple, but comprehensive description of code (1-3 paragraphs max)
2. **Link** - Include the provided link, or use **ADD LINK** (bolded) if none given
3. **Platforms** - Check Desktop web by default. Only check others if relevant per guidelines above
4. **QA steps** - Clear, checkbox steps to test the change. Adding headers to delineate individual tests/areas in the app is helpful.
5. **Screenshots** - Use `wealthbox:screenshot` skill or write N/A
