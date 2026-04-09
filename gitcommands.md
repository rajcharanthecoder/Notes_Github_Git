# Everyday Git and GitHub Commands

## 1. git init

**Description:** Initialize a new Git repository in the current directory.

**Use case:** Used when starting a new project or when you want to start tracking changes in an existing directory that isn't already a Git repository.

**Example:**
```
mkdir my-new-project
cd my-new-project
git init
# Creates a .git directory to track changes
```

## 2. git status

**Description:** Show the status of the working directory and staging area.

**Use case:** Check which files are modified, staged, or untracked before committing changes.

**Example:**
```
git status
# Output shows:
# On branch main
# Changes not staged for commit:
#   modified:   file.txt
# Untracked files:
#   newfile.txt
```

## 3. git add

**Description:** Add file(s) to the staging area.

**Use case:** Prepare files for the next commit by staging them.

**Examples:**
```
git add file.txt          # Stage a specific file
git add .                 # Stage all files in current directory
git add -A                # Stage all files including deleted ones
git add *.txt             # Stage all .txt files
```

## 4. git commit

**Description:** Record changes to the repository with a commit message.

**Use case:** Save staged changes as a snapshot in the repository history.

**Examples:**
```
git commit -m "Add new feature"              # Commit with message
git commit -am "Fix bug in login"            # Add all modified files and commit
git commit --amend -m "Updated commit message"  # Amend last commit message
```

## 5. git log

**Description:** Show commit history.

**Use case:** View the history of commits, authors, dates, and messages.

**Examples:**
```
git log                    # Full commit history
git log --oneline          # Compact one-line per commit view
git log --graph --oneline  # Show branch/merge history graphically
git log -5                 # Show last 5 commits
git log --author="John"    # Show commits by specific author
```

## 6. git diff

**Description:** Show differences between files or commits.

**Use case:** See what changes have been made before staging or committing.

**Examples:**
```
git diff                  # Changes in working directory vs last commit
git diff --staged         # Changes in staging area vs last commit
git diff HEAD~1           # Changes between current and previous commit
git diff branch1..branch2 # Differences between two branches
```

## 7. git branch

**Description:** List, create, or delete branches.

**Use case:** Manage branches in your repository.

**Examples:**
```
git branch                # List all local branches
git branch -a             # List all branches (local and remote)
git branch new-feature    # Create a new branch
git branch -d old-branch  # Delete a merged branch
git branch -D force-delete # Force delete unmerged branch
```

## 8. git checkout

**Description:** Switch branches or restore files.

**Use case:** Move between branches or restore files to their committed state.

**Examples:**
```
git checkout main         # Switch to main branch
git checkout -b feature   # Create and switch to new branch
git checkout -- file.txt  # Restore file.txt to last commit state
git checkout commit-hash  # Checkout specific commit (detached HEAD)
```

## 9. git merge

**Description:** Merge a branch into the current branch.

**Use case:** Combine changes from different branches.

**Example:**
```
git checkout main
git merge feature-branch
# Merges feature-branch into main
# If conflicts occur, resolve them manually
```

## 10. git rebase

**Description:** Reapply commits on top of another base commit.

**Use case:** Clean up commit history or integrate changes from another branch.

**Examples:**
```
git rebase main           # Rebase current branch onto main
git rebase -i HEAD~3      # Interactive rebase last 3 commits
git rebase --continue     # Continue after resolving conflicts
```

## 11. git remote add

**Description:** Add a remote repository.

**Use case:** Connect your local repository to a remote repository (like on GitHub).

**Example:**
```
git remote add origin https://github.com/user/repo.git
# Adds GitHub repo as 'origin' remote
```

## 12. git clone

**Description:** Clone a repository into a new directory.

**Use case:** Download a copy of an existing repository.

**Example:**
```
git clone https://github.com/user/repo.git
# Downloads the repo to a new directory
git clone https://github.com/user/repo.git my-folder
# Clones into 'my-folder' directory
```

## 13. git push

**Description:** Push local commits to a remote repository.

**Use case:** Share your local commits with others or backup to remote.

**Examples:**
```
git push origin main      # Push main branch to origin
git push -u origin feature # Push and set upstream for feature branch
git push origin --delete branch # Delete remote branch
```

## 14. git pull

**Description:** Fetch and merge changes from remote repository.

**Use case:** Update your local repository with remote changes.

**Examples:**
```
git pull origin main      # Pull and merge from origin/main
git pull --rebase origin main # Pull and rebase instead of merge
```

## 15. git fetch

**Description:** Download objects and refs from remote repository.

**Use case:** Get latest changes from remote without merging.

**Example:**
```
git fetch origin          # Fetch all branches from origin
git fetch origin main     # Fetch specific branch
# Then you can merge or compare locally
```

## 16. git restore

**Description:** Restore files to their committed state.

**Use case:** Undo changes in working directory or staging area.

**Examples:**
```
git restore file.txt      # Restore file.txt to last commit
git restore --staged file.txt # Unstage file.txt
git restore --source=HEAD~1 file.txt # Restore to specific commit
```

## 17. git reset

**Description:** Reset current HEAD to specified state.

**Use case:** Undo commits or unstage changes.

**Examples:**
```
git reset HEAD file.txt   # Unstage file.txt
git reset --soft HEAD~1   # Undo last commit, keep changes staged
git reset --mixed HEAD~1  # Undo last commit, keep changes unstaged
git reset --hard HEAD~1   # Undo last commit, discard all changes
```

## 18. git revert

**Description:** Create new commit that undoes changes from previous commit.

**Use case:** Undo a commit without rewriting history.

