---
"@biomejs/biome": patch
---

Fixed a `fatal runtime error: stack overflow` that aborted `biome check` when a type-aware nursery rule (such as [`noFloatingPromises`](https://biomejs.dev/linter/rules/no-floating-promises/), [`noMisusedPromises`](https://biomejs.dev/linter/rules/no-misused-promises/), [`noUnnecessaryConditions`](https://biomejs.dev/linter/rules/no-unnecessary-conditions/), [`useArraySortCompare`](https://biomejs.dev/linter/rules/use-array-sort-compare/), [`useExhaustiveSwitchCases`](https://biomejs.dev/linter/rules/use-exhaustive-switch-cases/), [`useFind`](https://biomejs.dev/linter/rules/use-find/), or [`useRegexpExec`](https://biomejs.dev/linter/rules/use-regexp-exec/)) ran over minified or bundled JavaScript with deeply nested call expressions. Type inference now bounds its mutual recursion in `flattening::expressions` instead of exhausting the worker stack.
