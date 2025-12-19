# Updating the `.github` Submodule (Org GitHub Templates Repo)

The repository at `templates/repos/github-organization/.github` is a Git submodule that points to:

`git@github.com:NovaStreamCA/.github.git`

Submodules are pinned by the parent repository to a specific commit SHA. Updating the `.github` repo therefore **always requires two steps**:

1. Update and push changes in the submodule repository
2. Update (bump) the pinned submodule SHA in the parent repository

---

## One-time setup (recommended): track an explicit branch

To avoid `origin/HEAD` resolution issues and ensure consistent updates, the parent repository should explicitly track the desired branch (typically `main`).

Run these commands **from the parent repository root**:

```bash
cd /opt/novastream

git config -f .gitmodules submodule.templates/repos/github-organization/.github.branch main
git add .gitmodules
git commit -m "chore: track org .github submodule on main"
git push

git submodule sync --recursive
```

---

## Updating the `.github` submodule

Enter the submodule directory:

```bash
cd /opt/novastream/templates/repos/github-organization/.github
```

Ensure you are on a branch (not a detached HEAD):

```bash
git status
git switch main
git pull --ff-only
```

Make your changes, then commit and push them:

```bash
git add -A
git commit -m "chore: update org GitHub templates/workflows"
git push origin main
```

At this point, the `.github` repository is updated on origin.  
**The parent repository is still pinned to the previous commit** until it is explicitly updated.

---

## Troubleshooting

### `origin/HEAD` or branch resolution errors

If you see errors such as:

```
fatal: Unable to find current origin/HEAD revision
```

Verify the available branches:

```bash
git ls-remote --heads origin
```

- If `refs/heads/main` exists, ensure `.gitmodules` uses `main`
- If only `refs/heads/master` exists, use `master` instead
- If no refs are returned, the repository may be empty or access is misconfigured
