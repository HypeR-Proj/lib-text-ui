<!--
SPDX-FileCopyrightText: 2026 roolrz
SPDX-License-Identifier: Apache-2.0
-->

# lib-text-ui

Application-side terminal keys, display cells and fullscreen sessions.

Exports Decoder/Key for input, Screen and safe display helpers for rendering, and
Session for scoped fullscreen ownership. Native delivery also provides the shared
wrapper package in shared/.

See the [implementation entry](src/lib.rs) and [component declaration](component.json)
for the public interfaces, build dependencies and delivered artifacts.

## Boundaries

The library owns no terminal-service queues or line discipline. Rendered text is
converted into display cells; application models and command policy remain with the
consuming program.

## Build and test

Use this checkout inside the [repo-managed workspace](https://github.com/HypeR-Proj/HypeR).
From this repository directory:

```sh
make
make test
```

An absolute `OUT=/path/to/out` selects a shared output directory. The module
entry delegates to build/system, which prepares the installed SDK and declared
dependencies. Native binaries require HypeR; host module checks cover the tests
selected by component.json. A standalone clone does not contain the workspace’s
other source repositories or Native SDK.
