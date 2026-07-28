# Pushing this repo to GitHub

The repository is already initialized with a first commit. Two steps.

## 1. Create an empty repo on GitHub

Go to https://github.com/new and create it:

- **Name:** `supplement-label-review`
- **Visibility:** your choice
- **Do NOT** initialize with a README, .gitignore, or license — this repo already has them, and adding them creates a conflict.

## 2. Push

In Terminal, from this folder:

```bash
cd "$(dirname "$0")"

git remote add origin https://github.com/YOUR_USERNAME/supplement-label-review.git
git push -u origin main
```

Replace `YOUR_USERNAME`. If you use SSH instead:

```bash
git remote add origin git@github.com:YOUR_USERNAME/supplement-label-review.git
git push -u origin main
```

## 3. Optional — attach the .skill file to a release

`supplement-label-review.skill` is committed in the repo, but attaching it to a
GitHub Release gives people a clean download link:

1. Repo → **Releases** → **Draft a new release**
2. Tag `v1.0.0`, title `v1.0.0`
3. Drag `supplement-label-review.skill` into the binaries area
4. Publish

The README's install instructions link to `../../releases`, which will resolve
once a release exists.

## After pushing

Update the clone URL in README.md — it currently says `YOUR_USERNAME`.
