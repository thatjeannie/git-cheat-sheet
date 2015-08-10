# Git Cheat Sheet

## Basic Tips with Commands
* Create and check out a new local branch:
  * `git checkout -b branch_name`

* Check out an existing branch OR master:
  * `git checkout branch_name` OR `git checkout master`

* Add changes (INcluding new files, EXcluding `rm` or manually deleted files) to stage:
  * `git add .`

* Add changes (EXcluding new files, INcluding `rm` or manually deleted files) to stage:
  * `git add -u`

* Add changes (INcluding new files, INcluding `rm` or manually deleted files) to stage:
  * `git add -A`

* Commit added changes (`-m` precedes the commit message):
  * `git commit -m 'commit message'`

* Pull master from origin:
  * `git pull origin master`

* See all remote branches
  * `git branch -r`

* Pull all remote branches
  * `git fetch`

* Pull a branch from origin:
  * `git pull origin branch_name`

* Pull someone else's remote branch and track it in a local branch:
  * `git fetch` then `git checkout branch_name` **NEW: This will pull all remote branches then set up a local branch to track the remote one.**
  * `git checkout -b branch_name origin/branch_name` **OLD: This will return a fatal error in git >1.6.6**

* Push local master to origin: **DANGER ZONE: Generally avoid this command. Use branching.**
  * `git push origin master`

* Push local branch to origin:
  * `git push origin branch_name`

* Delete a local branch: **DANGER ZONE: Be sure this is necessary before performing.**
  * `git branch -d branch_name`
  * This will possibly result in a fatal error because deleting = bad. To continue with delete anyway:
  * `git branch -D branch_name`

## Branching and Merging
* When a merge request is made, but hasn't been fulfilled yet, any pushes made to the branch while it's waiting to be merged, will still receive any commits pushed to it.
* When you're ready to submit a merge request for a branch, switch to master, pull master, then switch back to your branch, merge master into that branch, push the branch, then submit merge request.
* Create new feature branch: `git checkout master` `git checkout -b feature_branch_name`
* Push feature branch to origin: `git push origin feature_branch_name`

### Other Random Stuff From Mark

// Install Git
sudo apt-get update
sudo apt-get install git

Stop tracking a tracked file:
git rm -r --cached filename.ext

Check origin URL:
git remote show origin

Remove origin
git remote rm origin

Add new origin
git remote add origin root@yoursite.com:path/to/gitfile/projectname.git

Clone a repo:
git clone root@yoursite.com:path/to/gitfile/projectname.git

// Edit your .gitignore file
Add all config files and nbproject folder to .gitignore

Merge master into feature branch:
git checkout feature-branch-name
git merge master

Delete a branch on origin:
git push origin --delete feature-branch-name

Best Practices
Branch naming convention

Always separate words with hyphens ("-").
Use descriptive branch names.
Use all lowercase.
If there is a jira ticket for the issue/feature being addressed in the branch, include it at the beginning of the branch name.

Examples:

"jira-1234-user-login-style-improvements"

Commit Messages:

Keep your commit messages succinct yet descriptive.

Example:
"Fixed slider bug on index page"

Submitting a QA Request
When submitting a QA request, please include the branch name at the top of the request description. Example:
branch: colorscheme-tool-improvements

Submitting a Merge Request
When submitting a merge request in GitLab, please include the following in the merge request description:
jira ticket number
the text: "passed QA"

Git Shell Tips

Tab Completion
To complete a git command without typing the entire command in manually, use tab completion.  If a command name doesn’t complete, the characters you entered are not unique. In that case press the tab key twice in a row.

Command History
Use the "up arrow" and "down arrow" keys to navigate through your command history.
