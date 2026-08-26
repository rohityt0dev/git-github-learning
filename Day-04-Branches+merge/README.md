# 🌿 Git Branching, Merging & Rebasing

Git branches are one of the most important concepts in Git and are heavily used in modern software development and DevOps.

Branches allow developers to work on different features, bug fixes, and experiments without directly changing the main production code.

This README covers:

* 🌿 Git Branching
* 🔀 Git Merging
* 🔄 Git Rebasing
* ⚔️ Merge Conflicts
* 🆚 Merge vs Rebase
* 🚀 Practical Workflow
* 💡 Best Practices

---

# 🌿 1. What is a Git Branch?

A **branch** is a movable pointer to a commit.

Branches allow developers to work independently without affecting the main branch.

Example:

```text
                feature
                   │
                   ▼
A ─── B ─── C ─── D
                   │
                 main
```

A common repository structure is:

```text
main
│
├── develop
│
├── feature/login
│
├── feature/payment
│
└── bugfix/navbar
```

---

# 🧠 Why Do We Use Branches?

Branches are useful for:

* Developing new features
* Fixing bugs
* Testing experimental changes
* Working with multiple developers
* Protecting production code
* Supporting CI/CD workflows

For example:

```text
main
 │
 ├── feature/login
 │
 ├── feature/payment
 │
 └── bugfix/login-error
```

Each developer can work independently.

---

# 🛠️ 2. Basic Branch Commands

## Check Current Branch

```bash
git branch
```

Example:

```text
* main
  feature/login
  feature/payment
```

The `*` indicates the current branch.

---

## Create a Branch

```bash
git branch feature/login
```

This creates a new branch but does not switch to it.

---

## Switch to a Branch

```bash
git switch feature/login
```

Older Git command:

```bash
git checkout feature/login
```

---

## Create and Switch to a Branch

Recommended:

```bash
git switch -c feature/login
```

Older syntax:

```bash
git checkout -b feature/login
```

---

## Delete a Branch

```bash
git branch -d feature/login
```

Force delete:

```bash
git branch -D feature/login
```

⚠️ `-D` should be used carefully because it can delete a branch containing unmerged changes.

---

# 🌐 3. Remote Branches

To see remote branches:

```bash
git branch -r
```

To see local and remote branches:

```bash
git branch -a
```

Example:

```text
* main
  feature/login
  remotes/origin/main
  remotes/origin/feature/login
```

---

# 📤 Push a New Branch to GitHub

Create a branch:

```bash
git switch -c feature/login
```

Make changes and commit:

```bash
git add .
git commit -m "Add login feature"
```

Push the branch:

```bash
git push -u origin feature/login
```

The `-u` option establishes the upstream relationship between the local and remote branch.

After that, you can usually use:

```bash
git push
```

---

# 🔀 4. What is Git Merge?

**Git merge** combines changes from one branch into another branch.

Example:

```text
Before Merge:

main
A ─── B ─── C

feature
       └── D ─── E
```

After merging:

```text
                 D ─── E
                /       \
A ─── B ─── C ─────────── M
```

`M` represents the merge commit.

---

# 🛠️ 5. Git Merge Example

Suppose you have:

```text
main
feature/login
```

First switch to `main`:

```bash
git switch main
```

Update the main branch:

```bash
git pull
```

Merge the feature branch:

```bash
git merge feature/login
```

Push the result:

```bash
git push
```

Complete workflow:

```bash
git switch main
git pull
git merge feature/login
git push
```

---

# 🔀 6. Fast-Forward Merge

Sometimes Git can merge without creating an additional merge commit.

Example:

```text
A ─── B ─── C
           │
         feature
```

If `main` has not changed, Git can simply move the main pointer forward:

```text
A ─── B ─── C
           │
           ├── main
           └── feature
```

This is called a **Fast-Forward Merge**.

---

# 🔀 7. Three-Way Merge

When both branches have new commits, Git usually performs a three-way merge.

Before:

```text
        D ─── E
       /
A ─── B ─── C
```

After:

```text
        D ─── E
       /       \
A ─── B ─── C ── M
```

`M` is the merge commit.

---

# ⚔️ 8. Merge Conflicts

A merge conflict happens when Git cannot automatically determine which changes should be kept.

Example:

```text
<<<<<<< HEAD
Hello from main
=======
Hello from feature
>>>>>>> feature/login
```

Git is asking you to choose the correct version.

---

# 🛠️ 9. How to Resolve a Merge Conflict

### Step 1: Check the conflict

```bash
git status
```

### Step 2: Open the conflicted file

You may see:

```text
<<<<<<< HEAD
Hello from main
=======
Hello from feature
>>>>>>> feature/login
```

