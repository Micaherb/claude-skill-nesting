---
name: linters
description: Runs linters for wealthbox CRM app
---

# Wealthbox CRM linters

If this is not the Wealthbox CRM app, ignore this skill.
Run only the linters which affect relevant files on this branch:

**Backend:**

```bash
bin/docker/docker-runner bundle exec rubocop <files>
bin/docker/docker-runner bundle exec slim-lint <files>
bin/docker/docker-runner bundle exec brakeman --only-files <files>
```

**Frontend:**

```bash
bin/docker/docker-runner yarn eslint <files>
bin/docker/docker-runner yarn prettier --check <files>
bin/docker/docker-runner yarn stylelint <files>
bin/docker/docker-runner yarn tsc --noEmit
```