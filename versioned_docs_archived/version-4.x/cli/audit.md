---
id: audit
title: pnpm audit
original_id: audit
---

Added in: 4.3.0

Checks for known security issues with the installed packages.

## Options

### --audit-level \<severity>

- Type: **low**, **moderate**, **high**, **critical**
- Default: **low**

Only print advisories with severity greater than or equal to `<severity>`.

### --json

Output audit report in JSON format.

### --dev, -D

Only audit dev dependencies.

### --prod, -P

Only audit prod dependencies.

### --no-optional

Don't audit "optionalDependencies".
