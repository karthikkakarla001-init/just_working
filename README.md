Important Git Commands and Usage

This section covers commonly used Git commands and when to use them.

1. Clone a Repository

Clone a remote repository to your local machine.

git clone <repository-url>

Example:

git clone https://github.com/username/project.git
2. Check Repository Status

View modified, staged, and untracked files.

git status
3. Check Available Branches

View local branches:

git branch

View both local and remote branches:

git branch -a
4. Create a New Branch

Create a new local branch:

git branch <branch-name>

Example:

git branch feature-login

Create and switch to the new branch:

git switch -c <branch-name>

Example:

git switch -c feature-login
5. Switch Between Branches

Switch to an existing branch:

git switch <branch-name>

Example:

git switch main

Older Git versions may use:

git checkout <branch-name>
6. Get Latest Remote Information

Download the latest branch and commit information from the remote repository without changing your working files:

git fetch origin

If a branch was created on GitHub after cloning the repository:

git fetch origin
git switch <branch-name>
7. Stage Changes

Stage all modified and new files:

git add .

Stage a specific file:

git add <file-name>

Example:

git add README.md
8. Commit Changes

Save staged changes to the local Git repository:

git commit -m "<commit-message>"

Example:

git commit -m "Update README documentation"

A commit exists only in the local repository until it is pushed.

9. Push Changes to GitHub

Push local commits to a remote branch:

git push origin <branch-name>

Example:

git push origin feature-login

For the first push of a newly created branch:

git push -u origin <branch-name>

Example:

git push -u origin feature-login

The -u option connects the local branch to the remote branch. After that, future pushes can usually be done with:

git push
10. Pull Latest Changes

Download and merge the latest changes from the remote branch:

git pull origin <branch-name>

Example:

git pull origin main

If the local branch is already tracking the remote branch:

git pull
11. View Commit History

View previous commits:

git log

For a shorter view:

git log --oneline
12. View Changes

View changes that have not yet been staged:

git diff

View staged changes:

git diff --staged
13. Remove a File

Remove a file from the project and stage the deletion:

git rm <file-name>

Example:

git rm old-file.txt
14. Rename or Move a File
git mv <old-name> <new-name>

Example:

git mv old.txt new.txt
15. Merge a Branch

First switch to the branch that should receive the changes:

git switch main

Then merge another branch into it:

git merge <branch-name>

Example:

git merge feature-login
16. Delete a Local Branch
git branch -d <branch-name>

Example:

git branch -d feature-login

Force deletion if necessary:

git branch -D <branch-name>
17. Delete a Remote Branch
git push origin --delete <branch-name>

Example:

git push origin --delete feature-login
Common Git Workflow

A typical development workflow looks like this:

# Clone repository
git clone <repository-url>

# Enter project directory
cd <project-directory>

# Get latest remote information
git fetch origin

# Create and switch to a feature branch
git switch -c feature-branch

# Make code changes

# Check changed files
git status

# Stage changes
git add .

# Commit changes locally
git commit -m "Add new feature"

# Push branch to GitHub
git push -u origin feature-branch

For future changes on the same branch:

git add .
git commit -m "Update feature"
git push
Local Commit vs Remote Push

A commit and a push are different operations.

Working Files
     |
     | git add
     v
Staging Area
     |
     | git commit
     v
Local Repository
     |
     | git push
     v
Remote Repository (GitHub)
git commit
git commit -m "message"

Saves the changes to the Git history on your local computer.

git push
git push origin <branch-name>

Uploads your local commits to the remote repository.

Example:

git add .
git commit -m "Fix login issue"
git push origin feature-login

The changes are available on GitHub only after the git push command completes successfully.
