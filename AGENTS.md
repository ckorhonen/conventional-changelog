# Repository agent guide

## Repository workflow and completion

The pnpm workspace contains independently published `packages/` with shared lint/Vitest configuration. Use repository-pinned pnpm and `pnpm install --frozen-lockfile`. Package engines require Node 18+; retain CI's matrix. `pnpm build` recursively builds; `pnpm lint`, `pnpm test:types`, and `pnpm test:unit` are distinct checks combined by `pnpm test`.

Git-history tests need disposable repos and local identity, not changes to user global Git identity. Inspect generated output and affected package boundaries. Hook-update/release scripts can change config, commit/tag, or publish; keep those effects within explicit authorization and separate local validation from release evidence.

Continue the authorized change through relevant validation and repair of failures it causes; preserve unrelated work. Report checks actually run, commands only inspected, and exact missing prerequisites. Ask only when a material decision, missing authorization, or required input blocks progress; continue independent reversible work. Existing mandatory contribution and validation gates still apply.
