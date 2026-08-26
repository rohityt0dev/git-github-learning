# 🐧 Install Git on Linux

Before installing Git, first check whether it is already installed.

## 1️⃣ Check Git Installation

Run:

```bash
git --version
```

If Git is installed, you should see output similar to:

```text
git version 2.43.0
```

The exact version may be different.

If you see:

```text
git: command not found
```

Git is not installed and you need to install it.

---

# 2️⃣ Install Git on Ubuntu / Debian

For Ubuntu or Debian-based Linux distributions, first update the package repository:

```bash
sudo apt update
```

Then install Git:

```bash
sudo apt install git -y
```

Verify the installation:

```bash
git --version
```

Example:

```text
git version 2.43.0
```

### Complete Command

```bash
sudo apt update
sudo apt install git -y
git --version
```

---

# 3️⃣ Install Git on Red Hat Enterprise Linux (RHEL)

On modern RHEL systems, use `dnf`.

First update the package information:

```bash
sudo dnf update -y
```

Install Git:

```bash
sudo dnf install git -y
```

Verify:

```bash
git --version
```

Example:

```text
git version 2.x.x
```

### Complete Command

```bash
sudo dnf update -y
sudo dnf install git -y
git --version
```

---

# 4️⃣ Install Git on CentOS

For CentOS Stream and newer CentOS versions, use:

```bash
sudo dnf install git -y
```

Verify:

```bash
git --version
```


# 🆚 Linux Git Installation Commands

| Linux Distribution | Install Command           |
| ------------------ | ------------------------- |
| Ubuntu             | `sudo apt install git -y` |
| Debian             | `sudo apt install git -y` |
| RHEL               | `sudo dnf install git -y` |
| CentOS Stream      | `sudo dnf install git -y` |
| Older CentOS       | `sudo yum install git -y` |
| Amazon Linux 2023  | `sudo dnf install git -y` |
| Amazon Linux 2     | `sudo yum install git -y` |

---

# 🔄 Installation Workflow

```text
Check Git
    │
    ▼
git --version
    │
    ├── Git installed
    │       │
    │       ▼
    │     Done ✅
    │
    └── Git not installed
            │
            ▼
       Identify Linux
            │
      ┌─────┴──────┐
      ▼            ▼
   Debian/RPM    Red Hat/Amazon
      │            │
      ▼            ▼
     apt        dnf / yum
      │            │
      └─────┬──────┘
            ▼
        Install Git
            │
            ▼
      git --version
```

---

# 🔍 Check Your Linux Distribution

If you don't know which Linux distribution you are using, run:

```bash
cat /etc/os-release
```

Example Ubuntu output:

```text
NAME="Ubuntu"
VERSION="24.04 LTS"
```

Example Red Hat output:

```text
NAME="Red Hat Enterprise Linux"
```

Example Amazon Linux:

```text
NAME="Amazon Linux"
VERSION="2023"
```

You can then select the appropriate installation command.

---

