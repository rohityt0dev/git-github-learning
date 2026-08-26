# 🐙 Introduction to Git & GitHub

Git and GitHub are two of the most important tools used in modern software development and DevOps.

They help developers:

* Track code changes
* Maintain project history
* Collaborate with other developers
* Manage branches
* Review code
* Support CI/CD automation

> **Git = Version Control**
> **GitHub = Hosting + Collaboration**

---

## 📌 What is Git?

**Git** is a distributed version control system (DVCS) used to track changes in source code and files.

Git allows developers to:

* ✅ Track changes to code
* ✅ Maintain complete project history
* ✅ Create and manage branches
* ✅ Work on multiple features independently
* ✅ Merge changes from different branches
* ✅ Return to previous versions
* ✅ Work locally without an internet connection
* ✅ Collaborate through remote repositories
* ✅ Support DevOps and CI/CD workflows

Git was created by **Linus Torvalds in 2005** for Linux kernel development.

---

## 📌 What is GitHub?

**GitHub** is a cloud-based development platform built around Git.

It provides a place to host Git repositories and collaborate on software projects.

GitHub allows developers and teams to:

* 📦 Host Git repositories online
* 👥 Collaborate with developers
* 🔀 Create and review Pull Requests
* 🐛 Manage Issues
* 📋 Track project work
* ⚙️ Automate workflows using GitHub Actions
* 🔐 Manage access and permissions
* 📚 Maintain project documentation
* 🌍 Share and showcase projects

---

# 🆚 Git vs GitHub

| Git                                            | GitHub                                                 |
| ---------------------------------------------- | ------------------------------------------------------ |
| Distributed version control system             | Cloud-based development platform                       |
| Runs primarily on your local computer          | Provides remote repository hosting                     |
| Tracks changes in files                        | Hosts Git repositories online                          |
| Creates commits                                | Stores and shares repositories                         |
| Creates and manages branches                   | Supports Pull Requests and code reviews                |
| Can work without internet for local operations | Internet is normally required for remote collaboration |
| Command-line tool                              | Web platform with Git integration                      |
| Maintains local project history                | Provides collaboration and automation features         |

### Easy Way to Remember

```text
Git
│
└── Version Control
    └── Tracks and manages code changes locally


GitHub
│
└── Collaboration Platform
    ├── Hosts Git repositories
    ├── Pull Requests
    ├── Issues
    ├── Code Reviews
    └── GitHub Actions
```

---

# 🔄 Git Workflow

The basic Git workflow moves changes through several stages:

```text
Create / Modify Files
        │
        ▼
Working Directory
        │
     git add
        │
        ▼
Staging Area
        │
   git commit
        │
        ▼
Local Repository
        │
    git push
        │
        ▼
Remote Repository
      (GitHub)
```

The simple workflow is:

> **Work → Stage → Commit → Push → Collaborate**

---

# 1️⃣ Working Directory

The **Working Directory** contains the files you are currently creating or modifying.

Example:

```text
my-project/
│
├── app.py
├── index.html
└── README.md
```

When you create or modify a file, the changes first exist in the Working Directory.

### Check Current Status

```bash
git status
```

Example:

```text
modified: app.py
```

---

# 2️⃣ Staging Area

The **Staging Area** contains changes that you want to include in your next commit.

### Stage a Specific File

```bash
git add app.py
```

### Stage All Changes

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

# 3️⃣ Local Repository

After staging the required changes, create a commit:

```bash
git commit -m "Add application code"
```

A **commit** is a saved snapshot of the staged changes.

Workflow:

```text
Staging Area
      │
      │ git commit
      ▼
Local Repository
```

---

# 4️⃣ Remote Repository

A **remote repository** is a Git repository hosted on a remote platform such as GitHub.

Push your local commits to GitHub:

```bash
git push
```

Workflow:

```text
Local Repository
      │
      │ git push
      ▼
GitHub Remote Repository
```

---

# 🌐 Git and GitHub Together

A typical development workflow looks like this:

```text
Developer
    │
    ▼
Create / Modify Code
    │
    ▼
Working Directory
    │
    │ git add
    ▼
Staging Area
    │
    │ git commit
    ▼
Local Git Repository
    │
    │ git push
    ▼
GitHub Repository
    │
    ├── Pull Request
    ├── Code Review
    ├── Issues
    ├── Collaboration
    └── GitHub Actions / CI-CD
```

Git provides the **version-control engine**, while GitHub provides a platform for **collaboration and remote development**.

---

# ⭐ Why Git and GitHub Are Important for DevOps

Git is a fundamental tool in DevOps because application source code and infrastructure configuration are commonly managed in repositories.

Git and GitHub can be used with:

* Jenkins
* GitHub Actions
* Docker
* Kubernetes
* Terraform
* Ansible
* Maven
* AWS
* CI/CD pipelines

### Example DevOps Workflow

```text
Developer
    │
    │ git push
    ▼
GitHub
    │
    │ Trigger
    ▼
CI/CD Pipeline
    │
    ├── Build
    ├── Test
    ├── Security Scan
    ├── Docker Build
    └── Deploy
```

This makes Git and GitHub important foundations for learning DevOps.

---

# 🎯 Key Git Concepts

```text
Git
│
├── Track Changes
├── Create Commits
├── Create Branches
├── Merge Changes
├── Maintain History
└── Work with Remote Repositories
```

# 🎯 Key GitHub Concepts

```text
GitHub
│
├── Host Repositories
├── Collaborate
├── Pull Requests
├── Code Reviews
├── Issue Tracking
└── Automation with GitHub Actions
```

---

# 🧠 Remember

### Git

> **Track, Version, Branch, Commit, and Merge Code**

### GitHub

> **Host, Share, Review, and Collaborate on Git Repositories**

---

# 🏁 Conclusion

Git is a distributed version control system that helps developers safely manage and track changes to their projects.

GitHub builds on Git by providing online repository hosting and collaboration features.

The fundamental Git workflow is:

```text
Working Directory
       ↓
Staging Area
       ↓
Local Repository
       ↓
Remote Repository (GitHub)
```

Understanding this basic flow provides the foundation for advanced Git and GitHub concepts such as:

* Branching strategies
* Merge conflicts
* Pull Requests
* Rebasing
* Git hooks
* GitHub Actions
* CI/CD pipelines
* Collaborative development

---

# 🚀 What's Next?

After understanding Git fundamentals, continue with:

1. Git Installation & Configuration
2. `git init`
3. `git clone`
4. `git status`
5. `git add`
6. `git commit`
7. `git log`
8. `git branch`
9. `git checkout` / `git switch`
10. `git merge`
11. `git pull`
12. `git push`
13. Merge Conflicts
14. GitHub Pull Requests
15. GitHub Actions
16. Git + CI/CD

> 🚀 **Learn Git first, then use GitHub to collaborate and automate your development workflow.**
