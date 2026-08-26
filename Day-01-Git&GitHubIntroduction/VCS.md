# Version Control

A **Version Control System (VCS)** is software that tracks changes made to files and source code over time.

It keeps a history of changes so developers can:

* Track changes
* Compare different versions
* Restore previous versions
* Collaborate with other developers
* Maintain the history of a project

---

## Types of Version Control Systems

There are three major types of Version Control Systems:

1. **Local Version Control System (LVCS)**
2. **Centralized Version Control System (CVCS)**
3. **Distributed Version Control System (DVCS)**

---

## 1. Local Version Control System (LVCS)

In a Local VCS, different versions of files are stored on the **local computer**.

### How It Works

```text
File
  |
  ▼
Local Database
  |
  ├── Version 1
  ├── Version 2
  └── Version 3 (Latest)
```

### Characteristics

* All versions are stored on a single system.
* No central server is required.
* Can work without a network.
* Suitable for individual developers.
* Collaboration is limited.
* If the local computer fails, there is a risk of losing data.

### Example

* RCS (Revision Control System)

---

# 2. Centralized Version Control System (CVCS)

In a Centralized VCS, there is a **central server** that stores the main repository.

Developers connect to the central server to download files, make changes, and commit their changes back to the server.

### How It Works

```text
                 Central Server
                 (Repository)
                /      |      \
               /       |       \
              ▼        ▼        ▼
        Developer A  Developer B  Developer C
```

Typical operations:

```text
Developer
    |
    | Checkout
    ▼
Central Repository
    |
    | Update
    ▼
Developer
    |
    | Commit
    ▼
Central Repository
```

### Characteristics

* Central server stores the project data.
* Developers need network access to communicate with the server.
* Good collaboration between developers.
* Easy to manage from a central location.
* The central server can become a **single point of failure**.
* If the server is unavailable, developers may not be able to commit or update.

### Examples

* SVN (Subversion)
* CVS
* Perforce

---

# 3. Distributed Version Control System (DVCS)

In a Distributed VCS, every developer has a **complete copy of the repository**, including its history.

Developers can work offline and synchronize their changes with a remote repository when required.

### How It Works

```text
                     Remote Repository
                        (GitHub)
                       /    |    \
                      /     |     \
                     ▼      ▼      ▼
              Developer A Developer B Developer C
                 Local       Local       Local
                 Repo        Repo        Repo
```

Developers can:

```text
Local Repository
       |
       | Push
       ▼
Remote Repository
       |
       | Pull / Fetch
       ▼
Local Repository
```

### Characteristics

* Every developer has a complete repository.
* Developers can work offline.
* Local operations are fast.
* Easy branching and merging.
* Better flexibility and performance.
* No single central server is required for local work.
* More resilient because multiple copies of the repository exist.

### Examples

* Git
* Mercurial
* Bazaar

---

# Comparison: LVCS vs CVCS vs DVCS

| Feature             | Local VCS (LVCS)     | Centralized VCS (CVCS)             | Distributed VCS (DVCS)                        |
| ------------------- | -------------------- | ---------------------------------- | --------------------------------------------- |
| Repository Location | Local machine only   | Central server                     | Every developer's machine + remote repository |
| Working Offline     | Yes                  | No / Limited                       | Yes                                           |
| Performance         | Fast                 | Depends on server/network          | Fast for local operations                     |
| Collaboration       | Poor                 | Good                               | Excellent                                     |
| Data Redundancy     | No                   | Limited                            | Yes                                           |
| Failure Impact      | Affects local system | Server failure can affect everyone | No single point of failure                    |
| Best For            | Individual projects  | Small to medium teams              | Large teams, open source, enterprise          |
| Examples            | RCS                  | SVN, CVS, Perforce                 | Git, Mercurial, Bazaar                        |

---

# When to Use Which?

## Use LVCS When:

* You are working alone.
* You have a small project.
* You want a simple local solution.
* Collaboration is not required.

## Use CVCS When:

* You are working in a team.
* You need a central place to store source code.
* Centralized access control is important.
* Your organization prefers a centralized workflow.

## Use DVCS When:

* You need maximum flexibility and speed.
* You need offline capabilities.
* You are working on large or complex projects.
* You are working on open-source projects.
* You need powerful branching and merging.

---

# Git and DVCS

**Git is a Distributed Version Control System (DVCS).**

In Git, every developer normally has a complete local repository.

```text
                  GitHub
               Remote Repo
                    ▲
                    │ Push
                    │
                    ▼
              Local Repository
                    │
              ┌─────┴─────┐
              │           │
            Commit       Branch
              │           │
              └─────┬─────┘
                    ▼
                 Working
                Directory
```

This allows developers to:

* Commit changes locally
* Create branches
* Merge branches
* Work offline
* Compare versions
* Revert changes
* Push changes to GitHub
* Pull changes from GitHub

---

# Key Takeaways

### LVCS

> Simple and local, but poor for collaboration.

### CVCS

> Uses a central server and provides better collaboration, but the server can become a single point of failure.

### DVCS

> Provides a complete repository to every developer and offers powerful offline work, branching, and merging.

### Most Popular DVCS

**Git** is one of the most widely used distributed version control systems today.



---




# Summary

| VCS Type   | Main Idea                                        |
| ---------- | ------------------------------------------------ |
| **LVCS**   | Versions stored locally                          |
| **CVCS**   | One central repository                           |
| **DVCS**   | Complete repository on every developer's machine |
| **Git**    | Distributed Version Control System               |
| **GitHub** | Remote platform for hosting Git repositories     |

---

## Learning

This topic is part of my **DevOps Learning Journey

**Topic:** Version Control Systems
**Primary Tool:** Git
**Remote Repository:** GitHub

---

