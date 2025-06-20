
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