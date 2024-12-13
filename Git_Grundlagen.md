# Git and GitHub Guide for Beginner Developers

## Understanding Git and GitHub
**Git** is a distributed version control system that helps developers track changes in their codebase, collaborate with others, and manage different versions of code. **GitHub** is a web-based platform that hosts Git repositories and provides additional features such as issue tracking, project management, and collaboration tools.

## Local Branches vs. Remote Branches
- **Local Branch**: A branch that exists only on your local machine. Changes made in a local branch are not visible to others until they are pushed to a remote repository.
- **Remote Branch**: A branch that exists on a remote repository like GitHub. This is where you share your code with others and collaborate.

## Creating a Branch
Branches allow you to work on different features or bug fixes independently from the main codebase.

## Committing vs. Pushing
- **Commit**: Saves your changes locally. A commit creates a snapshot of your changes.
- **Push**: Uploads your local changes to a remote repository, making them visible to others.

## Pulling Changes from Others
To incorporate changes made by other developers into your local repository:

## Reverting Local Changes
If you need to undo local changes:

## Switching Branches with Local Changes
If you need to switch branches but have uncommitted changes:

~~~bash
# Create a new branch
git checkout -b feature-branch
# This creates and switches to a new branch named 'feature-branch'.

# Switch to an existing branch
git checkout main
# This switches back to the 'main' branch.

# Stage changes for commit
git add .
# This stages all the changes in your working directory for the next commit.

# Commit changes with a message
git commit -m "Add new feature"
# This commits the staged changes with a message describing what was done.

# Push changes to the remote repository
git push origin feature-branch
# This uploads your local 'feature-branch' to the remote repository.

# Fetch and merge changes from the remote repository
git pull origin main
# This fetches the latest changes from the 'main' branch on the remote repository and merges them into your current branch.

# Discard changes in a specific file
git checkout -- <filename>
# This discards changes in the specified file, reverting it to the last committed state.

# Discard all local changes (use with caution)
git reset --hard
# This discards all local changes, reverting all files to the last committed state.

# Stash your local changes
git stash
# This temporarily saves (stashes) your changes so you can switch branches.

# Switch to the desired branch
git checkout another-branch
# This switches to 'another-branch'.

# Apply stashed changes
git stash apply
# This reapplies the stashed changes to your working directory.
