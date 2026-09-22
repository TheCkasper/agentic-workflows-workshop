---
# Trigger - when should this workflow run?
on:
  workflow_dispatch:
  schedule:
    - cron: '0 9 * * 1-5'

# Permissions - what can this workflow access?
permissions:
  contents: read
  issues: read
  pull-requests: read

# Network access
network: defaults

# Motor configurado sin forzar modelo manual (para Copilot Student)
engine:
  id: copilot

# Outputs - what APIs and tools can the AI use?
safe-outputs:
  create-issue:
    max: 1

---

# daily-digest

Every weekday, create a GitHub issue that summarises all open issues and pull requests in this repository. Group them by label. Include the total count, the title, the author, and how long each item has been open. Title the issue "Daily Digest - <date>".