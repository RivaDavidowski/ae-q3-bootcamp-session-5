---
description: Create UI tests for required critical user journeys
mode: agent
agent: test-engineer
tools: ['search', 'read', 'edit', 'execute', 'todo']
---

Create or update Playwright UI tests for critical user journeys.

Journeys (optional): ${input:journeys:Optional journeys list (comma-separated). Leave blank to use defaults}

Workflow:

1. If journeys are not provided, use defaults: create, edit, toggle, delete, and core error-state handling.
2. HARD LIMIT: create a maximum of 5 Playwright tests for this run (target 3-5 total).
3. Include at least 1 error-path test within the 3-5 total.
4. If more than 5 candidate scenarios exist, select the highest-risk 5 and list deferred scenarios instead of creating more tests.
5. Generate or update UI tests using the project UI test framework.
6. Prefer stable selectors and state-based waits.
7. Apply Page Object Model (POM): place reusable interactions/selectors in page objects and keep tests scenario-focused.
8. Before finishing, verify the count of created/updated Playwright test cases (test(...) / it(...)) and reduce to <= 5 if over limit.
9. Do not claim small scope if the final authored count is greater than 5.
10. Report files changed and scenarios covered.
