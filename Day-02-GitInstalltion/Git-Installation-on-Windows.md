# 🐙 Git Installation on Windows

## 📌 Introduction

**Git** is a distributed version control system used to track changes in source code and collaborate with other developers.

Git is commonly used with platforms such as:

* GitHub
* GitLab
* Bitbucket

This guide explains how to **download, install, and verify Git on Windows**.

---

# 1️⃣ Download Git for Windows

Go to the official Git website:

[Download Git for Windows](https://git-scm.com/download/win?utm_source=chatgpt.com)

Click:

```text
Download for Windows
```

The Git installer `.exe` file will be downloaded.

---

# 2️⃣ Install Git

Open the downloaded `.exe` installer.

For a beginner, you can generally keep the default options unless mentioned below.

### Select Components

Keep the default options.

Click:

```text
Next
```

---

### Choosing the Default Editor

Keep the default editor or select your preferred editor.

Click:

```text
Next
```

---

### Adjusting the Name of the Initial Branch

You can select:

```text
Override the default branch name for new repositories
```

and use:

```text
main
```

This is commonly used as the default branch name for modern Git repositories.

Click:

```text
Next
```

---

### Adjusting Your PATH Environment

Select the recommended option:

```text
Git from the command line and also from 3rd-party software
```

This allows you to run Git commands from:

* Git Bash
* Command Prompt
* PowerShell
* Other applications

Click:

```text
Next
```

---

### Choosing HTTPS Transport Backend

Keep the default option.

Click:

```text
Next
```

---

### Configuring Line Ending Conversions

Keep the default option.

Click:

```text
Next
```

---

### Configuring the Terminal Emulator

Keep the default option.

Click:

```text
Next
```

---

### Continue Installation

Continue through the remaining installation options using the defaults unless you have a specific requirement.

---

### Install

Click:

```text
Install
```

Wait for the installation to complete.

---

### Finish

Once the installation is complete:

```text
Click Finish
```

Git is now installed on your Windows computer. ✅

---

# 3️⃣ Verify Git Installation

Open the Windows Start menu and search for:

```text
Git Bash
```

Open **Git Bash**.

Run:

```bash
git --version
```

You should see output similar to:

```text
git version 2.x.x
```

The exact version number may be different.

For example:

```text
git version 2.51.0
```

If you see a Git version, Git has been installed successfully.

---
