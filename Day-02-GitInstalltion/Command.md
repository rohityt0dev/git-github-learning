# 🐙 Git Basic Commands

---

# 📚 Git Commands Cheat Sheet

| Command         | Purpose                               |
| --------------- | ------------------------------------- |
| `git --version` | Check Git version                     |
| `git config`    | Configure Git                         |
| `git init`      | Create / initialize a Git repository  |
| `git status`    | Check repository status               |
| `git add`       | Add changes to the staging area       |
| `git commit`    | Save staged changes to the repository |
| `git log`       | View commit history                   |
| `git diff`      | View changes                          |
| `git show`      | View details of a commit              |

---

# 1️⃣ `git --version`

Used to check whether Git is installed and display the installed version.

```bash
git --version
```

Example:

```text
git version 2.43.0
```

---

# 2️⃣ `git config`

Used to configure Git settings such as your username and email.

### Configure Username

```bash
git config --global user.name "Rohit Tambadkar"
```

### Configure Email

```bash
git config --global user.email "your-email@example.com"
```

### View Configuration

```bash
git config --global --list
```

---

# 3️⃣ `git init`

Used to initialize a new Git repository.

```bash
git init
```

Example:

```bash
mkdir my-project
cd my-project
git init
```

Output:

```text
Initialized empty Git repository
```

This creates a hidden `.git` directory.

```text
my-project/
│
├── .git/
├── README.md
└── application files
```

---

# 4️⃣ `git status`

Used to check the current status of your Git repository.

```bash
git status
```

It can show:

* Modified files
* New files
* Deleted files
* Staged files
* Current branch

Example:

```text
On branch main

Changes not staged for commit:
  modified: app.py
```

---

# 5️⃣ `git add`

Used to add changes to the **staging area**.

### Add a specific file

```bash
git add README.md
```

### Add multiple files

```bash
git add file1.txt file2.txt
```

### Add all changes

```bash
git add .
```

Workflow:

```text
Working Directory
       │
       │ git add
       ▼
Staging Area
```

---

# 6️⃣ `git commit`

Used to save staged changes as a commit in the local repository.

```bash
git commit -m "Initial commit"
```

Example:

```bash
git add .
git commit -m "Add README file"
```

A commit creates a snapshot of the staged changes.

Workflow:

```text
Staging Area
       │
       │ git commit
       ▼
Local Repository
```

---

# 7️⃣ `git log`

Used to view the commit history.

```bash
git log
```

For a shorter format:

```bash
git log --oneline
```

Example:

```text
a82f123 Add README
b72d456 Add Dockerfile
c91e234 Initial commit
```

---

# 8️⃣ `git diff`

Used to view changes between different states of your repository.

For example:

```bash
git diff
```

This shows changes that have been made but are **not yet staged**.

Example:

```text
- old line
+ new line
```

You can also compare staged changes:

```bash
git diff --staged
```

---

# 9️⃣ `git show`

Used to display details about a specific commit.

```bash
git show <commit-id>
```

Example:

```bash
git show a82f123
```

It can show:

* Commit ID
* Author
* Date
* Commit message
* Changes introduced by the commit

---