---
url: /docs/guide/usage/linter/rules/vue/no-deprecated-events-api.md
---

### What it does

Disallow using deprecated Events API (`$on`, `$off`, `$once`) in Vue.js 3.0.0+.

### Why is this bad?

In Vue.js 3.0.0+, the internal event APIs `$on`, `$off`, and `$once` have been removed.
These methods were used for event handling between components but are no longer available.

### Examples

Examples of **incorrect** code for this rule:

```vue
<script>
export default {
  mounted() {
    this.$on("event", () => {});
    this.$off("event");
    this.$once("event", () => {});
  },
};
</script>
```

Examples of **correct** code for this rule:

```vue
<script>
import mitt from "mitt";

const emitter = mitt();

export default {
  mounted() {
    emitter.on("event", () => {});
    emitter.off("event");
    emitter.once("event", () => {});
  },
};
</script>
```

## How to use

## Version

This rule was added in v1.62.0.

## References
