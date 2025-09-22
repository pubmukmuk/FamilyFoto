# 🔐 SSH KEY SETUP FOR GIT & GITHUB
**Author:** Mike Mattinson  
**Created:** 2025-08-24  
**Purpose:** Set up secure SSH authentication for Git operations using Git Bash on Windows (Desktop or Laptop)

## 📁 Where to Save This
Place this file in your project’s `docs/` folder:
```
docs/
├── SETUP-SSH-KEY.md      ← This file
├── PROJECT-DOCS.md
├── diagrams/
└── ...
```

## 🧰 Prerequisites

- Git for Windows (installed to `E:\Git\` with OpenSSH + Unix tools)
- GitHub account (e.g., `devmukmuk`)
- Git Bash terminal or VS Code terminal set to use Git Bash

## 🔧 Step-by-Step Instructions

### ✅ 1. Generate SSH Key
Open Git Bash and run:
```bash
ssh-keygen -t ed25519 -C "devmukmuk@gmail.com"
```

Press Enter to accept:
```
> File to save: /c/Users/Mike/.ssh/id_ed25519
> Passphrase (optional): [your secure passphrase or leave blank]
```

✅ Creates:
```
~/.ssh/id_ed25519       ← Private key (KEEP SECRET)
~/.ssh/id_ed25519.pub   ← Public key (safe to share)
```

### ✅ 2. Add Public Key to GitHub

Show your public key:
```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the output, go to:
📎 https://github.com/settings/keys  
Click ➕ **New SSH key** → Paste → Title: `Desktop - Git Bash`

### ✅ 3. Configure SSH Agent in `.bash_profile`

Create/edit this file:

```bash
nano ~/.bash_profile
```

Paste:

```bash
# ===============================
# ~/.bash_profile – Git Bash Login Setup
# ===============================

# Load interactive settings
test -f ~/.bashrc && . ~/.bashrc
test -f ~/.profile && . ~/.profile

# Start SSH agent if not already running
eval "$(ssh-agent -s)" >/dev/null 2>&1

# Add SSH key only if not already loaded
ssh-add -l >/dev/null 2>&1
if [ $? -ne 0 ]; then
  ssh-add ~/.ssh/id_ed25519
fi
```

---

### ✅ 4. Create or Update `.bashrc`

```bash
nano ~/.bashrc
```

Paste:

```bash
# ===============================
# ~/.bashrc – Git Bash Shell Setup
# ===============================

# Ensure essential Unix tools are available (Git installed in E:\Git)
export PATH="/e/Git/usr/bin:/e/Git/usr/libexec/ssh:/e/Git/mingw64/bin:$PATH"

# 🧪 Project-specific aliases
alias activate_carsim='source /p/Code/py-carsim-2d-game-v1.0.0/.venv/Scripts/activate'
alias activate_securecli='export PATH="/p/Code/py-secure-cli-v1/.venv/Scripts:$PATH"'
```

Then reload:
```bash
source ~/.bashrc
```

Test:
```bash
which ssh-add
which sed
```

### ✅ 5. Test GitHub SSH Access

```bash
ssh -T git@github.com
```

Expected:
```
The authenticity of host 'github.com' can't be established...
Are you sure you want to continue connecting (yes/no)? yes
Enter passphrase for '/c/Users/Mike/.ssh/id_ed25519':
Hi devmukmuk! You've successfully authenticated...
```

### 🧠 Tips & Best Practices

- 🔒 Use **one key per device per GitHub user**
- ❌ Do **not share** your private key
- 🗂️ Backup your `.ssh/` folder to a secure archive
- 💬 Passphrase optional, but recommended for security
- 📂 Git Bash caches your key in memory until you close the session

## 🗃️ Key Files Summary

| File                        | Purpose                                  |
|-----------------------------|------------------------------------------|
| `~/.ssh/id_ed25519`         | Private key (keep secure!)               |
| `~/.ssh/id_ed25519.pub`     | Public key (upload to GitHub)            |
| `~/.ssh/config`             | SSH host settings (optional)             |
| `~/.bash_profile`           | Auto-starts agent and loads key          |
| `~/.bashrc`                 | Shell aliases and PATH fixes             |
| `~/.ssh/known_hosts`        | GitHub’s public host fingerprint         |

✅ SSH key setup is now complete for Git Bash and VS Code integration.  
Test with: `git clone`, `git push`, `git pull` — no username/password required.