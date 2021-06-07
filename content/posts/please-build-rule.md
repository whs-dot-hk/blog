---
title: "Please build_rule"
date: 2021-06-07T13:22:33+08:00
tags:
  - Build System
  - Please
  - Bazel
---
So, everything in [Please][plz] is a [`build_rule`][build_rule],
e.g. [`go_binary`][go_binary] is returned as a [`build_rule`][go_binary build_rule].

But, what is a [`build_rule`][build_rule]? It **only** said [`pass`][build_rule pass] in the source code.

Luckily, it's [comment][build_rule comment] hinted that it is in [`targets.go`][targets.go]?!

[plz]: https://github.com/thought-machine/please

[build_rule ]: https://github.com/thought-machine/please/blob/v16.1.0/rules/builtins.build_defs#L5
[build_rule comment]: https://github.com/thought-machine/please/blob/v16.1.0/rules/builtins.build_defs#L4
[build_rule pass]: https://github.com/thought-machine/please/blob/v16.1.0/rules/builtins.build_defs#L16

[go_binary ]: https://github.com/thought-machine/please/blob/v16.1.0/rules/go_rules.build_defs#L518
[go_binary build_rule]: https://github.com/thought-machine/please/blob/v16.1.0/rules/go_rules.build_defs#L562

[targets.go]: https://github.com/thought-machine/please/blob/v16.1.0/src/parse/asp/targets.go
