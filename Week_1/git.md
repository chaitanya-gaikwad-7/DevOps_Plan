
##  **Git Essentials**

---

### 1. ⚙️ **What is Git?**

* **Definition**: Git is a distributed version control system.
* **Why it's used**:

  * Tracks changes in source code.
  * Enables collaboration.
  * Allows rollback and branching.

> 🔍 Git stores your project history and allows multiple developers to work without overwriting each other’s changes.

---

### 2. 📁 **Git Installation & Configuration**

* Install Git (`git --version`)

* Configure Git (first-time setup):

  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "you@example.com"
  git config --list  # View current config
  ```

* Understand `~/.gitconfig`

---

### 3. 🗂️ **Repositories**

* **Local Repository**: On your machine.
* **Remote Repository**: Hosted elsewhere (GitHub, GitLab, Bitbucket).
* **Commands**:

  * `git init` – create a new local repo.
  * `git clone <url>` – clone a remote repo.

> 🧠 Understanding the difference between local and remote is critical.

---

### 4. 📋 **Working Directory, Staging Area, and Commit**

* **Working Directory**: Where you edit files.
* **Staging Area (Index)**: Files selected to be committed.
* **Commit History (HEAD)**: Snapshot of the project.

**Commands to know**:

* `git status`
* `git add file.txt` or `git add .`
* `git commit -m "message"`
* `git log` – see commit history

> 📌 You must add → then commit → then push.

---

### 5. 🔄 **Basic Git Workflow**

```bash
git clone <repo>
cd <repo>
# edit files
git add .
git commit -m "your message"
git push origin main
```

---

### 6. 🌿 **Branches in Git**

* What is a branch? A separate line of development.
* **Common branches**: `main`, `dev`, `feature/*`, `bugfix/*`

**Commands**:

* `git branch` – list branches
* `git branch <name>` – create branch
* `git checkout <name>` – switch branch
* `git checkout -b <name>` – create and switch
* `git merge <branch>` – merge into current branch
* `git rebase` – reapply commits on top of another base

> 🧠 Learn the difference between merge and rebase (important for DevOps teams).

---

### 7. ⬆️ **Pushing and Pulling**

* `git push origin <branch>` – send local commits to remote
* `git pull` – fetch and merge changes from remote
* `git fetch` – only fetches remote changes (no merge)

---

### 8. 🧪 **Viewing Changes**

* `git diff` – see changes not staged
* `git diff --staged` – see changes staged for commit
* `git log` – view commit history
* `git show <commit>` – view a specific commit

---

### 9. 🔁 **Undoing Changes / Rollback**

* `git restore <file>` – undo changes in working directory
* `git reset <file>` – unstage a file
* `git reset --hard <commit>` – reset everything (destructive!)
* `git revert <commit>` – undo a commit safely (creates a new commit)

> 🧨 **Reset** can be dangerous. Use carefully.

---

### 10. 👥 **Working with Remote Repositories**

* `git remote -v` – view remotes
* `git remote add origin <url>` – add a remote
* `git push -u origin main` – push for the first time and set upstream

---

### 11. 🎯 **Git Ignore**

* Use `.gitignore` to exclude files from version control
* Examples:

  ```bash
  *.log
  node_modules/
  __pycache__/
  .env
  ```

>  Good practice for DevOps to avoid pushing sensitive or build-specific files.

---

### 12. 🧪 **Git Tags**

* Tag specific commits (usually releases)

  ```bash
  git tag v1.0.0
  git push origin v1.0.0
  ```

---

### 13. 🤝 **Collaboration and Pull Requests (PRs)**

* **Forking & Pull Requests**: Used on GitHub/GitLab
* **Creating PRs**:

  * Push your branch
  * Create a PR via GitHub UI
  * Review code
  * Merge into `main` or `dev`

> 🛠️ This is essential in a team setting.

---

### 14. 🛠️ **Resolving Merge Conflicts**

* Happens when two branches change the same lines

* Git marks the conflict like this:

  ```diff
  <<<<<<< HEAD
  Your change
  =======
  Their change
  >>>>>>> branch-name
  ```

* You fix the file manually and then:

  ```bash
  git add <conflicted-file>
  git commit
  ```

---

### 15. 🔄 **Stashing Changes**

* Temporarily save uncommitted changes:

  ```bash
  git stash
  git stash list
  git stash apply
  ```

> 💡 Useful when switching branches without committing.

---

## 🧠 Bonus Topics (Optional but Valuable)

* **Git Hooks**: Automate tasks like running tests before a commit.
* **Git Submodules**: Track external repositories inside your project.
* **Signing commits**: `GPG` for secure and verifiable commits.

---
---
---

## **5 mini projects** to help you **practice Git essentials** effectively. 

---

##  1. **Personal Portfolio Website with GitHub Pages**

**Goal**: Host your personal site using Git & GitHub.

### Skills Practiced:

* `git init`, `add`, `commit`, `push`
* Remote repo setup on GitHub
* GitHub Pages deployment

### Steps:

1. Create a simple HTML/CSS portfolio project.
2. Initialize a Git repository.
3. Make multiple commits as you improve the design.
4. Push to GitHub.
5. Use GitHub Pages to publish it.

> Bonus: Create a `dev` branch, add new features there, then merge into `main`.

---

##  2. **Collaborative To-Do App (Simulated Teamwork)**

**Goal**: Simulate team collaboration using Git branches and pull requests.

### Skills Practiced:

* Branching (`checkout -b`, `merge`)
* Conflict resolution
* Pull requests (if using GitHub)
* Commit history review

### Steps:

1. Create a basic to-do list app (HTML or Python CLI).
2. Clone the repo twice (simulate two team members).
3. Each "team member" works on a new feature branch.
4. Merge both into `main` and resolve conflicts.
5. Use `git log` to review the commit history.

> Bonus: Add `.gitignore` and a `README.md`.

---

##  3. **Versioned Documentation Site**

**Goal**: Maintain versions of a project manual using Git branches and tags.

### Skills Practiced:

* Branches for different versions (`v1`, `v2`)
* Tags (`git tag`)
* Diffs between versions

### Steps:

1. Create markdown files for software documentation.
2. Version 1: Basic commands.
3. Create a `v2` branch: Add advanced sections.
4. Tag releases using `git tag v1.0` and `v2.0`.
5. Use `git diff` and `git log` to see what changed.

---

##  4. **Git Cheat Sheet Project (Public or Private)**

**Goal**: Build and maintain your own Git cheat sheet using markdown and version it over time.

### Skills Practiced:

* Commits
* Branches
* Tags
* GitHub README editing

### Steps:

1. Start with basic Git commands in a `cheatsheet.md` file.
2. Commit each section separately (init, commit, push, etc.).
3. Add examples or tips in new branches and merge back.
4. Use tags to mark versions (v1, v2, etc.).
5. Optionally publish on GitHub as public reference.

---

##  5. **DevOps Pipeline Notes Repository (with Git Hooks)**

**Goal**: Maintain learning notes, and implement a Git hook to lint or format markdown before commits.

### Skills Practiced:

* Git hooks (e.g., pre-commit)
* Commit message formatting
* Consistent history with `git log --oneline`

### Steps:

1. Create a repo with folders for CI/CD, Kubernetes, Terraform, etc.
2. Add a `pre-commit` hook to auto-format `.md` files or check for TODOs.
3. Write and commit notes for each tool.
4. Enforce commit message style: e.g., `feat: add terraform notes`.

> Bonus: Use `.gitignore` to avoid committing local configs.

---

### 🧠 Tip:

Treat these projects **as if you're in a team**:

* Use separate branches for new features.
* Write clear commit messages.
* Merge via pull requests if using GitHub.

---

