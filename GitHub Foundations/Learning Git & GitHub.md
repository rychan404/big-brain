
## Working with Git

### Understanding version control

- Version control
	- Track changes
	- Project history
	- Backup & restore
- Collaboration
	- Group changes
	- Share code
	- Who, what, when
- Different types (centralized & distributed)
- Centralized
	- Storage in centralized server
	- Tracked
	- Retrieved
	- Ex: Apache Subversion (SVN)
- Distributed
	- Cloning into own machines
	- Working copy (independently make changes to code)
	- Push/Pull to/from main repo

### What is Git?

- Version control
- Time machine
- Check points (commits)
- Multiverse (branches)
- Synchronize (merging)

### Setting up Git

- Git Config
	- `git config --global user.name "Your Name"`
	- `git config --global user.email "Your Email"`
- Staging Files
```
git add FILENAME
# git add -A
# git add .
git commit -m "First Commit"
```

### Understanding Git environments

- Git Information `git log`
	- Hash (unique ID), branch, author, email, date & commit message
- Git Environments
	- Working: files from last commit
	- Staging: queue changes before committing
	- Commit: new log entry w/ new hash created
- File States
	- Tracked: previous snapshot (commit you did)
		- Unmodified: files haven't changed
		- Modified: files have been changed
		- Staged
	- Untracked
	- View status by `git status`
- Restoring Files
```
git restore README.md
# git restore .
# git checkout .
# git restore --staged . (move out of staging)
# git restore -S .
```

### Ignoring Files

- Why Ignore Files?
	- Sensitive info
	- Personal notes
- Use .gitignore
```
.DS_Store
.vscode/
autentication.js
node_modules
notes/
**/*-todo.md
```
- Global Ignore File
	- Across all projects
	- `git config --global core.excludesfile [file]`
- Clearing the cache
	- `git rm -r --cached .`

### Deleting & renaming files

- Deleting
```
# Delete file from file system
git rm file # (already stages change)
```
- Renaming
```
# Rename files from file system (records as deletion & adding a new file)
git mv name new_name # (records as renamed & stages)
```

### Differences

- `git diff`
	- Shows difference b/w 2 files (modified vs. commits)
- `git log`
	- `git log --oneline`
		- Commits in order
		- Shows them all in single line

### Changing history

- Amending
```
git commit --amend
# git commit --ammend -m "New commit message" (modify message)
# git commit --amend --no-edit (uses message as last commit)
```
- Reset
	- Go back to previous commit
	- `git reset [hash]`
	- `git reset --hard [hash]`
		- Deletes all commits before specified hash
		- Gets rid of changes as well
- Rebasing
	- Take commits of 1 branch & apply to another
```
git rebase <branch>/<commit>
# git rebase --interactive <branch>/<commit>
# git rebase -i HEAD-# (move back a certain number of commits)
# git rebase -i --root (all commits)
```

### Branches

- Looking at Branches
	- `git branch`
- Copying a branch
```
git switch -c NAME
# git checkout -b NAME
```
- Merging
	- Merge to main by switching to main `git switch main` & merging from there
	- `git merge <branch>`
- Deleting a branch
```
git branch --delete NAME
# git branch -d NAME
# git branch -D NAME
```
- Git Flow
	- Feature/fix branch
	- Make changes
	- Merge to master
	- Delete old branch

### Merge conflicts

- Conflicts happen when merging 2 branches, u & someone else made changes to same file

### **(Extra)** Git stash & clean

- Stashing
	- Put away code temporarily
```
git stash
# git stash list
# git stash apply (get item from stash)
# git stash pop (remove stash)
```
- Cleaning
	- Remove all on-track files & directories from branch
```
git clean -n # dry run
git clean -d # directories
git clean -f # force
```


## Working with GitHub

### What is GitHub?

- Cloud repository
- Collaborative development
- Project management
Learn how to...
- Set up remote
- Push changes
- Fetch/pull

### Pushing to GitHub

- Remotes
```
git remote add NAME URL
# git remote remove NAME
# git rename OLDNAME NEWNAME
# git remote -v
```
- Git Push
```
git push REMOTE BRANCH
# git push --set-upstream-to origin main
git push -u origin main # --set-upstream
# git push --all
# git branch --set-upstream-to <origin/remote-branch>
```

### Understanding GitHub Flow

- GitHub Flow
	- Main branch
	- Feature branch
	- Commit & push
- Creating pull requests (move code from feature back to main)
	- Ask for Merge
	- Review requests
	- Feedback & comments
- Merging Pull Requests
	- Merge process
	- Review conflicts
	- Delete feature branch

### Learning Markdown

- Syntax: Headings
```
# Headline Level 1
Also Headline Level 1
=====================

## Headline Level 2
Also Headline Level 2
---------------------

### Headline Level 3
#### Headline Level 4
##### Headline Level 5
###### Headline Level 6
```
- Special Styles
```
**bold**
__bold__

*italic*
_italic_

~~strike through~~

> Quotation

--- Horizontal Rule
	*** Asteriks
	___ Underscores
```
- Lists
```
- Hyphens
* Asteriks
+ Plus sign

1. First ordered lsit item
	* Unordered sub-list
2. Numbers don't really matter
```
- Links
```
https://www.linkedin.com
[Website](https://www.linkedin.com "LinkedIn")

[LinkedIn]

[Learning][1]
[linkedin]: https://www.linkedin.com
[1]: https://www.linkedin.com/learning
```
- Images
```
![Tomolor](https//pixelprowess.com/i/stargazers/tomolor.png)

![Tomolor]
[Tomolor]: https//pixelprowess.com/i/stargazers/tomolor.png

# Image link
[![Tomolor](https//pixelprowess.com/i/stargazers/tomolor.png)](https://raybo.org)
```
- Code
	- 2 ticks for one line code
	- 3 ticks for multiline code

### GitHub Markdown additions

- Footnotes
```
This is a footnote[^1]. Another footnote[^2]

[^1]: My reference
[^2]: Another footnote
```
- Tables
```
| Left  | Center | Right   |
| ----  | :----: | ------: |
| One   | Two    | $1.00   |
| Three | Four   | $120.00 |
| Five  | Six    | $.99    |
```
- Task List
```
- [x] First
	- [x] One
	- [ ] Two
- [ ] Second
```