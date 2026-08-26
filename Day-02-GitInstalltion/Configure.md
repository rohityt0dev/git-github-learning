#  Configure Git

After installing Git, configure your name and email.

## Set Your Name

Run:

```bash
git config --global user.name "Your Name"
```

Example:

```bash
git config --global user.name "Rohit Tambadkar"
```

## Set Your Email

Use the email address associated with your GitHub account:

```bash
git config --global user.email "your-email@example.com"
```

Example:

```bash
git config --global user.email "your-email@example.com"
```

> 💡 You can use a GitHub-provided `noreply` email if you prefer to keep your personal email private.

---

#  Verify Git Configuration

Run:

```bash
git config --global --list
```

You should see something similar to:

```text
user.name=Rohit Tambadkar
user.email=your-email@example.com
```

You can also check the values individually:

```bash
git config --global user.name
git config --global user.email
```

---

#  Test Git

Create a test directory:

```bash
mkdir git-test
```

Move into the directory:

```bash
cd git-test
```

Initialize a Git repository:

```bash
git init
```

You should see a message similar to:

```text
Initialized empty Git repository
```

Check the repository status:

```bash
git status
```

You should see something similar to:

```text
On branch main

No commits yet
```

Your Git repository is now initialized successfully. ✅

---

# 🔄 Basic Git Workflow

The basic Git and GitHub workflow is:

```text
Create Project
     │
     ▼
git init
     │
     ▼
Create / Modify Files
     │
     ▼
git status
     │
     ▼
git add .
     │
     ▼
git commit
     │
     ▼
Connect Remote Repository
     │
     ▼
git push
     │
     ▼
GitHub
```

## Common Git Commands

```bash
git init
git status
git add .
git commit -m "Initial commit"
git branch
git log
git pull
git push
```

---

# 📚 Important Git Concepts

| Term         | Meaning                                                    |
| ------------ | ---------------------------------------------------------- |
| Git          | Distributed version control system                         |
| Repository   | Project tracked by Git                                     |
| Commit       | Saved snapshot of changes                                  |
| Branch       | Independent line of development                            |
| Remote       | Remote repository such as GitHub                           |
| Clone        | Creates a local copy of an existing repository             |
| Push         | Uploads local commits to a remote repository               |
| Pull         | Downloads and integrates changes from a remote repository  |
| Staging Area | Area where changes are prepared before committing          |
| GitHub       | Platform for hosting and collaborating on Git repositories |

---

# 🏁 Conclusion

Installing and configuring Git on Windows is an important first step toward using GitHub and implementing version control in a DevOps workflow.

The complete basic process is:

```text
Download Git
     │
     ▼
Install Git
     │
     ▼
Verify Installation
     │
     ▼
Configure Name & Email
     │
     ▼
Initialize Repository
     │
     ▼
Create / Modify Files
     │
     ▼
Stage Changes
     │
     ▼
Commit Changes
     │
     ▼
Push to GitHub
```

### Remember

> **Git = Version Control System**

> **GitHub = Platform for Hosting and Collaborating on Git Repositories**

---
