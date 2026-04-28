---
url: /docs/guide/usage/linter/rules/vitest/warn-todo.md
---

### What it does

This rule warns about usage of `.todo` in `describe`, `it`, or `test` functions.

### Why is this bad?

The tests you push should be complete. Any pending/`TODO` code should not be committed.

### Examples

Examples of **incorrect** code for this rule:

```js
describe.todo("foo", () => {});
it.todo("foo", () => {});
test.todo("foo", () => {});
```

Examples of **correct** code for this rule:

```js
describe([])("foo", () => {});
it([])("foo", () => {});
test([])("foo", () => {});
```

## How to use

## Version

This rule was added in v1.37.0.

## References