### Step 3: Edit the file

Keep the desired content and remove:

```text
<<<<<<< HEAD
=======
>>>>>>> feature/login
```

### Step 4: Stage the resolved file

```bash
git add filename
```

### Step 5: Complete the merge

```bash
git commit
```

Or, depending on Git's state:

```bash
git merge --continue
```

---

# 🔄 10. What is Git Rebase?

**Git rebase** moves or replays your commits on top of another branch.

Instead of creating a merge commit, rebase creates a cleaner, linear history.

Example:

### Before Rebase

```text
        D ─── E
       /
A ─── B ─── C
```

After rebase:

```text
A ─── B ─── C ─── D' ─── E'
```

The commits `D` and `E` are replayed as new commits `D'` and `E'`.

---

# 🛠️ 11. Git Rebase Example

Suppose you have:

```text
main
feature/login
```

Switch to your feature branch:

```bash
git switch feature/login
```

Update your local main branch:

```bash
git switch main
git pull
```

Return to your feature branch:

```bash
git switch feature/login
```

Rebase:

```bash
git rebase main
```

Now your feature commits are based on the latest `main`.

---

# ⚔️ 12. Rebase Conflicts

Rebase can also produce conflicts.

Check the status:

```bash
git status
```

Fix the conflicted file.

Then:

```bash
git add filename
```

Continue the rebase:

```bash
git rebase --continue
```

If another conflict appears, repeat the process.

---

# ❌ Cancel a Rebase

If you want to stop the rebase:

```bash
git rebase --abort
```

This returns the branch to its previous state.

---

# ❌ Cancel a Merge

If a merge is currently in progress and you want to cancel it:

```bash
git merge --abort
```

---

# 🆚 13. Git Merge vs Git Rebase

| Git Merge                         | Git Rebase                                  |
| --------------------------------- | ------------------------------------------- |
| Combines two branches             | Replays commits on another base             |
| Can create merge commits          | Usually creates a linear history            |
| Preserves branch history          | Rewrites commit history                     |
| Safer for shared branches         | Should be used carefully on shared branches |
| Good for preserving exact history | Good for keeping history clean              |
| Easy to understand                | Requires more understanding                 |

---

# 📊 Visual Comparison

## Merge

```text
        D ─── E
       /       \
A ─── B ─── C ── M
```

Merge creates a separate merge path.

## Rebase

```text
A ─── B ─── C ─── D' ─── E'
```

Rebase creates a linear history.

---

# ⚠️ Important Rebase Rule

> **Never rebase commits that other developers are already depending on unless your team explicitly agrees to it.**

Why?

Because rebase changes commit history.

For example:

```text
Original:

A ─── B ─── C
```

After rebase:

```text
A ─── B ─── C'
```

`C` and `C'` have different commit identities.

This can cause problems for other developers who already pulled the original commits.

---

# 🔥 14. Interactive Rebase

Interactive rebase allows you to modify commit history.

Example:

```bash
git rebase -i HEAD~3
```

This allows you to:

* Reorder commits
* Squash commits
* Edit commit messages
* Remove commits
* Modify commits

Example:

```text
pick abc123 Add login page
pick def456 Fix login button
pick ghi789 Fix typo
```

You could squash them into fewer commits.

---

# 🧹 15. Squashing Commits

Suppose you have:

```text
A ─── B ─── C ─── D
```

Where:

```text
B = Add login
C = Fix login
D = Fix login typo
```

You can combine them using:

```bash
git rebase -i HEAD~3
```

Then change:

```text
pick B Add login
pick C Fix login
pick D Fix login typo
```

to:

```text
pick B Add login
squash C Fix login
squash D Fix login typo
```

Result:

```text
A ─── B'
```

This creates a cleaner history.

---

# 🚀 16. Practical Feature Branch Workflow

A common DevOps development workflow:

```text
                 GitHub
                    │
                    ▼
                  main
                    │
                    │
              Create Branch
                    │
                    ▼
             feature/login
                    │
              Develop Code
                    │
                    ▼
                  Commit
                    │
                    ▼
                Push GitHub
                    │
                    ▼
              Pull Request
                    │
                    ▼
               Code Review
                    │
                    ▼
             Merge into main
```

Commands:

```bash
git switch main
git pull

git switch -c feature/login

# Make changes

git add .
git commit -m "Add login feature"

git push -u origin feature/login
```

Then create a Pull Request on GitHub.

---

# 🔄 17. Feature Branch Rebase Workflow

Before opening or updating a Pull Request:

```bash
git switch main
git pull

git switch feature/login
git rebase main
```

