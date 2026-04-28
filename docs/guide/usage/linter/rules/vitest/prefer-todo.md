---
url: /docs/guide/usage/linter/rules/vitest/prefer-todo.md
---

### What it does

When test cases are empty then it is better to mark them as `test.todo` as it
will be highlighted in the summary output.

### Why is this bad?

This rule triggers a warning if empty test cases are used without 'test.todo'.

### Examples

Examples of **incorrect** code for this rule:

```javascript
test("i need to write this test"); // invalid
test("i need to write this test", () => {}); // invalid
test.skip("i need to write this test", () => {}); // invalid
```

Examples of **correct** code for this rule:

```javascript
test.todo("i need to write this test");
```

## How to use

## Version

This rule was added in v0.0.16.

## References
