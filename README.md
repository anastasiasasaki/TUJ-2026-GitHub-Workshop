# 🌸 TUJ Coding Club — Git & GitHub Workshop

Welcome! This is the official practice repository for the **TUJ Coding Club Git & GitHub Workshop**.

By the end of this workshop you'll know how to:
- Fork a repo (repository)
- Clone a repo, explore its history, and understand its structure
- Create branches and push your changes
- Handle merge conflicts without panicking
- Rebase your branch to clean up history
- Open a pull request and get it reviewed and merged

---

## 🗺️ Workshop Flow

| # | Exercise | Skill Covered |
|---|----------|---------------|
| 1 | [Fork Repository](./exercises/01-fork-repository) | Fork repository using GitHub
| 2 | [Clone & Explore](./exercises/02-clone-explore/) | Cloning, `git log`, `git status`, `git branch` |
| 3 | [Branch & Push](./exercises/03-branch-and-push/) | Branching, committing, pushing |
| 4 | [Merge Conflict](./exercises/04-merge-conflict/) | Pulling, resolving conflicts |
| 5 | [Rebase Cleanup](./exercises/05-rebase-cleanup/) | Rebasing onto `main`, clean history |
| 6 | [Pull Request](./exercises/06-pull-request/) | Opening PRs, code review, merging |

Work through them **in order** — each one builds on the last.

---

## ✅ Completion Requirements (for your gift card 🎁)

To be eligible for the ¥1,000 Amazon gift card, you must complete **all three** of the following:

- [ ] A merged PR that adds your file to `participants/`
- [ ] A documented merge conflict resolution in Exercise 4
- [ ] A successful rebase in Exercise 5

Completion is verified through your commit and PR history — no extra form needed.

---

## 🧭 Getting Started

**Step 1 — Set up your environment**
→ Follow [SETUP.md](./SETUP.md) if you haven't installed Git or authenticated yet.

**Step 2 — Clone this repo**
```bash
git clone https://github.com/Alonzorr10/TUJ-2026-GitHub-Workshop.git
cd TUJ-2026-GitHub-Workshop
```

**Step 3 — Check out the first exercise**
```bash
cd exercises/01-fork-repository
cat README.md
```

---

## 📁 Repo Structure

```
TUJ-2026-GitHub-Workshop/
├── README.md                  ← you are here
├── SETUP.md                   ← install guide
├── leaderboard.md             ← updates as PRs merge
├── participants/              ← add your own file here
├── team-projects/             ← one file per team (conflict exercise)
├── exercises/
│   ├── 01-fork-repository/
│   ├── 02-clone-explore/
│   ├── 03-branch-and-push/
│   ├── 04-merge-conflict/
│   ├── 05-rebase-cleanup/
│   └── 06-pull-request/
└── .github/
    └── PULL_REQUEST_TEMPLATE.md
```

---

## 🙋 Questions?

Raise your hand during the workshop, or open a GitHub Issue using the **Question** template.

Happy committing! 🚀
