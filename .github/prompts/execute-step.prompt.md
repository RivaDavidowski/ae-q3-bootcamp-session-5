---
description: Execute instructions from the current GitHub Issue step
mode: agent
agent: tdd-developer
tools: ['search', 'read', 'edit', 'execute', 'web', 'todo']
---

Execute the current exercise step instructions from GitHub Issue context.

Issue number (optional): ${input:issue-number:Optional issue number (leave blank to auto-discover the exercise issue)}

Workflow:

1. If issue number is not provided, use gh CLI workflow utilities from project instructions to locate the exercise issue.
2. Fetch issue content with comments.
3. Parse the latest step instructions from the issue.
4. Execute each :keyboard: Activity: section systematically.

Scope boundaries:

- Do NOT create or run Playwright UI tests in this prompt.
- Handoff rule: use /create-ui-tests and /run-ui-tests for Playwright UI work (auto-switches to test-engineer).

Git boundary:

- Do NOT commit or push changes. Commit/push is handled by /commit-and-push.

Stop condition and next-command output:

- Stop after completing the activity sections.
- Then provide next commands in this exact order:
  - If the current step requires UI workflow: /create-ui-tests -> /run-ui-tests -> /validate-step {step-number}
  - If UI workflow is not required: /validate-step {step-number}
- Never recommend /validate-step before required UI prompts.
- IMPORTANT: Follow testing scope constraints from project instructions.
