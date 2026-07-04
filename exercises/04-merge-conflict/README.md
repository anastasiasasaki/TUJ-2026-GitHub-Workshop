# Exercise 4 — Merge Conflict

**Skill:** Pulling changes, resolving merge conflicts

**Time:** ~15 minutes (pair exercise)

---

> **Windows users:** Use **Git Bash** for all commands.

---

## What is a merge conflict?

A **merge conflict** happens when two people edit the **same lines** in the **same file**. Git doesn't know which version to keep, so it asks you to decide.

This sounds scary but it's completely normal — and after this exercise you'll know exactly how to handle it.

---

## Setup — Find Your Team

You'll be assigned to a team. Each team has a shared file:

```
team-projects/team1-notes.md
team-projects/team2-notes.md
...
```

Find your team number and your partner. You'll both be editing the same file.

---

## Steps

### Part A — Both Teammates Edit the Same File

**Both teammates do these steps independently on their own computers.**

#### 1. Make sure you're on your branch

```bash
git checkout team1-yourname
```

#### 2. Open your team's notes file

Open `team-projects/teamX-notes.md` (replace X with your team number) in your text editor.

#### 3. Fill in the Team Members table

Add your name and GitHub handle to the table.

#### 4. Edit the Conflict Zone

Find the section that says:

```
_(Edit this line on your branch — your teammate will write something different)_
```

**Replace it** with your answer to the question. Write something different from your teammate — that's the whole point!

#### 5. Save, stage, and commit

```bash
git add team-projects/teamX-notes.md
git commit -m "Add my answer to team X notes"
```

#### 6. Push your branch

```bash
git push origin team1-yourname
```

---

### Part B — Trigger the Conflict

**One teammate goes first (Person A), then the other (Person B).**

#### Person A: Merge your branch into main on your fork

```bash
git checkout main
git merge team1-yourname
git push origin main
```

This should work fine — no conflict yet.

#### Person B: Pull the updated main and merge

```bash
git checkout main
git pull origin main
git checkout team1-yourname
git merge main
```

**You should see a conflict message** like:

```
Auto-merging team-projects/teamX-notes.md
CONFLICT (content): Merge conflict in team-projects/teamX-notes.md
Automatic merge failed; fix conflicts and then commit the result.
```

---

### Part C — Resolve the Conflict

#### 1. Open the conflicting file

Open `team-projects/teamX-notes.md` in your text editor. You'll see conflict markers like this:

```
<<<<<<< HEAD
Your version of the text
=======
Your teammate's version of the text
>>>>>>> main
```

Here's what the markers mean:

| Marker | Meaning |
|--------|---------|
| `<<<<<<< HEAD` | Start of **your** changes |
| `=======` | Divider between the two versions |
| `>>>>>>> main` | End of the **incoming** changes |

#### 2. Fix it manually

Decide what to keep. You can:
- **Keep yours** — delete the teammate's version and all markers
- **Keep theirs** — delete your version and all markers
- **Keep both** — combine the two answers and delete all markers

**Important:** Delete ALL conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) — the file should look normal when you're done.

#### 3. Document your resolution

In the **Resolution Notes** section at the bottom of the file, write a one-sentence summary of how you resolved the conflict:

```markdown
## ✅ Resolution Notes

We combined both answers to show two different perspectives.
```

#### 4. Stage and commit the resolved file

```bash
git add team-projects/teamX-notes.md
git commit -m "Resolve merge conflict in team X notes"
```

> Git knows this is a merge commit — it will include both sets of changes.

#### 5. Push the result

```bash
git push origin team1-yourname
```

---

## Checkpoint

- [ ] Both teammates edited the same file on different branches
- [ ] A merge conflict was triggered
- [ ] I resolved the conflict by editing the file and removing all conflict markers
- [ ] I wrote a resolution note in the file
- [ ] The resolved file is committed and pushed

---

## Quick Reference

| Command | What it does |
|---------|-------------|
| `git merge <branch>` | Merge another branch into your current branch |
| `git pull origin main` | Fetch and merge the latest `main` from GitHub |
| `git diff` | Show what's different in your files |
| `git add <file>` | Stage a resolved file |
| `git commit` | Commit after resolving (no `-m` needed for merge commits) |

---

## Troubleshooting

**"I don't see conflict markers"**
- Both teammates may have edited different lines. Try editing the **exact same line** and repeat the process.

**"I messed up the merge and want to start over"**
- Run `git merge --abort` to undo the merge and go back to where you were before.

**"I accidentally committed the conflict markers"**
- That's okay! Just open the file, remove the markers, then `git add` and `git commit` again.

---

**Next up:** [Exercise 5 — Rebase Cleanup](../05-rebase-cleanup/)
