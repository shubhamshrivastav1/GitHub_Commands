Git & GitHub — Easy Commands & Uses
1. Git Version
```bash
git --version
```
Use: Check if Git is installed.
Remember: `version = Git installed?`
---
2. Git Configuration
Set name
```bash
git config --global user.name "Your Name"
```
Use: Set your name for Git commits.
Check name
```bash
git config --global user.name
```
Use: Check your Git name.
Set email
```bash
git config --global user.email "your@email.com"
```
Use: Set your email for Git commits.
Check email
```bash
git config --global user.email
```
Use: Check your Git email.
Set VS Code as editor
```bash
git config --global core.editor "code --wait"
```
Use: Use VS Code when Git needs an editor.
Handle line endings
```bash
git config --global core.autocrlf "input"
```
Use: Handle line-ending differences.
Remember: `git config = Git settings`
---
3. Start Git
```bash
git init
```
Use: Turn a normal project folder into a Git repository.
Remember: `init = Start Git`
---
4. Check Project Status
```bash
git status
```
Use: See what is happening in your project.
It shows:
Modified files
Untracked files
Staged files
Current branch
Remember: `status = What changed?`
---
5. Add Files
Add one file
```bash
git add file.txt
```
Use: Add one file to the staging area.
Add all files
```bash
git add .
```
Use: Add all changed files to staging.
Remember: `add = Prepare for commit`
---
6. Commit
```bash
git commit -m "Add login page"
```
Use: Save your staged changes as a checkpoint.
Remember: `commit = Save checkpoint`
---
7. See History
Full history
```bash
git log
```
Use: See commit history.
Short history
```bash
git log --oneline
```
Use: See commits in one-line format.
History with branch graph
```bash
git log --oneline --graph --all
```
Use: See commits and branches visually.
Remember: `log = History`, `graph = Branch map`
---
8. Branch Commands
See branches
```bash
git branch
```
Use: Show local branches.
Create branch
```bash
git branch feature/navbar
```
Use: Create a new branch.
It does not switch to it.
Switch branch
```bash
git switch feature/navbar
```
Use: Move to another branch.
Create + switch
```bash
git switch -c feature/navbar
```
Use: Create a new branch and immediately switch to it.
Remember: `-c = Create`
Create/switch with `-C`
```bash
git switch -C feature/navbar
```
Use: Create/switch to the branch; if it already exists, reset it to the current starting point.
Warning: Use `-C` carefully.
---
9. Merge
```bash
git switch main
git merge feature/navbar
```
Use: Bring changes from `feature/navbar` into `main`.
Remember: `merge = Combine`
Important: First switch to the branch that should RECEIVE the changes.
---
10. Fast-Forward Merge
Use: When the current branch has no separate new commits, Git can simply move the branch pointer forward.
Remember:  
No extra work → Pointer moves forward → Fast-forward
---
11. Three-Way Merge
Use: When both branches have their own commits.
Git compares:
Common ancestor
Current branch
Other branch
Remember:  
2 branches + 1 common ancestor = Three-way merge
---
12. Merge Conflict
A conflict happens when Git cannot decide which change to keep.
Usually happens when two branches change the same line.
VS Code commonly gives:
Accept Current Change → Keep your change
Accept Incoming Change → Keep other branch's change
Accept Both Changes → Keep both
After fixing:
```bash
git add .
git commit -m "Resolve merge conflict"
```
Remember:  
Current = Mine  
Incoming = Theirs  
Both = Both
Conflict flow
```text
Merge
 ↓
Conflict
 ↓
Open file
 ↓
Fix code
 ↓
Save
 ↓
git add .
 ↓
git commit
```
---
13. Squash
Squash = Combine many commits into one clean commit.
```text
Commit 1
Commit 2
Commit 3
Commit 4
      ↓
One clean commit
```
Remember: Many → One
---
14. Rebase
```bash
git switch feature
git rebase main
```
Use: Put your feature commits on top of the latest `main`.
Remember:
Merge = Join
Rebase = Move my work on top
Warning: Rebase can rewrite commit history, so use it carefully on shared branches.
---
15. Stash
```bash
git stash
```
Use: Temporarily save unfinished changes.
Remember: `stash = Keep unfinished work aside`
Stash pop
```bash
git stash pop
```
Use: Bring stashed changes back and remove that stash entry.
Remember: `pop = Bring back + remove stash`
Stash apply
```bash
git stash apply
```
Use: Bring stashed changes back without deleting the stash entry.
Remember: `apply = Bring back, keep stash`
Stash clear
```bash
git stash clear
```
Use: Delete all stash entries.
Important: If you already used `git stash apply`, then `git stash clear` does not delete the changes already applied to your working directory. It only deletes the saved stash entries.
Remember: `clear = Delete all stash`
---
16. Remote
```bash
git remote -v
```
Use: Check connected remote repositories.
Usually the remote name is:
```text
origin
```
Remember: `remote = Online repository connection`
---
17. Clone
```bash
git clone <repository-url>
```
Use: Copy an existing GitHub repository to your computer.
Remember: GitHub → Computer = Clone
---
18. Fetch
```bash
git fetch
```
Use: Get information about new remote changes without automatically merging them into your current branch.
Remember: Fetch = Check/Get remote updates
---
19. Pull
```bash
git pull
```
Use: Get remote changes and integrate them into your current branch.
Simple idea:
```text
git pull ≈ git fetch + integration
```
Remember: Pull = Bring changes into my branch
---
20. Push
```bash
git push
```
Use: Send your local commits to the remote repository.
Remember: Local → GitHub = Push
First push with `-u`
```bash
git push -u origin main
```
Use: Push `main` to GitHub and set the upstream/tracking connection.
After that:
```bash
git push
```
is usually enough.
You can also use:
```bash
git push origin main
```
Remember: `-u = Link local branch with remote branch`
---
21. Fetch vs Pull vs Push
Command	Simple meaning
`git fetch`	Get remote information
`git pull`	Get + integrate remote changes
`git push`	Send local commits to remote
Super easy
```text
FETCH = Get information
PULL  = Bring changes
PUSH  = Send changes
```
---
22. Fetch + Manual Merge
```bash
git fetch origin
```
Then check:
```bash
git log --oneline --graph --all
```
Then merge:
```bash
git merge origin/main
```
Use: Get remote changes first, inspect them, then manually merge them.
Remember: Fetch → Check → Merge
---
23. Revert
```bash
git revert <commit-id>
```
Use: Undo the effect of a previous commit by creating a new commit.
Remember: Revert = Undo with a new commit
---
24. Reset
Soft reset
```bash
git reset --soft HEAD~1
```
Use: Move back one commit while keeping changes staged.
Mixed reset
```bash
git reset --mixed HEAD~1
```
Use: Move back one commit and keep changes in the working directory, but unstaged.
Hard reset
```bash
git reset --hard HEAD~1
```
Use: Move back one commit and discard uncommitted changes.
Warning: Be very careful with `--hard`.
Remember:
Revert = Undo with a new commit
Reset = Move history back
---
25. Delete Branch
Normal delete
```bash
git branch -d feature/navbar
```
Use: Delete a local branch, normally after it has been merged.
`-d = delete`
Force delete
```bash
git branch -D feature/navbar
```
Use: Force delete a branch even if it has unmerged work.
Warning: Use `-D` carefully.
`-D = Force delete`
---
Complete Git Workflow
When working on a new feature:
```bash
git switch main
git pull
git switch -c feature/navbar

# Write code

git status
git add .
git commit -m "Add navbar"
git push -u origin feature/navbar

# After review/merge, update main

git switch main
git pull
git merge feature/navbar
git push
git branch -d feature/navbar
```
---
Most Important Commands for Beginners
```bash
git status
git add .
git commit -m "message"
git branch
git switch main
git switch -c feature/name
git merge feature/name
git pull
git push
git fetch
```
---
Final Memory Sheet
```text
git --version
→ Check Git version

git init
→ Start Git

git status
→ Check what changed

git add .
→ Prepare changes

git commit -m "message"
→ Save checkpoint

git log
→ See history

git log --oneline
→ Short history

git log --oneline --graph --all
→ See branch/commit graph

git branch
→ See branches

git branch name
→ Create branch

git switch name
→ Change branch

git switch -c name
→ Create + change branch

git merge name
→ Combine branch

git rebase main
→ Put work on latest main

git stash
→ Keep unfinished work aside

git stash pop
→ Bring it back + remove stash

git stash apply
→ Bring it back + keep stash

git stash clear
→ Delete all stashes

git remote -v
→ Check remote

git clone URL
→ GitHub → Computer

git fetch
→ Get remote information

git pull
→ Get + integrate remote changes

git push
→ Local → GitHub

git push -u origin main
→ First push + link branches

git revert ID
→ Undo with new commit

git reset
→ Move history back

git branch -d name
→ Delete branch

git branch -D name
→ Force delete branch
```
One-line Git Memory
> **STATUS → ADD → COMMIT → BRANCH → SWITCH → MERGE → PULL → PUSH**
