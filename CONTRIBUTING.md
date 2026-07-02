# Contributing — how we work

These conventions apply to **every AdrusApp repo**. They exist so three people can ship five apps without stepping on each other.

## The one rule

**If it isn't an issue on the Adrus Board, it isn't happening.** All work — code, infra, marketing — enters as an issue and gets triaged in the weekly planning call.

## Branches & PRs (GitHub Flow)

- `main` is always deployable. **No direct pushes** — every change is a PR.
- Branch names: `feat/<slug>`, `fix/<slug>`, `chore/<slug>`.
- Keep PRs small and focused; open a **draft PR** early for work in progress.
- **Squash merge** only — one commit per PR on `main`.
- Reviewer: the most relevant other developer (CODEOWNERS auto-requests them).
- Link the issue in the description (`Closes #123`) so the board updates itself.

## Commits — Conventional Commits

```
<type>: <summary in the imperative>
```

`type` ∈ `feat` | `fix` | `chore` | `docs` | `refactor` | `test`.

release-please turns these into version bumps and changelogs automatically, so the prefix matters.

## Bilingual rule (ar / en)

Every user-facing string exists in **both** `ar.json` and `en.json`. Arabic is the default locale and renders **RTL** — test both directions for any UI change.

## Labels

`type:*` (bug / feature / chore) · `priority:P0..P2` · `area:*` (backend / web / dashboard / mobile / desktop / infra / marketing) · `blocked` · `launch-v1`.

The canonical set lives in this repo — sync it to a repo with:

```bash
gh label clone AdrusApp/.github --repo AdrusApp/<repo> --force
```

## Secrets

Never commit `.env*` files. Secrets live in GitHub **Actions secrets** (CI) or on the server. If a secret ever lands in a commit: **rotate it first**, then clean up history.
