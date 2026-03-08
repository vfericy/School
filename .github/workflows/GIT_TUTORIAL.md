 Git & GitHub Crash Course

This file lives **in Git**, so you learn Git by using it.  
Use it with GitHub Enterprise, GitHub.com, or any Git server.

---

## 1. What Git Is (and Why It Matters)

Git is a **version control system**. It:

- Tracks every change to your files over time.
- Lets multiple people work on the same project safely.
- Makes it easy to roll back mistakes.

GitHub (or GitHub Enterprise) is a **place where Git repositories live** so teams can collaborate, automate CI/CD, and integrate security tools like CodeQL, Dependabot, and secret scanning.[web:154][web:156]

---

## 2. One-Time Setup

Run these commands once on your machine (replace with your name/email):

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Optional: see all your config
git config --list
3. Create or Clone a Repository
Option A: Start a new repo in an existing folder
bash
cd path/to/your/project
git init          # turn this folder into a Git repository
Option B: Clone an existing repo from GitHub
bash
git clone https://github.com/your-org/your-repo.git
cd your-repo
With GitHub Enterprise, your URL will look like:

bash
git clone https://github.your-company.com/your-org/your-repo.git
4. The Basic Git Workflow
You’ll use these commands every day:[web:153][web:156]

4.1 Check repo status
bash
git status
Shows:

New (untracked) files

Modified files

Which branch you’re on

4.2 Stage changes
bash
git add GIT_TUTORIAL.md        # add a specific file
git add .                       # add everything in this folder
Staging = “I want these changes in my next snapshot.”

4.3 Commit changes (local snapshot)
bash
git commit -m "Add Git tutorial file"
A commit is a recorded checkpoint in your local repo.

4.4 Push changes to GitHub
bash
git push origin main
origin = remote name (default from git clone)

main = branch name (older repos use master)

5. Branching: Work Safely Without Breaking Main
Branches are parallel lines of development.

5.1 Create a new branch
bash
git checkout -b feature/add-readme
# or, in newer Git:
git switch -c feature/add-readme
5.2 Work on your branch
bash
# edit files...
git add .
git commit -m "Add initial README"
git push -u origin feature/add-readme
Then open a Pull Request (PR) on GitHub to merge into main.

6. Updating Your Local Repo
Stay in sync with the remote repository:[web:156]

bash
git pull origin main
This does:

fetch new commits from GitHub

merge them into your local main

7. Seeing History and Differences
7.1 Commit history
bash
git log
Useful flags:

bash
git log --oneline --graph --decorate --all
7.2 See what changed in a file
bash
git diff
git diff HEAD~1 HEAD   # last commit vs current
8. Working With GitHub Features (High Level)
When using GitHub Enterprise, you also benefit from:

Pull Requests – review and discuss changes before merging.

Actions (CI/CD) – run tests and deployments automatically when you push.

Security tools – CodeQL analysis, Dependabot updates, secret scanning, and security overview integrated into the repo.[web:154][web:156]

These are configured mostly on GitHub’s web UI or via YAML files in .github/workflows/.

9. Common Command Cheat Sheet
bash
# Setup
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Start
git init
git clone <url>

# Daily workflow
git status
git add <file>         # stage
git add .              # stage all
git commit -m "Message"
git push origin main

# Branching
git branch             # list branches
git switch -c <name>   # create & switch
git switch <name>      # switch
git push -u origin <name>

# Sync
git pull origin main

# Inspect
git log
git diff
10. Practice Exercises
Initialize a new repo in a test folder.

Create this file GIT_TUTORIAL.md, add some text, then:

bash
git add GIT_TUTORIAL.md
git commit -m "Add Git tutorial"
Create a new branch:

bash
git switch -c feature/update-tutorial
Edit this file (add a new section), then commit and push the branch.

Open a Pull Request in GitHub to merge feature/update-tutorial into main.

11. Where to Learn More
GitHub’s “Beginner Git commands you need to know” video[web:156]

Codecademy’s Learn Git interactive course[web:155]

You can extend this file as you learn. Every time you add something new, commit it—that’s you learning Git by doing.

text

You can save that as `GIT_TUTORIAL.md` (or `README.md` if you want it to show on the repo home), commit it, and you’ve already practiced the basics.