**Example:**
```
git revert abc123         # Create new commit that undoes commit abc123
git revert -m 1 def456    # Revert a merge commit
```

## 19. git stash

**Description:** Stash current changes for later use.

**Use case:** Temporarily save uncommitted changes when switching branches.

**Examples:**
```
git stash                 # Stash current changes
git stash save "work in progress" # Stash with message
git stash list            # List all stashes
git stash apply           # Apply latest stash
git stash pop             # Apply and remove latest stash
git stash drop            # Delete latest stash
```

## 20. git tag

**Description:** Create, list, or delete tags.

**Use case:** Mark specific points in history (like releases).

**Examples:**
```
git tag v1.0              # Create lightweight tag
git tag -a v1.0 -m "Release version 1.0" # Annotated tag
git tag -l               # List all tags
git tag -d v1.0          # Delete tag
```

## 21. git config

**Description:** Get and set repository or global options.

**Use case:** Configure Git settings like user name and email.

**Examples:**
```
git config --global user.name "John Doe"
git config --global user.email "john@example.com"
git config --list         # Show all config settings
git config --global core.editor "code" # Set VS Code as default editor
```

## 22. git blame

**Description:** Show who last modified each line of a file.

**Use case:** Find out who made specific changes and when.

**Example:**
```
git blame file.txt        # Show blame for file.txt
git blame -L 10,20 file.txt # Show blame for lines 10-20
```

## 23. git cherry-pick

**Description:** Apply changes from specific commits.

**Use case:** Apply individual commits from one branch to another.

**Example:**
```
git cherry-pick abc123    # Apply commit abc123 to current branch
git cherry-pick abc123 def456 # Apply multiple commits
```

## GitHub CLI Commands

## 24. gh repo clone

**Description:** Clone a GitHub repository.

**Use case:** Download a GitHub repository to your local machine.

**Example:**
```
gh repo clone user/repo
# Equivalent to: git clone https://github.com/user/repo.git
```

## 25. gh repo create

**Description:** Create a new repository on GitHub.

**Use case:** Start a new project on GitHub.

**Example:**
```
gh repo create my-new-repo --public
# Creates a public repository and initializes it locally
```

## 26. gh pr create

**Description:** Create a pull request on GitHub.

**Use case:** Propose changes to a repository.

**Example:**
```
gh pr create --title "Add new feature" --body "This adds a new feature"
# Creates a PR from current branch to default branch
```

## 27. gh pr list

**Description:** List pull requests in a repository.

**Use case:** See open pull requests.

**Example:**
```
gh pr list                # List all PRs
gh pr list --state closed # List closed PRs
```

## 28. gh pr checkout

**Description:** Checkout a pull request locally.

**Use case:** Work on or review a pull request.

**Example:**
```
gh pr checkout 123        # Checkout PR #123
```

## 29. gh issue list

**Description:** List issues in a repository.

**Use case:** See open issues or tasks.

**Example:**
```
gh issue list             # List all issues
gh issue list --assignee @me # List issues assigned to you
```

## 30. gh issue create

**Description:** Create a new issue on GitHub.

**Use case:** Report bugs or request features.

**Example:**
```
gh issue create --title "Bug report" --body "There's a bug in..."
# Opens editor to write detailed issue description
```

## Additional Useful Commands

## 31. .gitignore

**Description:** Specify files Git should ignore.

**Use case:** Prevent unwanted files from being tracked.

**Example:**
Create a `.gitignore` file with:
```
*.log
node_modules/
.DS_Store
```

## 32. git reflog

**Description:** Show reference log (history of HEAD changes).

**Use case:** Recover lost commits or branches.

**Example:**
```
git reflog               # Show recent HEAD changes
git checkout HEAD@{2}    # Go back 2 steps in reflog
```

## 33. git clean

**Description:** Remove untracked files from working directory.

**Use case:** Clean up temporary or generated files.

**Examples:**
```
git clean -n             # Show what would be removed
git clean -f             # Remove untracked files
git clean -fd            # Remove untracked files and directories
```

## 34. git bisect

**Description:** Find the commit that introduced a bug.

**Use case:** Debug when a bug was introduced.

**Example:**
```
git bisect start
git bisect bad           # Mark current commit as bad
git bisect good abc123   # Mark commit abc123 as good
# Git will help you find the bad commit
```

## 35. git submodule

**Description:** Manage submodules (repositories within repositories).

**Use case:** Include other Git repositories as subdirectories.

**Examples:**
```
git submodule add https://github.com/user/lib lib/
git submodule update --init --recursive
```

## 36. git archive

**Description:** Create an archive of files from a named tree.

**Use case:** Create zip/tar files of your repository at a specific point.

**Example:**
```
git archive --format=zip --output=release.zip HEAD
# Create zip archive of current HEAD
```

## 37. git worktree

**Description:** Manage multiple working trees.

**Use case:** Work on multiple branches simultaneously.

**Example:**
```
git worktree add ../feature-branch feature
# Creates new worktree for 'feature' branch
```

## 38. git rerere

**Description:** Reuse recorded resolution of conflicted merges.

**Use case:** Automatically resolve recurring merge conflicts.

**Example:**
```
git config --global rerere.enabled true
# Enable reuse of recorded resolutions
```

## 39. git fsck

**Description:** Check repository for errors.

**Use case:** Verify repository integrity.

**Example:**
```
git fsck                 # Check for corrupted objects
```

## 40. git gc

**Description:** Clean up unnecessary files and optimize repository.

**Use case:** Maintain repository performance.

**Example:**
```
git gc                   # Garbage collect and optimize
```
