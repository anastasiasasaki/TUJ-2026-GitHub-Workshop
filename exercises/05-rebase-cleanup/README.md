# Exercise 5 — Rebase Cleanup

**Skill:** Rebasing your branch onto `main` for a clean history

**Time:** ~10 minutes

---

> **Windows users:** Use **Git Bash** for all commands.

---

## What is rebasing?

**Rebasing** replays your branch's commits on top of the latest `main`. Instead of creating a messy merge commit, it makes it look like you started your work from the latest version of `main` all along.

### Merge vs. Rebase — a quick comparison

```
MERGE (creates a merge commit):          REBASE (replays your commits on top):

  main:  A — B — C ———— M                main:  A — B — C
              \        /                                   \
  yours:       D — E —                    yours:            D' — E'
```

Both get the job done, but rebasing gives a **cleaner, linear history**. Many teams prefer this.

---

## Steps

### 1. Switch to your feature branch

```bash
git checkout team1-yourname
```

### 2. Fetch the latest changes from upstream

Pull the latest `main` from the original workshop repo:

```bash
git fetch upstream
```

> If you didn't set up `upstream` in Exercise 2, do it now:
> ```bash
> git remote add upstream https://github.com/Alonzorr10/TUJ-2026-GitHub-Workshop.git
> git fetch upstream
> ```

### 3. Rebase your branch onto the latest main

```bash
git rebase upstream/main
```

If there are **no conflicts**, you'll see something like:

```
Successfully rebased and updated refs/heads/team1-yourname.
```

Skip ahead to step 5.

### 4. If there's a conflict during rebase

If Git finds a conflict, it will pause and show you which file has the problem:

```
CONFLICT (content): Merge conflict in <filename>
error: could not apply <hash>... <commit message>
```

To fix it:

**a)** Open the conflicting file and resolve the conflict (same as Exercise 4 — remove all `<<<<<<<`, `=======`, `>>>>>>>` markers).

**b)** Stage the fixed file:

```bash
git add <filename>
```

**c)** Continue the rebase:

```bash
git rebase --continue
```

**d)** If there are multiple conflicts, repeat a–c for each one.

> **Want to bail out?** Run `git rebase --abort` to undo the entire rebase and go back to how things were before.

### 5. Verify the rebase worked

Check your commit history:

```bash
git log --oneline --graph
```

Your commits should now appear **after** the latest commits from `main`, in a clean straight line — no merge commits.

### 6. Push to update your branch on GitHub

Because rebasing rewrites history, you need to push:

```bash
git push origin team1-yourname
```

---

## Checkpoint

- [ ] I rebased my branch onto the latest `upstream/main`
- [ ] I resolved any conflicts that came up during the rebase
- [ ] `git log --oneline --graph` shows a clean linear history
- [ ] I pushed my updated branch to GitHub

---

## Quick Reference

| Command | What it does |
|---------|-------------|
| `git fetch upstream` | Download the latest changes from the original repo |
| `git rebase upstream/main` | Replay your commits on top of the latest `main` |
| `git rebase --continue` | Continue rebase after fixing a conflict |
| `git rebase --abort` | Cancel the rebase and go back to before |
| `git push --force-with-lease` | Force push safely after rewriting history |

---

## Troubleshooting

**"fatal: 'upstream' does not appear to be a git repository"**
- You haven't added the upstream remote. Run:
  ```bash
  git remote add upstream https://github.com/Alonzorr10/TUJ-2026-GitHub-Workshop.git
  ```

**"You have unstaged changes"**
- Commit or stash your changes first:
  ```bash
  git stash
  git rebase upstream/main
  git stash pop
  ```

**"I'm stuck in rebase with lots of conflicts"**
- Run `git rebase --abort` to start over. Ask for help if needed.

---

**Next up:** [Exercise 6 — Pull Request](../06-pull-request/)
