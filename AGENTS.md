# AGENTS.md — rpiv-todo

Vendored mirror of **juicesharp/rpiv-mono** `packages/rpiv-todo` (npm
`@juicesharp/rpiv-todo` 2.8.0) for the opencharly org. It is a Pi Agent
extension: a `todo` tool, a `/todos` command, and a live panel above the editor,
with the task list rebuilt from the conversation so it survives `/reload` and
compaction.

Canonical files:

- `package.json` — the npm package (`@juicesharp/rpiv-todo`, version `2.8.0`)
  and the `test` script.
- `index.ts` — the extension entry point.
- `todo.ts`, `config.ts`, `tool/`, `view/`, `state/` — the tool, configuration,
  state store/reducer/selectors, task graph, and overlay rendering.
- `locales/` — the i18n strings.
- `docs/` — configuration and tool-schema references.
- `CHANGELOG.md` + `LICENSE` — upstream attribution.
- `README.md` — user overview only; never agent guidance.

There is no `charly.yml`, no candy, and no `skill:` entity — this is a vendored
mirror, so no owning `/charly-<family>:<name>` skill is projected into the
marketplace corpus.

## Load these skills first (R0)

- `/charly-internals:agents` — the closest charly skill: multi-agent support
  across harnesses and the Pi harness relationship.
- `/charly-internals:git-workflow` — before any git/PR action.

There is no pi-family owning skill in the marketplace. The gap is recorded
against `opencharly/opencharly#291`; when one is authored, add it here.

## Build / validate / test

- `npm install` — install dependencies.
- `npm test` — `vitest run` (config, overlay lifecycle/render/shortcut,
  session-isolation, invalidation, task-graph, and ship-manifest tests).
- This mirror carries **no `.github/workflows`**; the merge gate is the
  **org-wide** `charly/pr-validator` (required check `validate / validate`,
  defined in `opencharly/.github`).

## Modify this repo

- This is a **vendored mirror** — prefer upstreaming a fix to
  `juicesharp/rpiv-mono` and re-vendoring, rather than diverging here.
- Keep `CHANGELOG.md` and `package.json`'s `version` current when re-vendoring.

## Landing

Every change lands through a pull request gated by the org-required
`charly/pr-validator`. The landing mechanics — the `feat/` branch, the PR-only
rule, `CHANGELOG/` history, and the tag-on-merge CalVer — are owned by
`/charly-internals:git-workflow` and the umbrella `AGENTS.md` /
`charly/AGENTS.md`; this signpost points at them and does not restate them.
