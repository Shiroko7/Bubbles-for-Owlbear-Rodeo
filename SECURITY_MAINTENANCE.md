# Dependency security maintenance

Use Node.js 24. Dependencies and lockfiles have been updated against the current advisory database. CI audits the full dependency graph and builds the application.

Use pnpm 10.34.9 (`packageManager` records this version), then run `pnpm install --frozen-lockfile`, `pnpm audit`, and `pnpm run build`. Only esbuild is allowed to run an installation hook.

The Owlbear SDK currently pins an affected UUID version. A scoped override supplies UUID 11.1.1 or newer; its `v4` API stays compatible. Remove the override after the SDK updates its own requirement.
