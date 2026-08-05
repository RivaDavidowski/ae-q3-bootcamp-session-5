---
description: Run UI tests and summarize failures
mode: agent
agent: test-engineer
tools: ['read', 'execute', 'todo']
---

Run UI tests with required setup sequencing, then summarize outcomes and failure categories.

Execution rules:

1. REQUIRED first step before /run-ui-tests:
   - Run: npm run test:ui:install --workspace=frontend
2. In Ubuntu/Linux environments, test:ui:install is mandatory and must perform playwright install --with-deps chromium before running tests.
3. test:ui:install includes automatic bounded Ubuntu repo remediation for the common Yarn key issue, plus one retry.
4. Do NOT perform ad-hoc package hunting or broad OS troubleshooting beyond that automated remediation.
5. If install still fails:
   - Stop immediately.
   - Report an environment blocker with the failing command and key error lines.
   - Do not run Playwright tests after a failed dependency install.
6. Ensure both backend and frontend are running before UI execution (start from repo root with npm start if needed).
7. Run UI tests using the project command.
8. Summarize pass/fail results.
9. For failures, classify likely root cause as application code, test code, or environment.
