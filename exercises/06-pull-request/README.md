# Exercise 6 — Pull Request

**Skill:** Opening a pull request, code review, merging

**Time:** ~10 minutes

---

## What is a pull request?

A **pull request** (PR) is how you propose your changes to a project. It says: *"Hey, I made some changes on my branch — can someone review them and merge them in?"*

PRs are the heart of collaboration on GitHub. They let others review your code, leave comments, and approve the changes before they become part of the main project.

---

## Steps

### 1. Go to the original workshop repo on GitHub

Open this link:

```
https://github.com/Alonzorr10/TUJ-2026-GitHub-Workshop
```

### 2. GitHub should show a prompt to create a PR

If you recently pushed your branch, you'll see a yellow banner:

> **"team1-yourname had recent pushes — Compare & pull request"**

Click **Compare & pull request**.

If you don't see the banner:
1. Click the **Pull requests** tab
2. Click **New pull request**
3. Click **"compare across forks"**
4. Set **base repository** to `Alonzorr10/TUJ-2026-GitHub-Workshop` and **base** to `main`
5. Set **head repository** to `YOUR-USERNAME/TUJ-2026-GitHub-Workshop` and **compare** to `team1-yourname`

### 3. Fill in the PR template

A template will appear with checkboxes.

- **Title:** `Add team1 to participants` (use your team name)
- **Description:** Check off the exercises you completed and describe how you resolved your merge conflict

### 4. Double-check your changes

Scroll down to see the **Files changed** tab at the bottom of the PR creation page. Make sure:

- Your team's participant file (`participants/team1.md`) is included
- Your team notes file (`team-projects/team1-notes.md`) has no leftover conflict markers
- All your commits look correct

### 5. Create the pull request

Click the green **Create pull request** button.

### 6. Wait for review

A workshop organizer (or a teammate) will review your PR. They may:

- **Approve it** — your PR gets merged
- **Request changes** — they'll leave comments explaining what to fix

If changes are requested:
1. Read the comments
2. Make the fixes on your branch locally
3. Commit and push — the PR updates automatically

```bash
git checkout team1-yourname
# make your fixes
git add .
git commit -m "Fix review feedback"
git push origin team1-yourname
```

### 7. Celebrate your merged PR

Once approved and merged, your changes are now part of the official workshop repo. You did it!

---

## Checkpoint

- [ ] I opened a pull request from my fork to the original repo
- [ ] The PR title and description are filled in
- [ ] The PR template checklist is complete
- [ ] My team's participant file is included in the PR
- [ ] No conflict markers are left in any files

---

## Quick Reference

| Term | Meaning |
|------|---------|
| **PR (Pull Request)** | A proposal to merge your changes into a project |
| **Base branch** | Where you want your changes to go (usually `main`) |
| **Compare branch** | The branch with your changes (e.g., `team1-yourname`) |
| **Review** | Someone reads your changes and approves or requests fixes |
| **Merge** | Your changes become part of the main project |

---

## Troubleshooting

**"There isn't anything to compare"**
- Make sure you pushed your branch to your fork (`git push origin team1-yourname`).
- Make sure you're comparing across forks (click "compare across forks").

**"This branch has conflicts that must be resolved"**
- Go back to [Exercise 5](../05-rebase-cleanup/) and rebase your branch onto the latest `main`.

**"I can't find the PR template"**
- If it doesn't auto-fill, that's okay — just describe your changes manually.

---

## You're Done! 🎉

You've completed all 6 exercises. Here's what you learned:

| Exercise | Skill |
|----------|-------|
| 1 | Forking a repo on GitHub |
| 2 | Cloning, exploring history, understanding remotes |
| 3 | Creating branches, committing, pushing |
| 4 | Handling merge conflicts like a pro |
| 5 | Rebasing for a clean commit history |
| 6 | Opening pull requests and getting code reviewed |

Make sure you've completed the [requirements in the main README](../../README.md) to be eligible for your gift card!
