# Upstream review notes

Original repository: https://github.com/arias007/obsidian-ntfy

- Original version at this derivative's provided snapshot: **not yet confirmed**.
- Base commit SHA: **not yet determined** (record when verified; never guess).
- Last reviewed upstream commit SHA: **not yet determined**.

## Procedure

1. Add the original repository as read-only comparison remote:
   `git remote add upstream https://github.com/arias007/obsidian-ntfy.git`
2. `git fetch upstream`
3. Record the upstream commit SHA you reviewed.
4. For the next review, run `git log --oneline OLD_SHA..upstream/main` and `git diff OLD_SHA upstream/main -- main.js styles.css`.
5. Adopt selected changes manually into our own branch and test; **do not auto-merge upstream**.

This project intentionally preserves legacy internal variable, method and CSS names to reduce unnecessary diff noise.
