
---

## Basic Bash Scripting Topics Explained

### 1. **Introduction to the Shell and Bash**

* What is a shell? (Command interpreter)
* Difference between Bash and other shells (sh, zsh, etc.)
* How to write and run a bash script (`.sh` files)
* Making a script executable (`chmod +x script.sh`)
* Running scripts (`./script.sh` or `bash script.sh`)

---

### 2. **Basic Syntax and Script Structure**

* Shebang line (`#!/bin/bash`) — tells the system which interpreter to use
* Comments (`# This is a comment`)
* Commands and how they work in scripts
* Whitespace and newlines

---

### 3. **Variables and Data Types**

* Declaring variables (e.g., `name="John"`)
* Accessing variables (`$name`)
* Variable naming rules
* Using `read` to get user input
* Environment variables and exporting variables (`export VAR=value`)

---

### 4. **Input and Output**

* Printing output with `echo` and `printf`
* Redirecting output (`>`, `>>`)
* Reading user input with `read`
* Standard input (stdin), output (stdout), and error (stderr)

---

### 5. **Basic Operators**

* Arithmetic operators (`+`, `-`, `*`, `/`, `%`)
* String operators (concatenation, comparison)
* Boolean/logical operators (`-eq`, `-ne`, `-gt`, `-lt`, `&&`, `||`)

---

### 6. **Conditionals (if, else, elif)**

* Syntax of `if` statements
* Using `[ ]` and `[[ ]]` for tests
* Numeric and string comparisons
* Nested conditions
* Using `case` for multiple choice scenarios

---

### 7. **Loops**

* `for` loops (iterating over lists or sequences)
* `while` loops (repeating until a condition fails)
* `until` loops (repeat until condition is true)
* Using `break` and `continue` inside loops

---

### 8. **Functions**

* Defining functions (`function_name() { commands; }`)
* Calling functions
* Passing arguments to functions (`$1`, `$2`, ...)
* Returning values (using `return` or output capture)

---

### 9. **Command-line Arguments**

* Accessing arguments passed to scripts (`$0`, `$1`, `$2`, …)
* Using `$#` (number of arguments)
* Using `$@` and `$*` (all arguments)

---

### 10. **Working with Files and Directories**

* Basic commands (`ls`, `cp`, `mv`, `rm`, `mkdir`)
* Checking file types and existence (`-f`, `-d`, `-e`)
* Reading file contents (`cat`, `head`, `tail`)
* Looping over files

---

### 11. **Process Management**

* Running commands in the background (`&`)
* Using `wait` to pause script execution
* Getting process IDs (`$$`, `$!`)

---

### 12. **Error Handling and Exit Status**

* Understanding exit codes (`$?`)
* Using `set -e` to stop on errors
* Using `trap` to handle signals or cleanup

---

### 13. **Basic Text Processing**

* Using commands like `grep`, `sed`, `awk`, `cut`, `sort`, `uniq`
* Redirecting and piping (`|`) commands
* Combining tools for complex data manipulation

---

### 14. **Debugging Bash Scripts**

* Using `set -x` to enable debug mode (shows executed commands)
* Adding debug prints
* Common pitfalls and best practices

---

### Bonus (Optional) — Simple Automation Examples

* Automate backups
* Write simple system monitoring scripts
* Batch rename files

---

## **5 simple automation tasks** you can practice with Bash scripting. 

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

