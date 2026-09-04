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
