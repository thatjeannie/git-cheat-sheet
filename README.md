# Git Cheat Sheet

## Basic Tips with Commands

* Create and check out a new local branch:
  * `git checkout -b branch_name`

* Check out an existing branch OR `main`:
  * `git checkout branch_name` OR `git checkout main`

* Add changes (**IN**cluding new files, **EX**cluding `rm` or manually deleted files) to stage:
  * `git add .`

* Add changes (**EX**cluding new files, **IN**cluding `rm` or manually deleted files) to stage:
  * `git add -u`

* Add changes (**IN**cluding new files, **IN**cluding `rm` or manually deleted files) to stage:
  * `git add -A`

* Commit added changes (`-m` precedes the commit message):
  * `git commit -m 'commit message'`

* Pull main from origin:
  * `git pull origin main`

* See all remote branches
  * `git branch -r`

* Pull all remote branches
  * `git fetch`

* Pull a branch from origin:
  * `git pull origin branch_name`

* Pull someone else's remote branch and track it in a local branch:
  * `git fetch` then `git checkout branch_name` **NEW: This will pull all remote branches then set up a local branch to track the remote one.**
  * `git checkout -b branch_name origin/branch_name` **OLD: This will return a fatal error in git >1.6.6**

* Push local main to origin: **DANGER ZONE: Generally avoid this command. Use branching.**
  * `git push origin main`

* Push local branch to origin:
  * `git push origin branch_name`

* Delete a local branch: **DANGER ZONE: Be sure this is necessary before performing.**
  * `git branch -d branch_name`
  * This will possibly result in a fatal error because deleting = bad. To continue with delete anyway:
  * `git branch -D branch_name`

## Branching and Merging
* When a merge request is made, but hasn't been accepted, the branch will still receive any commits pushed to it while it's waiting to be merged.
* When you're ready to submit a merge request for a branch, switch to `main`, pull `main`, then switch back to your branch, merge `main` into that branch, push the branch, then submit merge request.
* Create new feature branch: `git checkout main`, `git checkout -b feature_branch_name`
* Push feature branch to origin: `git push origin feature_branch_name`

### Other Random Stuff From Mark

Install Git
```shell
sudo apt-get update
sudo apt-get install git
```

Stop tracking a tracked file:
```shell
git rm -r --cached filename.ext
```

Check origin URL:
```shell
git remote show origin
```

Remove origin
```shell
git remote rm origin
```

Add new origin
```shell
git remote add origin root@yoursite.com:path/to/gitfile/projectname.git
```

Clone a repo:
```shell
git clone root@yoursite.com:path/to/gitfile/projectname.git
```

Edit your .gitignore file
- Add all config files and nbproject folder to .gitignore

Merge main into feature branch:
```shell
git checkout feature-branch-name
git merge main
```

Delete a branch on origin:
```shell
git push origin --delete feature-branch-name
```

**Best Practices**
Branch naming convention:
- Separate words with hyphens ("-")
- Use descriptive branch names
- Use lowercase
- If there is a JIRA ticket for the issue / feature being addressed in the branch, include it at the beginning of the branch name
  - Example: "jira-1234-login-ui-fix"

Commit Messages:
- Keep your commit messages succinct yet descriptive
  - Example: "Fixed slider bug on index page"

Submitting a QA Request:
- Include the branch name at the top of the request description
  - Example: branch: colorscheme-tool-fix

Submitting a Merge Request:
- Include the JIRA ticket number in the merge request description
- Include the text: "passed QA"

Git Shell Tips:
- Tab Completion
  - To complete a git command without typing the entire command in manually, use tab completion
  - If a command name doesn’t complete, the characters you entered are not unique
    - In that case press the tab key twice in a row
  - Use the "up arrow" and "down arrow" keys to navigate through your command history
