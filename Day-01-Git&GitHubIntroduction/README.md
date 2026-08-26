🐙 Introduction to Git & GitHub

Git and GitHub are two of the most important tools used in modern software development and DevOps. They help developers track code changes, maintain project history, collaborate with other developers, and support automation and CI/CD workflows.

Git = Version Control
GitHub = Hosting + Collaboration

📌 What is Git?

Git is a distributed version control system (DVCS) used to track changes in source code and files.

Git allows developers to:

✅ Track changes to code

✅ Maintain a complete project history

✅ Create and manage branches

✅ Work on multiple features independently

✅ Merge changes from different branches

✅ Return to previous versions when required

✅ Work locally without an internet connection

✅ Collaborate with other developers through remote repositories

✅ Support modern DevOps and CI/CD workflows

Git was created by Linus Torvalds in 2005 for Linux kernel development. The Git history section of the provided PDF explains how Git was created to provide a fast, reliable, and distributed way of managing source code.

📌 What is GitHub?

GitHub is a cloud-based platform built around Git. It provides a place to host Git repositories and collaborate on software projects.

GitHub allows developers and teams to:

📦 Host Git repositories online

👥 Collaborate with other developers

🔀 Create and review Pull Requests

🐛 Manage Issues

📋 Track project work

⚙️ Automate workflows with GitHub Actions

🔐 Manage access and permissions

📚 Maintain project documentation

🌍 Share and showcase projects

The GitHub overview in the provided PDF describes GitHub as a platform for hosting, sharing, and collaborating on code from anywhere.

🆚 Git vs GitHub

Git and GitHub work together, but they are not the same thing.

Git

GitHub

Distributed version control system

Cloud-based development platform

Runs primarily on your local computer

Provides remote repository hosting

Tracks changes in files

Hosts Git repositories online

Creates commits

Stores and shares repositories

Creates and manages branches

Supports Pull Requests and code reviews

Can work without internet for local operations

Internet is normally required for remote collaboration

Command-line tool

Web platform with Git integration

Maintains local project history

Provides collaboration, project management, and automation features

Easy Way to Remember

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

🔄 Git Workflow

The basic Git workflow moves changes through several stages:

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

This workflow is also illustrated in the provided PDF, where the process is presented as:

Work → Stage → Commit → Push → Collaborate

1️⃣ Working Directory

The Working Directory contains the files you are currently creating or modifying.

Example:

my-project/
│
├── app.py
├── index.html
└── README.md

When you create or modify a file, the changes first exist in the Working Directory.

Check the current state:

git status

Example:

modified: app.py

2️⃣ Staging Area

The Staging Area contains changes that you want to include in your next commit.

Stage a specific file:

git add app.py

Stage all changes:

git add .

Workflow:

Working Directory
        │
        │ git add
        ▼
Staging Area

3️⃣ Local Repository

After staging the required changes, create a commit:

git commit -m "Add application code"

A commit is a saved snapshot of the staged changes.

Workflow:

Staging Area
      │
      │ git commit
      ▼
Local Repository

4️⃣ Remote Repository

A remote repository is a repository hosted on a remote platform such as GitHub.

Push your local commits to GitHub:

git push

Workflow:

Local Repository
      │
      │ git push
      ▼
GitHub Remote Repository

🌐 Git and GitHub Together

A typical development workflow looks like this:

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

Git provides the version-control engine, while GitHub provides a platform for collaboration and remote development.

⭐ Why Git and GitHub Are Important for DevOps

Git is a fundamental tool in DevOps because application source code and infrastructure configuration are commonly managed in repositories.

Git and GitHub can be used with:

Jenkins

GitHub Actions

Docker

Kubernetes

Terraform

Ansible

Maven

AWS

CI/CD pipelines

For example:

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

This makes Git and GitHub important foundations for learning DevOps.

🎯 Key Takeaways

Git
│
├── Track Changes
├── Create Commits
├── Create Branches
├── Merge Changes
├── Maintain History
└── Work with Remote Repositories

GitHub
│
├── Host Repositories
├── Collaborate
├── Pull Requests
├── Code Reviews
├── Issue Tracking
└── Automation with GitHub Actions

Remember

Git = Track, Version, Branch, Commit, and Merge Code

GitHub = Host, Share, Review, and Collaborate on Git Repositories

🏁 Conclusion

Git is a distributed version control system that helps developers safely manage and track changes to their projects. GitHub builds on Git by providing online repository hosting and collaboration features.

Understanding the basic flow:

Working Directory
       ↓
Staging Area
       ↓
Local Repository
       ↓
Remote Repository (GitHub)

is the foundation for learning advanced Git and GitHub concepts such as:

Branching strategies

Merge conflicts

Pull Requests

Rebasing

Git hooks

GitHub Actions

CI/CD pipelines

Collaborative development

🚀 Learn Git first, then use GitHub to collaborate and automate your development workflow.