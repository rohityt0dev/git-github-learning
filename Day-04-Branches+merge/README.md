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

# 🔀 2. What is Git Merge?

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

# 🛠️ 3. Git Merge Example

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

# 🔀 4. Fast-Forward Merge

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

# 🔀 5. Three-Way Merge

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

# ⚔️ 6. Merge Conflicts

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

# 🛠️ 7. How to Resolve a Merge Conflict

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

# 🔄 8. What is Git Rebase?

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

# 🛠️ 9. Git Rebase Example

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

# ⚔️ 10. Rebase Conflicts

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

# 🆚 11. Git Merge vs Git Rebase

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

# 🚀  Practical Feature Branch Workflow

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

# 🔄  Feature Branch Rebase Workflow

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

```

### Remember:

> 🌿 **Branch = Separate line of development**

> 🔀 **Merge = Combine branches**

> 🔄 **Rebase = Move/replay commits onto a new base**

> ⚔️ **Conflict = Git needs your help to choose the correct changes**

> 🚀 **Pull Request = Review and collaborate before merging**

---
