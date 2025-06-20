
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

## What is Git?

- Version control
- Time machine
- Check points (commits)
- Multiverse (branches)
- Synchronize (merging)

## Setting up Git

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
	- Tracked: previous snapshot