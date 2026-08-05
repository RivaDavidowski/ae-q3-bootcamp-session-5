# Patterns Discovered

This file captures accumulated implementation and workflow patterns over time. Add patterns when they are validated through coding, testing, or debugging.

## Pattern Template

### Pattern Name

- Context:
- Problem:
- Solution:
- Example:
- Related Files:

---

## Example Pattern: Service Initialization (Empty Array vs Null)

- Context: Service modules that expose collections at startup.
- Problem: Using `null` for uninitialized collections introduces repeated null checks and inconsistent behavior between tests and runtime.
- Solution: Initialize collections to `[]` by default and treat empty array as a valid initialized state.
- Example:

```js
// Prefer
const items = [];

// Avoid
const items = null;
```

- Related Files:
  - `packages/backend/src/app.js`
  - `packages/backend/__tests__/app.test.js`

---

Add new patterns below this line as learnings accumulate.
