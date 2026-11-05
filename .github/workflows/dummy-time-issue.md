---
description: Creates a dummy issue that records the time it was created.
on:
  workflow_dispatch:
permissions:
  contents: read
safe-outputs:
  create-issue:
    title-prefix: "[dummy] "
    labels: [dummy]
    max: 1
---

# Dummy Time Issue

Create one issue that records the exact time it was created.

1. Run the `date -u +"%Y-%m-%d %H:%M:%S UTC"` command to get the current time.
2. Create an issue using the `create-issue` safe output:
   - Title: "Dummy issue created at" followed by the time you found.
   - Body: a short friendly message saying this is a dummy issue, with the line
     "Created at: <the time you found>". Make the body at least a few sentences
     long and explain that it was generated automatically to test the workflow.
3. Do not do anything else. If you cannot get the current time, call `noop`
   with a short reason.