If there are conflicts:

```bash
git status
```

Fix files, then:

```bash
git add .
git rebase --continue
```

After a successful rebase, if the branch was already pushed:

```bash
git push --force-with-lease
```

### Why `--force-with-lease`?

It is safer than:

```bash
git push --force
```

because Git checks whether the remote branch changed unexpectedly.

---

# 🌳 18. Recommended Branch Structure

A simple project can use:

```text
main
│
├── feature/login
├── feature/payment
├── feature/dashboard
└── bugfix/login-error
```

For larger teams, a more structured strategy might include:

```text
main
│
├── develop
│   │
│   ├── feature/login
│   ├── feature/payment
│   └── feature/dashboard
│
└── release
```

The exact branching strategy depends on the team's development and deployment process.

---

# 🛡️ 19. Git Branch Best Practices

### ✅ Use meaningful branch names

Good:

```text
feature/login
feature/payment-api
bugfix/navbar
hotfix/production-error
```

Avoid:

```text
test
abc
mybranch
new
```

### ✅ Keep branches focused

A feature branch should generally contain changes related to one feature or task.

### ✅ Pull latest changes regularly

```bash
git pull
```

or update your branch with:

```bash
git fetch origin
```

### ✅ Write meaningful commit messages

Good:

```bash
git commit -m "Add user login validation"
```

Bad:

```bash
git commit -m "changes"
```

### ✅ Protect the main branch

Teams commonly use:

* Pull Requests
* Code Reviews
* Required CI checks
* Branch protection rules

---

# 🧠 20. Important Git Commands

| Command                       | Purpose                             |
| ----------------------------- | ----------------------------------- |
| `git branch`                  | List branches                       |
| `git branch name`             | Create branch                       |
| `git switch name`             | Switch branch                       |
| `git switch -c name`          | Create and switch branch            |
| `git branch -d name`          | Delete branch                       |
| `git merge branch`            | Merge branch                        |
| `git rebase branch`           | Rebase current branch               |
| `git rebase -i HEAD~N`        | Interactive rebase                  |
| `git merge --abort`           | Cancel merge                        |
| `git rebase --abort`          | Cancel rebase                       |
| `git rebase --continue`       | Continue rebase                     |
| `git push -u origin branch`   | Push new branch                     |
| `git push --force-with-lease` | Safely update rebased remote branch |

---

# 🎯 Interview Questions

## 1. What is a Git branch?

A Git branch is a movable pointer to a commit that allows developers to work independently on different features or fixes.

---

## 2. What is Git merge?

Git merge combines the changes from one branch into another branch.

---

## 3. What is Git rebase?

Git rebase moves or replays commits onto a new base commit, usually creating a cleaner and more linear project history.

---

## 4. What is the difference between merge and rebase?

**Merge** combines histories and may create a merge commit.

**Rebase** rewrites the commit history by replaying commits on top of another branch.

---

## 5. What is a merge conflict?

A merge conflict occurs when Git cannot automatically combine changes from different branches.

---

## 6. How do you resolve a merge conflict?

```text
1. Check git status
2. Open the conflicted file
3. Resolve the conflicting changes
4. Remove conflict markers
5. git add
6. Complete the merge
```

---

## 7. What is interactive rebase?

Interactive rebase allows you to modify commit history, such as:

* Squashing commits
* Reordering commits
* Editing commit messages
* Removing commits

Command:

```bash
git rebase -i HEAD~3
```

---

## 8. Why should you avoid rebasing shared branches?

Because rebase rewrites commit history and can cause problems for developers who already have the original commits.

---

# 🚀 Final Summary

```text
Git Branch
    │
    ├── Isolated Development
    │
    ▼
Feature Branch
    │
    ├── git add
    ├── git commit
    └── git push
    │
    ▼
GitHub Pull Request
    │
    ├── Code Review
    ├── CI/CD
    └── Testing
    │
    ▼
Main Branch
```

### Remember:

> 🌿 **Branch = Separate line of development**

> 🔀 **Merge = Combine branches**

> 🔄 **Rebase = Move/replay commits onto a new base**

> ⚔️ **Conflict = Git needs your help to choose the correct changes**

> 🚀 **Pull Request = Review and collaborate before merging**

---

## 📚 Next Git Topics

After Branching, Merging, and Rebasing, learn:

1. Git Merge Conflicts — Hands-on Practice
2. Git Reset vs Revert
3. Git Fetch vs Pull
4. Git Stash
5. Git Cherry-Pick
6. Git Tags
7. Git Log and Git Diff
8. GitHub Pull Requests
9. GitHub Actions
10. Git + Jenkins CI/CD
