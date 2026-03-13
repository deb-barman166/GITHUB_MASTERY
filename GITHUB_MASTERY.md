# 🚀 GitHub Mastery — From Beginner to Expert
### 📘 Complete Notes by a 34-Year GitHub Expert | All Options, Commands, Features & More

> **"Version control is not just a tool — it's a superpower."**  
> This guide covers everything: Git, GitHub, Actions, Deployment, Profile Optimization, Live Websites, and beyond.

---

## 📋 Table of Contents

| # | Topic |
|---|-------|
| 1 | [What is Git vs GitHub?](#1-what-is-git-vs-github) |
| 2 | [Git Installation & Setup](#2-git-installation--setup) |
| 3 | [All Git Commands (A–Z)](#3-all-git-commands-a-z) |
| 4 | [GitHub Interface — Every Option Explained](#4-github-interface--every-option-explained) |
| 5 | [Repositories — Create, Clone, Fork, Star](#5-repositories) |
| 6 | [Branches — Create, Merge, Delete](#6-branches) |
| 7 | [Pull Requests & Code Review](#7-pull-requests--code-review) |
| 8 | [Issues & Project Boards](#8-issues--project-boards) |
| 9 | [GitHub Actions (CI/CD)](#9-github-actions-cicd) |
| 10 | [GitHub Pages — Live Website](#10-github-pages--live-website) |
| 11 | [GitHub Deployments & Environments](#11-github-deployments--environments) |
| 12 | [GitHub Profile Optimization](#12-github-profile-optimization) |
| 13 | [README Mastery](#13-readme-mastery) |
| 14 | [GitHub Secrets & Security](#14-github-secrets--security) |
| 15 | [GitHub Packages & Releases](#15-github-packages--releases) |
| 16 | [GitHub Codespaces](#16-github-codespaces) |
| 17 | [GitHub Copilot](#17-github-copilot) |
| 18 | [GitHub CLI](#18-github-cli) |
| 19 | [Advanced Git (Rebase, Cherry-pick, Stash)](#19-advanced-git) |
| 20 | [Pro Tips & Best Practices](#20-pro-tips--best-practices) |

---

## 1. What is Git vs GitHub?

```
Git  ≠  GitHub

Git    → A version control TOOL that runs on your computer (local)
GitHub → A WEBSITE/PLATFORM to host Git repositories (remote/cloud)
```

| Feature | Git | GitHub |
|---------|-----|--------|
| Type | Software (CLI tool) | Web Platform |
| Works Offline | ✅ Yes | ❌ No |
| Stores Code | Locally | On the Cloud |
| Collaboration | ❌ Manual | ✅ Built-in |
| Free? | ✅ Always | ✅ Free tier available |

> 🖼️ **Visual:**
> ```
> Your Computer                   GitHub.com
> ┌─────────────┐    git push    ┌─────────────────┐
> │  LOCAL REPO │ ─────────────► │   REMOTE REPO   │
> │  (Git)      │ ◄───────────── │   (GitHub)      │
> └─────────────┘    git pull    └─────────────────┘
> ```

---

## 2. Git Installation & Setup

### 🔧 Install Git

```bash
# Windows → Download from https://git-scm.com/download/win
# macOS
brew install git

# Ubuntu/Debian Linux
sudo apt-get install git

# Arch Linux
sudo pacman -S git
```

### ⚙️ First-Time Configuration

```bash
# Set your name (shown on every commit)
git config --global user.name "Your Name"

# Set your email (must match GitHub email)
git config --global user.email "you@example.com"

# Set default branch name to main
git config --global init.defaultBranch main

# Set VS Code as default editor
git config --global core.editor "code --wait"

# View all configs
git config --list

# View a single config
git config user.name
```

### 🔑 SSH Key Setup (Recommended)

```bash
# Step 1: Generate SSH key
ssh-keygen -t ed25519 -C "your_email@example.com"

# Step 2: Start SSH agent
eval "$(ssh-agent -s)"

# Step 3: Add key to agent
ssh-add ~/.ssh/id_ed25519

# Step 4: Copy public key
cat ~/.ssh/id_ed25519.pub
# → Paste this on GitHub: Settings > SSH and GPG keys > New SSH key

# Step 5: Test connection
ssh -T git@github.com
# Should say: "Hi username! You've successfully authenticated..."
```

---

## 3. All Git Commands (A–Z)

### 📁 Repository Setup

```bash
git init                    # Initialize a new local repo
git init my-project         # Create a new folder and init repo
git clone <url>             # Clone a remote repo to local
git clone <url> my-folder   # Clone into custom folder name
```

### 📌 Staging & Committing

```bash
git status                  # See which files changed
git add file.txt            # Stage a specific file
git add .                   # Stage ALL changes
git add *.py                # Stage all Python files
git add -p                  # Interactively stage chunks

git commit -m "message"     # Commit with message
git commit -am "message"    # Stage tracked files + commit
git commit --amend          # Edit the last commit message
git commit --amend --no-edit # Add to last commit without changing message
```

### 🔍 Viewing History

```bash
git log                     # Full commit history
git log --oneline           # Compact one-line history
git log --oneline --graph   # Visual branch graph
git log --author="Name"     # Commits by specific person
git log -n 5                # Last 5 commits only
git log --since="2024-01-01" # Commits after a date
git log --grep="fix"        # Commits mentioning "fix"

git show <commit-hash>      # Show a specific commit details
git diff                    # Unstaged changes
git diff --staged           # Staged changes ready to commit
git diff main..feature      # Difference between branches
```

### 🌿 Branching

```bash
git branch                  # List local branches
git branch -a               # List all branches (local + remote)
git branch feature-login    # Create new branch
git checkout feature-login  # Switch to branch
git checkout -b feature-login # Create AND switch (shortcut)
git switch main             # Modern way to switch (Git 2.23+)
git switch -c new-feature   # Modern way to create + switch

git branch -d feature-login  # Delete branch (safe - only if merged)
git branch -D feature-login  # Force delete branch
git branch -m old-name new-name # Rename a branch
```

### 🔀 Merging & Rebasing

```bash
git merge feature-login     # Merge branch into current
git merge --no-ff feature   # Merge with a merge commit (keeps history)
git merge --squash feature  # Combine all commits into one

git rebase main             # Rebase current branch onto main
git rebase -i HEAD~3        # Interactive rebase last 3 commits
# In interactive rebase:
# pick   = keep commit
# reword = change message
# edit   = pause and edit
# squash = combine with previous
# drop   = delete commit

git cherry-pick <hash>      # Apply a specific commit to current branch
```

### 🌐 Remote Operations

```bash
git remote -v               # View remote connections
git remote add origin <url> # Add a remote called "origin"
git remote remove origin    # Remove remote
git remote rename old new   # Rename remote

git fetch origin            # Download changes (don't merge)
git fetch --all             # Fetch all remotes
git pull                    # Fetch + merge
git pull origin main        # Pull from specific branch
git pull --rebase           # Pull with rebase instead of merge

git push origin main        # Push to remote
git push -u origin main     # Push and set upstream tracking
git push --force            # Force push (⚠️ dangerous!)
git push --force-with-lease # Safer force push
git push origin --delete feature # Delete remote branch
git push --tags             # Push all tags
```

### 🏷️ Tags

```bash
git tag                     # List all tags
git tag v1.0.0              # Create lightweight tag
git tag -a v1.0.0 -m "Release v1.0.0" # Annotated tag
git tag v1.0.0 <commit-hash> # Tag a specific commit
git push origin v1.0.0      # Push a single tag
git push origin --tags      # Push all tags
git tag -d v1.0.0           # Delete local tag
git push origin --delete v1.0.0 # Delete remote tag
```

### 💾 Stashing

```bash
git stash                   # Save work-in-progress temporarily
git stash push -m "WIP login feature" # Named stash
git stash list              # View all stashes
git stash pop               # Apply latest stash + delete it
git stash apply stash@{0}   # Apply stash without deleting
git stash drop stash@{0}    # Delete a specific stash
git stash clear             # Delete ALL stashes
git stash branch new-branch # Create branch from stash
```

### ↩️ Undoing Changes

```bash
git restore file.txt        # Discard unstaged changes to a file
git restore --staged file.txt # Unstage a file
git reset HEAD~1            # Undo last commit (keep changes)
git reset --soft HEAD~1     # Undo commit, keep staged
git reset --mixed HEAD~1    # Undo commit, unstage changes (default)
git reset --hard HEAD~1     # Undo commit AND delete changes ⚠️
git revert <hash>           # Create new commit that undoes a commit (safe)
git revert HEAD             # Undo the last commit safely
git clean -fd               # Delete untracked files and folders
```

### 🗑️ Deleting Files

```bash
git rm file.txt             # Remove file from git + filesystem
git rm --cached file.txt    # Remove from git only (keep file)
git mv old.txt new.txt      # Rename/move file
```

### 🔎 Searching

```bash
git grep "search term"      # Search in working directory
git log -S "function_name"  # Find when a string was added/removed
git blame file.txt          # See who changed each line
git bisect start            # Start binary search for bug
git bisect bad              # Mark current as bad
git bisect good <hash>      # Mark a known-good commit
```

### 🧹 Maintenance

```bash
git gc                      # Garbage collection (optimize)
git prune                   # Remove unreachable objects
git fsck                    # Check integrity
git reflog                  # Show ALL recent HEAD movements (lifesaver!)
```

---

## 4. GitHub Interface — Every Option Explained

### 🏠 GitHub Navigation Bar (Top)

```
┌─────────────────────────────────────────────────────────────────────┐
│  🐙 GitHub  [Search bar]  Pull requests  Issues  Codespaces  +▼  🔔  │
└─────────────────────────────────────────────────────────────────────┘
```

> 🔗 **Image Reference:** https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png

| Option | What it does |
|--------|--------------|
| **Search bar** | Search repos, users, issues, code globally |
| **Pull requests** | All PRs assigned to / created by you |
| **Issues** | All issues across repos |
| **Codespaces** | Cloud-based dev environments |
| **`+` button** | New repo, gist, org, import repo |
| **🔔 Bell** | Notifications from repos you watch |
| **Profile avatar** | Your profile, settings, sign out |

---

### 📂 Repository Page Layout

```
owner/repo-name
├── 📌 Code          ← Files & folders
├── 🐛 Issues        ← Bug reports, feature requests
├── 🔀 Pull requests ← Code review & merging
├── ▶️  Actions       ← CI/CD pipelines
├── 📦 Projects      ← Kanban boards
├── 🔒 Security      ← Vulnerabilities, secrets scanning
├── 📊 Insights      ← Stats, contributors, traffic
└── ⚙️  Settings     ← Everything about the repo
```

#### 📌 Code Tab

```
┌─────────────────────────────────────────────────────────────┐
│  main ▼  [Branch selector]              [Code ▼] [Star] [Fork] │
│                                                              │
│  📁 src/          2 hours ago   Add login feature           │
│  📁 tests/        yesterday     Fix unit tests              │
│  📄 README.md     3 days ago    Update docs                 │
│  📄 .gitignore    1 week ago    Add node_modules            │
│                                                              │
│  [README preview below]                                     │
└─────────────────────────────────────────────────────────────┘
```

**Key buttons on Code tab:**

| Button | Action |
|--------|--------|
| **Branch selector** | Switch between branches/tags |
| **Code ▼** | Clone (HTTPS/SSH), Open in Codespaces, Download ZIP |
| **Go to file** | Fuzzy search for any file |
| **Add file** | Create or upload files |
| **Star ⭐** | Bookmark the repo (like a Like button) |
| **Fork 🍴** | Copy repo to your account |
| **Watch 👁️** | Get notifications for this repo |

---

## 5. Repositories

### ✨ Creating a Repository

**On GitHub.com:**
1. Click `+` → "New repository"
2. Fill in:
   - **Repository name** (use kebab-case: `my-project`)
   - **Description** (optional but recommended)
   - **Public / Private**
   - ✅ Add a README file
   - ✅ Add .gitignore (choose your language)
   - Choose a License (MIT is popular)
3. Click "Create repository"

```bash
# Then connect locally:
git clone https://github.com/username/repo-name.git
cd repo-name
```

### 🍴 Forking a Repository

Forking = Making YOUR OWN COPY of someone else's repo.

```
Original Repo (someone-else/project)
         ↓  Fork
Your Repo (your-username/project)
         ↓  git clone
Your Computer
```

**Steps:**
1. Go to any public repo
2. Click **Fork** (top right)
3. Select your account
4. Now you have your own copy!

```bash
# After forking, keep your fork updated:
git remote add upstream https://github.com/original-owner/repo.git
git fetch upstream
git merge upstream/main
```

### 📥 Cloning

```bash
# HTTPS (easier for beginners)
git clone https://github.com/username/repo.git

# SSH (recommended, no password needed after setup)
git clone git@github.com:username/repo.git

# Clone specific branch
git clone -b develop https://github.com/username/repo.git

# Clone with limited history (faster)
git clone --depth 1 https://github.com/username/repo.git
```

### ⭐ Stars, Watching, Pinning

```bash
# Stars = Bookmarks for repos you like
# Watching = Get notifications
#   - "Not watching" = only get notified if mentioned
#   - "Watching"     = all activity
#   - "Releases"     = only new releases

# Pin repos on your profile:
# Profile → Customize your pins → Select up to 6 repos
```

---

## 6. Branches

### 🌿 Branch Strategy (Professional)

```
main (production) ─────────────────────────────────────►
         │                          ↑
         └──► develop ──────────────┤ merge when stable
                   │           ↑   │
                   └──► feature/login ──► PR ──► merge
                   └──► fix/navbar-bug ──► PR ──► merge
                   └──► hotfix/critical ─────────────────►
```

**Branch naming conventions:**
```
feature/user-authentication
bugfix/fix-login-error
hotfix/security-patch
release/v2.0.0
chore/update-dependencies
docs/add-api-docs
```

### Creating & Managing Branches

```bash
# Create from current branch
git checkout -b feature/new-login

# Create from specific branch
git checkout -b hotfix/bug main

# Push branch to GitHub
git push -u origin feature/new-login

# See all branches on GitHub
# Go to repo → Click "main" dropdown → See all branches
```

### 🔒 Branch Protection Rules (GitHub Settings)

Navigate: `Settings → Branches → Add branch protection rule`

```
✅ Require a pull request before merging
✅ Require approvals (1-2 reviews)
✅ Require status checks to pass (tests must pass)
✅ Require signed commits
✅ Include administrators
❌ Allow force pushes (keep disabled!)
```

---

## 7. Pull Requests & Code Review

### What is a Pull Request (PR)?

A PR = "Please pull my changes into your branch."  
It's a REQUEST to MERGE your branch into another branch.

```
feature/login  ──── PR ────► main
   (your work)             (production)
```

### Creating a PR

**On GitHub:**
1. Push your branch to GitHub
2. Go to repo → Click "Compare & pull request" (yellow banner)
   OR → "Pull requests" tab → "New pull request"
3. Fill in:
   - **Title**: Clear, descriptive (`Add user authentication`)
   - **Description**: What you changed, why, screenshots
   - **Reviewers**: Tag people to review
   - **Labels**: bug, enhancement, documentation
   - **Assignees**: Who is responsible
   - **Milestone**: Link to project milestone
   - **Projects**: Link to project board

### PR Description Template

```markdown
## What changed?
Brief description of the changes.

## Why?
Explain the motivation/context.

## How to test?
1. Step 1
2. Step 2

## Screenshots
(if UI changes)

## Checklist
- [ ] Tests added
- [ ] Documentation updated
- [ ] No breaking changes
```

### 👁️ Code Review

**As a Reviewer:**
1. Click "Files changed" tab
2. Hover over any line → Click `+` to add comment
3. Click "Review changes" →
   - **Comment**: General feedback
   - **Approve**: ✅ Looks good!
   - **Request changes**: ❌ Need fixes first

**Review Comment Types:**
```
Suggestion: Can replace code directly in browser
Comment: Ask questions, give feedback  
Resolved: Mark comment as done
```

### Merging a PR

```
Three merge strategies:
┌────────────────────────────────────────────────────┐
│ 1. Create a merge commit   → Keeps all commits     │
│ 2. Squash and merge        → One clean commit      │ ← Most common
│ 3. Rebase and merge        → Linear history        │
└────────────────────────────────────────────────────┘
```

### Reopening a PR

```bash
# If a PR was closed accidentally:
# GitHub UI: Go to the closed PR → Click "Reopen pull request"

# OR via CLI:
gh pr reopen <PR-number>
```

---

## 8. Issues & Project Boards

### 🐛 Issues

Issues = Tasks, bugs, feature requests, discussions.

```
Issue Types:
🐛 Bug Report    → Something is broken
✨ Feature Request → New functionality wanted
📚 Documentation → Docs need updating
❓ Question      → Help needed
```

**Creating an Issue:**
1. Repo → Issues → New Issue
2. Fill in title + description (use Markdown!)
3. Add labels, assignee, milestone

**Closing Issues via Commits:**
```bash
# These keywords in commit messages AUTO-CLOSE the issue:
git commit -m "Fix login bug, closes #42"
git commit -m "Add dark mode, fixes #15, resolves #16"

# Keywords: closes, fixes, resolves (followed by #issue-number)
```

**Issue Templates:**  
Create `.github/ISSUE_TEMPLATE/bug_report.md`

```markdown
---
name: Bug report
about: Create a report to help us improve
labels: bug
---

**Describe the bug**
A clear description of the bug.

**Steps to reproduce**
1. Go to '...'
2. Click on '...'
3. See error

**Expected behavior**
What you expected to happen.

**Screenshots**
If applicable, add screenshots.
```

### 📊 Project Boards

Navigate: Repo → Projects → New Project

```
Kanban View:
┌──────────────┬──────────────┬──────────────┬──────────────┐
│   Backlog    │  In Progress │   Review     │    Done      │
├──────────────┼──────────────┼──────────────┼──────────────┤
│ Issue #1     │ Issue #3     │ PR #7        │ Issue #2     │
│ Issue #4     │ Issue #5     │              │ Issue #6     │
└──────────────┴──────────────┴──────────────┴──────────────┘
```

---

## 9. GitHub Actions (CI/CD)

### What is GitHub Actions?

GitHub Actions = Automated workflows triggered by events.

```
Event (push to main)
      ↓
Workflow (.github/workflows/ci.yml)
      ↓
Job (runs on a virtual machine)
      ↓
Steps (checkout → install → test → deploy)
```

### File Structure

```
your-repo/
└── .github/
    └── workflows/
        ├── ci.yml          # Continuous Integration
        ├── deploy.yml      # Deployment
        └── release.yml     # Release automation
```

### Basic Workflow Syntax

```yaml
# .github/workflows/ci.yml
name: CI Pipeline

on:                          # TRIGGERS
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '0 0 * * *'     # Every day at midnight
  workflow_dispatch:          # Manual trigger button on GitHub

jobs:
  build-and-test:            # Job name
    runs-on: ubuntu-latest   # Operating system
    
    steps:
      - name: Checkout code
        uses: actions/checkout@v4
        
      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.11'
          
      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt
          
      - name: Run tests
        run: pytest tests/ -v
        
      - name: Upload test results
        uses: actions/upload-artifact@v4
        with:
          name: test-results
          path: test-results/
```

### Python Project CI Example

```yaml
# .github/workflows/python-ci.yml
name: Python CI

on: [push, pull_request]

jobs:
  test:
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        os: [ubuntu-latest, windows-latest]
        python-version: ['3.10', '3.11', '3.12']
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Set up Python ${{ matrix.python-version }}
      uses: actions/setup-python@v4
      with:
        python-version: ${{ matrix.python-version }}
    
    - name: Cache pip
      uses: actions/cache@v3
      with:
        path: ~/.cache/pip
        key: ${{ runner.os }}-pip-${{ hashFiles('requirements.txt') }}
    
    - name: Install dependencies
      run: pip install -r requirements.txt
    
    - name: Lint with flake8
      run: flake8 . --max-line-length=100
    
    - name: Test with pytest
      run: pytest --cov=src tests/
    
    - name: Upload coverage to Codecov
      uses: codecov/codecov-action@v3
```

### Deploy to GitHub Pages via Actions

```yaml
# .github/workflows/deploy-pages.yml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup Pages
        uses: actions/configure-pages@v4
        
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: './dist'    # Your build output folder
          
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

### Docker Build & Push

```yaml
# .github/workflows/docker.yml
name: Docker Build

on:
  push:
    branches: [ main ]
    tags: [ 'v*' ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Login to DockerHub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}
      
      - name: Build and push
        uses: docker/build-push-action@v5
        with:
          push: true
          tags: username/myapp:latest
```

### Common Action Events

```yaml
on:
  push:               # Code pushed
  pull_request:       # PR opened/updated
  pull_request_review: # PR reviewed
  issues:             # Issue opened/closed
  issue_comment:      # Comment on issue
  release:            # Release published
  schedule:           # Cron job
    - cron: '0 9 * * 1'  # Every Monday 9 AM
  workflow_dispatch:  # Manual button
  workflow_call:      # Called from another workflow
  repository_dispatch: # External HTTP trigger
```

### Useful Actions from Marketplace

```yaml
# actions/checkout@v4         → Clone your repo
# actions/setup-node@v4       → Setup Node.js
# actions/setup-python@v4     → Setup Python
# actions/cache@v3            → Cache dependencies
# actions/upload-artifact@v4  → Save files between jobs
# actions/download-artifact@v4 → Download saved files
# github/codeql-action        → Security scanning
# codecov/codecov-action@v3   → Code coverage reports
# docker/build-push-action@v5 → Build Docker images
```

---

## 10. GitHub Pages — Live Website

### Method 1: Static HTML Site (Simplest)

```bash
# 1. Create an index.html in your repo root
# 2. Push to GitHub
# 3. Settings → Pages → Source: "Deploy from branch"
# 4. Branch: main, Folder: / (root)
# 5. Save → Wait ~2 minutes
# 6. Visit: https://username.github.io/repo-name
```

### Method 2: User/Org Profile Site

```bash
# Special repo name: username.github.io
# → Becomes your profile website at https://username.github.io

# Create repo named: yourname.github.io
# Add index.html
# Push → Live at https://yourname.github.io
```

### Method 3: React/Vue/Next.js App

```bash
# React project:
npm run build           # Creates /build folder

# In package.json, add:
"homepage": "https://username.github.io/repo-name"

# Install gh-pages:
npm install --save-dev gh-pages

# Add to scripts in package.json:
"predeploy": "npm run build",
"deploy": "gh-pages -d build"

# Deploy:
npm run deploy
# → Creates gh-pages branch automatically
```

### Method 4: Vite/Vue Project

```bash
# vite.config.js
export default {
  base: '/repo-name/',    // ← Add this line!
}

# Build
npm run build    # Creates /dist folder

# Settings → Pages → Source: Deploy from branch
# Branch: main, Folder: /dist
# OR use GitHub Actions (recommended)
```

### Custom Domain

```bash
# 1. Buy domain (e.g., yoursite.com) from Namecheap, GoDaddy
# 2. In domain DNS, add:
#    Type: CNAME, Name: www, Value: username.github.io
#    Type: A, Name: @, Value: 185.199.108.153
#                              185.199.109.153
#                              185.199.110.153
#                              185.199.111.153
# 3. GitHub repo: Settings → Pages → Custom domain → enter domain
# 4. ✅ Enforce HTTPS
```

---

## 11. GitHub Deployments & Environments

### Environments (staging, production)

```
Settings → Environments → New environment
```

```yaml
# Use environments in Actions:
jobs:
  deploy-staging:
    environment:
      name: staging
      url: https://staging.yourapp.com
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to staging
        run: echo "Deploying to staging..."

  deploy-production:
    environment:
      name: production
      url: https://yourapp.com
    needs: deploy-staging      # Only runs after staging succeeds
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to production
        run: echo "Deploying to production..."
```

### Deploy to Popular Platforms

#### Vercel (Best for Next.js/React)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# Auto-deploy: Connect GitHub repo at vercel.com
# → Every push to main = automatic deployment
# → Every PR = preview deployment with unique URL
```

#### Netlify
```bash
# Install Netlify CLI
npm i -g netlify-cli

# Deploy
netlify deploy --prod --dir=build

# netlify.toml configuration:
[build]
  command = "npm run build"
  publish = "dist"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

#### Railway / Render (Backend Apps)
```bash
# Connect GitHub repo → auto-deploy on push
# railway.toml or render.yaml for configuration
```

---

## 12. GitHub Profile Optimization

### 🌟 Profile README

**Special repo: Create `username/username` repository!**

```bash
# 1. Create new repo named exactly: your-github-username
# 2. Initialize with README.md
# 3. This README shows on your GitHub profile!
```

### Profile README Template

```markdown
# 👋 Hi, I'm [Your Name]!

<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=00D9FF&center=true&vCenter=true&width=435&lines=Python+Developer;AI+%7C+ML+%7C+Deep+Learning;Open+Source+Enthusiast;Class+XI+Student+%F0%9F%9A%80" alt="Typing SVG" />
</div>

---

## 🚀 About Me

- 🎓 Class XI Student passionate about tech
- 🤖 Building AI Agents and ML Models
- 💻 Python Developer & Open Source Contributor
- 📹 Video Editing & Content Creation
- 🌱 Currently learning: Deep Learning, LLMs

---

## 🛠️ Tech Stack

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white)

</div>

---

## 📊 GitHub Stats

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=tokyonight" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&theme=tokyonight" />
</div>

---

## 🔥 Streak Stats

<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=YOUR_USERNAME&theme=tokyonight" />
</div>

---

## 🏆 GitHub Trophies

<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=YOUR_USERNAME&theme=tokyonight&row=1" />
</div>

---

## 📈 Contribution Graph

![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=YOUR_USERNAME&theme=tokyo-night)

---

## 📫 Connect With Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/yourprofile)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/yourhandle)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF5722?style=for-the-badge&logo=google-chrome&logoColor=white)](https://yourwebsite.com)

---

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=YOUR_USERNAME&color=blue&style=flat-square" alt="Profile views" />
</div>
```

### Profile Settings to Optimize

```
github.com → Click avatar → Settings

✅ Profile:
   - Photo (professional or fun)
   - Name (real name helps)
   - Bio (short, punchy: "Python Dev | AI/ML | Building cool stuff")
   - Company
   - Location (optional)
   - Website (your portfolio)
   - Twitter
   - Pronouns

✅ Public profile:
   - Pin 6 best repositories
   - Display contribution graph

✅ Appearance:
   - Enable "Private Contributions" in contribution settings
   - → This shows contributions to private repos in your graph!
```

---

## 13. README Mastery

### Essential README Sections

```markdown
# Project Name

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.11-blue.svg)](https://python.org)
[![Stars](https://img.shields.io/github/stars/username/repo)](https://github.com/username/repo)

Short description of what the project does.

## ✨ Features
- Feature 1
- Feature 2

## 🚀 Quick Start
\`\`\`bash
git clone https://github.com/username/repo
cd repo
pip install -r requirements.txt
python main.py
\`\`\`

## 📖 Documentation
Full docs at [docs.yourproject.com](https://docs.yourproject.com)

## 🤝 Contributing
Pull requests welcome! Read [CONTRIBUTING.md](CONTRIBUTING.md)

## 📄 License
[MIT License](LICENSE)
```

### Shields/Badges (shields.io)

```markdown
# Build status
![Build](https://github.com/user/repo/workflows/CI/badge.svg)

# Stars
![Stars](https://img.shields.io/github/stars/user/repo)

# License
![License](https://img.shields.io/github/license/user/repo)

# Last commit
![Last Commit](https://img.shields.io/github/last-commit/user/repo)

# Language
![Language](https://img.shields.io/github/languages/top/user/repo)

# Custom badge
![Custom](https://img.shields.io/badge/label-message-color)
# Colors: brightgreen, green, yellow, orange, red, blue, lightgrey
# Example:
![Made with](https://img.shields.io/badge/Made%20with-Python-blue)
```

---

## 14. GitHub Secrets & Security

### Setting Secrets

```
Repo → Settings → Secrets and variables → Actions → New repository secret
```

```yaml
# Use secrets in workflow:
jobs:
  deploy:
    steps:
      - name: Deploy
        env:
          API_KEY: ${{ secrets.MY_API_KEY }}
          DB_PASSWORD: ${{ secrets.DATABASE_PASSWORD }}
        run: python deploy.py
```

**Types of Secrets:**
```
Repository secrets    → Only for that repo
Environment secrets   → Only for specific environment (staging/prod)
Organization secrets  → Shared across org repos
```

### Security Features

```
Settings → Security

🔒 Dependabot alerts    → Notifies about vulnerable dependencies
🔒 Code scanning        → Finds security bugs in your code (CodeQL)
🔒 Secret scanning      → Detects accidentally committed secrets
🔒 Private vulnerability reporting
```

### .gitignore (Never commit these!)

```gitignore
# .gitignore for Python/AI projects

# Secrets
.env
.env.local
*.key
secrets.json
credentials.json

# Python
__pycache__/
*.py[cod]
*.egg-info/
dist/
build/
venv/
.venv/
*.pyc

# Jupyter
.ipynb_checkpoints/

# ML/Data
*.pkl
*.h5
*.pt
*.pth
data/raw/
models/large/

# OS
.DS_Store
Thumbs.db

# IDE
.vscode/settings.json
.idea/
*.swp
```

---

## 15. GitHub Packages & Releases

### Creating a Release

```bash
# On GitHub:
# Repo → Releases → Draft a new release
# → Choose a tag: v1.0.0
# → Target: main
# → Release title: Version 1.0.0
# → Write release notes (changes, features, bugs fixed)
# → ✅ Set as latest release
# → Publish release

# Via Git:
git tag -a v1.0.0 -m "Release v1.0.0"
git push origin v1.0.0
```

### Auto-generate Release Notes

```yaml
# .github/workflows/release.yml
name: Release

on:
  push:
    tags:
      - 'v*'

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Create Release
        uses: softprops/action-gh-release@v1
        with:
          generate_release_notes: true   # Auto-generate from PRs!
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

---

## 16. GitHub Codespaces

Codespaces = VS Code in your browser, powered by cloud VMs.

```
Repo → Code → Codespaces → Create codespace on main
```

**Configuration:**

```json
// .devcontainer/devcontainer.json
{
  "name": "Python AI Dev",
  "image": "mcr.microsoft.com/devcontainers/python:3.11",
  "features": {
    "ghcr.io/devcontainers/features/git:1": {}
  },
  "postCreateCommand": "pip install -r requirements.txt",
  "customizations": {
    "vscode": {
      "extensions": [
        "ms-python.python",
        "ms-toolsai.jupyter",
        "github.copilot"
      ]
    }
  },
  "forwardPorts": [8000, 8080],
  "portsAttributes": {
    "8000": {"label": "App"}
  }
}
```

---

## 17. GitHub Copilot

GitHub Copilot = AI pair programmer (powered by OpenAI).

```bash
# Install in VS Code:
# Extensions → Search "GitHub Copilot" → Install
# Sign in with GitHub account (need Copilot subscription)

# Usage:
# Start typing a function comment → Copilot suggests code
# Tab → Accept suggestion
# Esc → Dismiss
# Alt+] → Next suggestion
# Alt+[ → Previous suggestion
# Ctrl+Enter → See all suggestions
```

**Copilot Chat:**
```bash
# Open Copilot Chat: Ctrl+Shift+I
# Commands:
/explain   # Explain selected code
/fix       # Fix bugs in selected code
/tests     # Generate unit tests
/doc       # Generate documentation
/optimize  # Suggest performance improvements
```

---

## 18. GitHub CLI

```bash
# Install
# Windows: winget install --id GitHub.cli
# macOS: brew install gh
# Linux: sudo apt install gh

# Authentication
gh auth login

# Repository commands
gh repo create my-project --public
gh repo clone username/repo
gh repo view username/repo --web   # Open in browser
gh repo fork username/repo

# Pull Request commands
gh pr create --title "Add feature" --body "Description"
gh pr list
gh pr view 42
gh pr checkout 42      # Checkout PR locally
gh pr merge 42 --squash
gh pr close 42
gh pr reopen 42

# Issue commands
gh issue create --title "Bug" --label "bug"
gh issue list
gh issue view 15
gh issue close 15
gh issue reopen 15
gh issue comment 15 --body "Looking into this"

# Actions commands
gh workflow list
gh workflow run ci.yml
gh run list
gh run view 12345
gh run watch           # Watch live run

# Other useful commands
gh gist create file.py --public
gh secret set MY_SECRET
gh release create v1.0.0
gh api /user           # Direct API calls
```

---

## 19. Advanced Git

### Interactive Rebase (Rewriting History)

```bash
# Edit last 3 commits
git rebase -i HEAD~3

# Editor opens:
# pick abc1234 Add login
# pick def5678 Fix typo
# pick ghi9012 Add tests

# Change to:
# pick abc1234 Add login
# squash def5678 Fix typo     ← Combine with above
# reword ghi9012 Add tests    ← Change message
```

### Rebase onto Another Branch

```bash
# Situation: main has moved forward, rebase your feature
git checkout feature/login
git rebase main

# If conflicts:
git rebase --continue    # After resolving conflict
git rebase --abort       # Cancel and go back
git rebase --skip        # Skip this commit
```

### Cherry-pick

```bash
# Apply a single commit from another branch
git log --oneline another-branch    # Find the commit hash
git cherry-pick abc1234              # Apply it here

# Cherry-pick a range
git cherry-pick abc1234..def5678

# Cherry-pick without committing
git cherry-pick -n abc1234
```

### Git Worktree (Multiple Working Directories)

```bash
# Work on two branches simultaneously!
git worktree add ../project-hotfix hotfix/critical-bug
# Now you can work in both folders at once
git worktree list
git worktree remove ../project-hotfix
```

### Reflog (Git's Safety Net)

```bash
# See EVERYTHING that happened
git reflog

# Output:
# abc1234 HEAD@{0}: commit: Add tests
# def5678 HEAD@{1}: checkout: moving from main to feature
# ...

# Recover a deleted branch:
git checkout -b recovered-branch HEAD@{3}

# Undo a bad rebase:
git reset --hard HEAD@{5}
```

### Submodules

```bash
# Add another repo inside your repo
git submodule add https://github.com/someone/library libs/library

# Clone repo with submodules
git clone --recurse-submodules https://github.com/you/repo

# Update submodules
git submodule update --init --recursive
git submodule update --remote              # Pull latest
```

---

## 20. Pro Tips & Best Practices

### 📝 Commit Message Convention (Conventional Commits)

```
Format: <type>(<scope>): <description>

Types:
feat     → New feature
fix      → Bug fix
docs     → Documentation only
style    → Formatting (no logic change)
refactor → Code restructure (no feature/fix)
test     → Adding tests
chore    → Build process, dependencies
ci       → CI/CD changes
perf     → Performance improvement
revert   → Revert a previous commit

Examples:
feat(auth): add Google OAuth login
fix(navbar): correct mobile menu z-index
docs(readme): add installation instructions
test(api): add unit tests for user endpoints
chore(deps): bump requests from 2.28 to 2.31
ci(actions): add Python 3.12 to test matrix
```

### 🔄 Daily Git Workflow

```bash
# Morning routine
git checkout main
git pull origin main
git checkout -b feature/todays-work

# During work
git add .
git commit -m "feat: implement X"
# (commit often, small commits are better!)

# End of day - push your branch
git push origin feature/todays-work

# When feature is done
# Create PR on GitHub → get reviewed → merge
```

### ⚡ Useful Git Aliases

```bash
# Add to ~/.gitconfig
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.lg "log --oneline --graph --decorate --all"
git config --global alias.undo "reset HEAD~1 --mixed"
git config --global alias.save "stash push"
git config --global alias.pop "stash pop"

# Usage:
git st       # git status
git lg       # Pretty log
git undo     # Undo last commit
```

### 🛡️ Best Practices Summary

```
DO ✅                              DON'T ❌
─────────────────────────────────────────────────────
Commit often (small changes)       One giant commit
Write clear commit messages        "fix stuff", "asdf"
Use branches for features          Commit directly to main
Review code before merging         Auto-merge everything
Use .gitignore                     Commit .env files
Tag releases with versions         Push without testing
Write good README                  Leave README.md empty
Protect main branch                Allow force pushes to main
Use SSH keys                       Type password every push
Enable 2FA on GitHub               Skip security settings
```

### 🎖️ GitHub Profile Checklist

```
Profile Completeness:
☐ Profile photo
☐ Display name
☐ Bio (mention: Python, AI/ML, Student)
☐ Location
☐ Website/Portfolio link
☐ Twitter handle

Repository Quality:
☐ All repos have descriptions
☐ All repos have topics/tags
☐ Key repos have good READMEs
☐ Pin 6 best repositories
☐ At least 1 live demo (GitHub Pages)

Activity:
☐ Contribution graph is green!
☐ Consistent commits
☐ Stars on interesting repos
☐ Follow relevant developers
☐ Contribute to open source

Profile README:
☐ Created username/username repo
☐ Typing animation
☐ Tech stack badges
☐ GitHub stats widgets
☐ Social links
```

---

## 🎓 Learning Path: Beginner → Expert

```
Week 1-2: BEGINNER
├── git init, add, commit, push, pull
├── Create GitHub account
├── Create first repo
└── Push code to GitHub

Week 3-4: INTERMEDIATE
├── Branching & merging
├── Pull requests
├── Issues & projects
├── .gitignore
└── GitHub Pages (first live site!)

Month 2: ADVANCED
├── GitHub Actions (CI/CD)
├── SSH keys setup
├── Rebase & cherry-pick
├── Profile README
└── Custom domain

Month 3+: EXPERT
├── Complex workflows
├── Docker + GitHub Actions
├── Contributing to open source
├── GitHub CLI mastery
├── Security best practices
└── Managing organizations/teams
```

---

## 📚 Resources

| Resource | Link |
|----------|------|
| Official Git Docs | https://git-scm.com/doc |
| GitHub Docs | https://docs.github.com |
| GitHub Actions Marketplace | https://github.com/marketplace/actions |
| Shields.io (badges) | https://shields.io |
| GitHub Stats (by anuraghazra) | https://github.com/anuraghazra/github-readme-stats |
| Readme Typing SVG | https://github.com/DenverCoder1/readme-typing-svg |
| GitHub Trophies | https://github.com/ryo-ma/github-profile-trophy |
| GitHub Skills (official tutorials) | https://skills.github.com |

---

<div align="center">

### ⭐ Star this guide if it helped you!

**Made with ❤️ for aspiring GitHub Experts**

![GitHub](https://img.shields.io/badge/GitHub-Expert_Notes-181717?style=for-the-badge&logo=github)
![Python](https://img.shields.io/badge/Python_Developer-🚀-3776AB?style=for-the-badge&logo=python)
![AI](https://img.shields.io/badge/AI_&_ML-Enthusiast-FF6F00?style=for-the-badge&logo=tensorflow)

</div>
