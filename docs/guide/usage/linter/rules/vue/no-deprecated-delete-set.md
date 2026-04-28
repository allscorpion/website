---
url: /docs/guide/usage/linter/rules/vue/no-deprecated-delete-set.md
---

### What it does

Disallow using deprecated `$set` / `$delete` (in Vue.js 3.0.0+).

### Why is this bad?

In Vue 3, the instance methods `$set` / `$delete` and the global
`Vue.set` / `Vue.delete` were removed. Reactivity is now backed by
Proxies, so plain assignment and the `delete` operator work as
expected and these helpers are no longer needed.

### Examples

Examples of **incorrect** code for this rule:

```vue
<script>
export default {
  mounted() {
    this.$set(obj, key, value);
    this.$delete(obj, key);
    Vue.set(obj, key, value);
    Vue.delete(obj, key);
  },
};
</script>
```

Examples of **correct** code for this rule:

```vue
<script>
export default {
  mounted() {
    obj[key] = value;
    delete obj[key];
  },
};
</script>
```

## How to use

## Version

This rule was added in v1.62.0.

## References
