# .github

Org-wide defaults for all **AdrusApp** repositories:

- **Issue forms** (bug / feature / task) and the **PR template** — automatically applied to every repo that doesn't define its own
- **[CONTRIBUTING.md](CONTRIBUTING.md)** — how we branch, commit, review and label
- **profile/README.md** — the org profile page
- The **canonical label set** lives on this repo — sync it to any repo with:

  ```bash
  gh label clone AdrusApp/.github --repo AdrusApp/<repo> --force
  ```
