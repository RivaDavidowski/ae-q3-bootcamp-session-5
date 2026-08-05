---
description: Validate that all success criteria for the current step are met
mode: agent
agent: code-reviewer
tools: ['search', 'read', 'execute', 'web', 'todo']
---

Validate completion status for a specific step using GitHub Issue success criteria.

Step number (required, examples: 5-0, 5-1): ${input:step-number:Required step number, for example 5-0}

Validation workflow:

1. Use gh CLI workflow utilities from project instructions to locate the main exercise issue.
2. Fetch issue content with comments.
3. Find the section matching # Step {step-number}:.
4. Extract the Success Criteria section for that step.
5. Check each criterion against the current workspace state.
6. Report completion status with specific guidance for each incomplete criterion.

Requirement:

- The step number is required.
