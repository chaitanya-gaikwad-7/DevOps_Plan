# 1. Python
---

### 1. **Calculator**

**Goal:** Build a simple calculator that can perform basic arithmetic operations: addition, subtraction, multiplication, and division.

**Concepts practiced:**

* Variables and data types
* Functions (for each operation)
* User input and output
* Conditionals to handle user choices

---

### 2. **Number Guessing Game**

**Goal:** Create a game where the program randomly picks a number, and the user tries to guess it. The program gives hints if the guess is too high or too low.

**Concepts practiced:**

* Loops (`while`)
* Conditionals (`if`/`else`)
* Random number generation (`random` module)
* Functions to structure code

---

### 3. **To-Do List Manager**

**Goal:** Implement a command-line to-do list app where users can add, remove, and view tasks.

**Concepts practiced:**

* Lists and basic data structures
* Loops to iterate over tasks
* Functions for modular code
* File handling (optional — saving tasks persistently)

---

### 4. **Palindrome Checker**

**Goal:** Write a program that checks if a given string is a palindrome (reads the same forwards and backwards).

**Concepts practiced:**

* String manipulation
* Functions
* Conditionals
* Input/output handling

---

### 5. **Simple Text-based Adventure Game**

**Goal:** Create a basic adventure game where the user can navigate between rooms, pick up items, and interact with simple puzzles.

**Concepts practiced:**

* Variables and data structures (dictionaries/lists)
* Functions to organize game logic
* Loops for gameplay flow
* Conditionals for decision-making

---

# 2. Basic Bash scripting

---

### 1. **Backup Files or Directories**

* Write a script that copies important files or folders to a backup directory.
* You can automate this to run daily or weekly via cron.

**Example idea:** Backup your Documents folder to a backup location with a timestamp.

---

### 2. **Batch Rename Files**

* Create a script that renames multiple files in a directory based on a pattern.
* For example, adding a prefix/suffix or changing file extensions.

**Example idea:** Rename all `.txt` files to `.bak` files.

---

### 3. **Disk Usage Report**

* Write a script that checks disk usage (`df -h`) and emails or saves a report if usage crosses a threshold.

**Example idea:** Alert when disk usage is more than 80%.

---

### 4. **System Update Script**

* Automate running system update commands (e.g., `apt update && apt upgrade` on Debian-based systems).
* Include logging so you know when the update was run.

---

### 5. **Clean Temporary Files**

* Write a script that deletes temporary or cache files older than a certain number of days to free up space.

**Example idea:** Delete files older than 7 days in `/tmp` or user cache folders.

---

# 3. Git

---

###  1. **Personal Portfolio Website with GitHub Pages**

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

###  2. **Collaborative To-Do App (Simulated Teamwork)**

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

###  3. **Versioned Documentation Site**

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

###  4. **Git Cheat Sheet Project (Public or Private)**

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

###  5. **DevOps Pipeline Notes Repository (with Git Hooks)**

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

