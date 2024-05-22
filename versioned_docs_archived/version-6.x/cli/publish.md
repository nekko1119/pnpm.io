---
id: publish
title: pnpm publish
---

Publishes a package to the registry.

```sh
pnpm [-r] publish [<tarball|folder>] [--tag <tag>]
     [--access <public|restricted>]
```

When publishing a package inside a [workspace](../workspaces.md), the LICENSE file
from the root of the workspace is packed with the package (unless the package
has a license of its own).

You may override some fields before publish, using the
[publishConfig] field in `package.json`.
You also can use the [`publishConfig.directory`](../package_json.md#publishconfigdirectory) to customize the published subdirectory (usually using third party build tools).

When running this command recursively (`pnpm -r publish`), pnpm will publish all
the packages that have versions not yet published to the registry.

[publishConfig]: ../package_json.md#publishconfig

## Options

### --tag \<tag\>

Publishes the package with the given tag. By default, `pnpm publish` updates
the `latest` tag.

For example:

```sh
# inside the foo package directory
pnpm publish --tag next
# in a project where you want to use the next version of foo
pnpm add foo@next
```

### --access \<public|restricted\>

Tells the registry whether the published package should be public or restricted.

### git-checks

Added in: v4.11.0

- Default : **true** (since v5)
- Type: **Boolean**

When true, `pnpm publish` checks if the current branch is your publish branch
(master by default), clean, and up-to-date.

### publish-branch

Added in: v4.11.0

- Default: **master**
- Types: **String**

The primary branch of the repository which is used for publishing the latest
changes.

### --force

Added in: v5.18.0

Try to publish packages even if their current version is already found in the
registry.

### --report-summary

Added in: v6.5.0

Save the list of published packages to `pnpm-publish-summary.json`. Useful when some other tooling is used to report the list of published packages.

### --filter \<package_selector\>

Added in: 4.6.0

[Read more about filtering.](../filtering.md)
