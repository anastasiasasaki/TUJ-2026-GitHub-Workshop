# Exercise 2 — Clone & Explore

**Skill:** Cloning, `git log`, `git status`, `git branch`

**Time:** ~10 minutes

---

> **Windows users:** Open **Git Bash** for all terminal commands in this workshop.
> It was installed with Git and works just like a Mac/Linux terminal.
> You can find it by searching "Git Bash" in the Start menu.

---

## What is cloning?

**Cloning** downloads a full copy of a remote repository to your computer. This gives you all the files, all the branches, and the entire commit history — everything you need to start working locally.

---

## Steps

### 1. Clone your fork

Open your terminal (Git Bash on Windows, Terminal on Mac) and run:

```bash
git clone https://github.com/YOUR-USERNAME/TUJ-2026-GitHub-Workshop.git
```

> Replace `YOUR-USERNAME` with your actual GitHub username.

Then move into the project folder:

```bash
cd TUJ-2026-GitHub-Workshop
```

### 2. Check the status

```bash
git status
```

You should see something like:

```
On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean
```

This means everything is synced and no files have been changed.

### 3. Look at the commit history

```bash
git log --oneline
```

This shows a short list of past commits. Each line has:
- A **short hash** (like `a1b2c3d`) — a unique ID for the commit
- The **commit message** — what was changed

Try scrolling with the arrow keys. Press **q** to exit.

Want more detail? Try:

```bash
git log --oneline --graph --all
```

This shows branches visually as a tree.

### 4. Check which branch you're on

```bash
git branch
```

You should see:

```
* main
```

The `*` means that's your current branch.

### 5. Check your remote connection

```bash
git remote -v
```

You should see something like:

```
origin  https://github.com/YOUR-USERNAME/TUJ-2026-GitHub-Workshop.git (fetch)
origin  https://github.com/YOUR-USERNAME/TUJ-2026-GitHub-Workshop.git (push)
```

This confirms your local repo is connected to your fork on GitHub.

### 6. Add the original repo as "upstream"

This lets you pull in updates from the original workshop repo later:

```bash
git remote add upstream https://github.com/Alonzorr10/TUJ-2026-GitHub-Workshop.git
```

Verify it was added:

```bash
git remote -v
```

Now you should see both `origin` (your fork) and `upstream` (the original repo).

---

## Checkpoint

- [ ] I cloned my fork and can see the files on my computer
- [ ] `git status` shows "nothing to commit, working tree clean"
- [ ] `git log --oneline` shows past commits
- [ ] `git branch` shows I'm on `main`
- [ ] `git remote -v` shows both `origin` and `upstream`

---

## Quick Reference

| Command | What it does |
|---------|-------------|
| `git clone <url>` | Download a repo to your computer |
| `git status` | Show what's changed since the last commit |
| `git log --oneline` | Show commit history (short format) |
| `git branch` | List branches and show which one you're on |
| `git remote -v` | Show connected remote repositories |

---

## Troubleshooting

**"fatal: repository not found"**
- Double check the URL — make sure it has your GitHub username, not someone else's.

**"Permission denied"**
- Make sure you followed [SETUP.md](../../SETUP.md) to authenticate with GitHub.

---

**Next up:** [Exercise 3 — Branch & Push](../03-branch-and-push/)
