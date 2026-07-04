# Exercise 3 — Branch & Push

**Skill:** Creating branches, committing changes, pushing to GitHub

**Time:** ~10 minutes

---

> **Windows users:** Use **Git Bash** for all commands.

---

## What are branches?

A **branch** is like a parallel timeline for your code. You can make changes on a branch without affecting `main`. When you're happy with your work, you merge it back.

This is how teams work on features, fixes, and experiments without stepping on each other's toes.

---

## Steps

### 1. Make sure you're on `main` and up to date

```bash
cd TUJ-2026-GitHub-Workshop
git checkout main
git pull origin main
```

### 2. Create a new branch

Each teammate creates their **own branch** using this format: `team1-yourname`

```bash
git checkout -b team1-yourname
```

> Replace `team1` with your team name and `yourname` with your name (lowercase, no spaces).
> Examples: `git checkout -b team1-sakura`, `git checkout -b team3-alex`

Verify you're on the new branch:

```bash
git branch
```

You should see your new branch with a `*` next to it.

> **Each teammate makes their own branch.** This is important — it lets you practice merging and resolving conflicts later.

### 3. Create your team's participant file

Create a new Markdown file in the `participants/` folder named after your team:

**Mac / Git Bash:**
```bash
touch participants/team1.md
```

> Replace `team1` with your team name.
> Example: `participants/team3.md`

Now open that file in your text editor and paste this template:

```markdown
# Hi, we're Team 1! 👋

## Team Members

| Name | GitHub |
|------|--------|
| Member A | @github-handle |
| Member B | @github-handle |

**Fun fact about our team:** <one sentence>
**Why we joined the Coding Club Github Workshop Event:** <one sentence>

## What we want to learn
- <goal 1>
- <goal 2>
```

Fill it in with your team's info and save the file.

### 4. Stage your changes

```bash
git add participants/team1.md
```

Check that it worked:

```bash
git status
```

You should see your file listed under "Changes to be committed" in green.

### 5. Commit your changes

```bash
git commit -m "Add team1 to participants"
```

> Write a short, descriptive commit message. Example:
> `git commit -m "Add team3 to participants"`

### 6. Push your branch to GitHub

```bash
git push origin team1-yourname
```

> Use the same branch name you created in step 2.

### 7. Verify on GitHub

Open your fork in a browser:

```
https://github.com/YOUR-USERNAME/TUJ-2026-GitHub-Workshop
```

- Click the **branch dropdown** (it says "main") — you should see your new branch
- Switch to your branch and check that your participant file is there

---

## Checkpoint

- [ ] I created my own branch (not working directly on `main`)
- [ ] I added my team's participant file in `participants/`
- [ ] I committed with a descriptive message
- [ ] I pushed my branch to GitHub
- [ ] I can see my branch and file on GitHub

---

## Quick Reference

| Command | What it does |
|---------|-------------|
| `git checkout -b <name>` | Create and switch to a new branch |
| `git add <file>` | Stage a file for committing |
| `git status` | See what's staged, modified, or untracked |
| `git commit -m "message"` | Save staged changes with a message |
| `git push origin <branch>` | Upload your branch to GitHub |

---

## Troubleshooting

**"fatal: not a git repository"**
- Make sure you're inside the `TUJ-2026-GitHub-Workshop` folder.

**"error: failed to push some refs"**
- Make sure you're pushing to the correct branch name: `git push origin team1-yourname`

---

**Next up:** [Exercise 4 — Merge Conflict](../04-merge-conflict/)
