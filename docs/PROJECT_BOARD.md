# Project Roadmap Board

This repository includes an automated workflow to create a Projects v2 board named "Roadmap" and populate it with starter items. The workflow runs on pushes to main and uses the repository's GITHUB_TOKEN to call the GitHub GraphQL API.

If the workflow fails to create the board automatically, follow these manual steps:

1. Ensure your account has permission to create Projects in this repository.
2. Run the GraphQL mutation to create a project manually via gh CLI or the GitHub API.
3. Refer to .github/workflows/create_project.yml for the exact mutation payload and example starter items.

Columns/Statuses (conceptual):
- Backlog
- Planned
- In Progress
- QA
- Done

Custom fields suggested:
- Priority (Low / Medium / High)
- Effort (S / M / L)
- Area (UI / Cloud / Library / Emulation / Shell)

