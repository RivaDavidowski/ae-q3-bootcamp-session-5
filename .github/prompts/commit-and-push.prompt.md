---
description: Analyze changes, generate commit message, and push to feature branch
mode: agent
tools: ['read', 'execute', 'todo']
---

Analyze local changes, generate a conventional commit message, and push to the requested branch.

Branch name (required): ${input:branch-name:Feature branch name (required, for example: feature/my-step-work)}

Requirements:

- If no branch name is provided, ask the user for it before continuing.
- If the current step includes required UI workflow, also run npm run test:ui (or require successful /run-ui-tests in the current chat) before committing.

Git workflow:

1. Analyze changes with git diff and related git status context.
2. Generate a descriptive conventional commit message aligned with project Git Workflow guidance.
3. If the branch does not exist, create and switch: git checkout -b <branch-name>.
4. If the branch exists, switch to it: git checkout <branch-name>.
5. Stage all changes: git add .
6. Commit using the generated message.
7. Push to the specified branch: git push origin <branch-name>.

Safety boundary:

- Do NOT commit to main or any other branch.
- ONLY use the user-provided branch name.
