# Git Command Reference


## Cloning
- go to Kamino and provide your DNA
  - `git clone url/to/your/repository`


## Status Checking and Updating
- print out what's modified since last commit
  - `git status`

- fetch any info on changes from the cloud (doesn't modify your local files)
  - `git fetch`

- pull the changes from cloud to your local branch files
  - `git pull`
- push your local commits to cloud
  - `git push`


## Branching
- checkout a local branch (may not be up to date)
  - `git checkout name_of_branch`

- checkout a remote branch
  - `git fetch`
  - `git checkout name_of_branch`

- make a new local branch & sync with remote
  - `git checkout -b new_branch_name`
  - `git push --set-upstream origin new_branch_name`


## Stage Your Changes
- add the files or folders you want to be in the commit
  - `git add /path/to/file.vhd`
  - `git add /folder/you/want/to/add/*`

- add everything
  - `git add -A`

- see changes for an unstaged file
  - `git diff specific/file/you/want/to/check`

- see changes to all unstaged files files
  - `git diff`


## Undo-ing
- undo a local commit without changing files:
  - `git reset --soft HEAD^`

- unstage everything 
  - `git reset`

- undo your changes to a file
  - `git checkout -- path/to/file.txt`

- reset your local files back to last commit 
  - `git reset --hard`
  - `git clean -fd`


## Committing
- moving staged files into a commit with just summary message
  - `git commit -m "summary of what was changed in this commit"`

- more verbose commit that brings up your vim text editor or whatever you set it to 
  first line will be summary, rest of lines for more detailed description
  - `git commit`


## Merging
- pull latest master changes from cloud to your local branch
  - `git merge origin/master`


## Fixing Merge Conflicts
- Yeah, good luck with that.  Time to call a team meeting.


## Stashing
- stash away a copy of your changes locally so you can put them back later
  - `git stash`
- deploy your stashed changes
  - `git stash pop`
- delete your stash
  - `git stash drop`

## Tagging
tagging helps you label your commits as certain product releases, etc.


Creating a local tag: 
- `git tag -a v1.1 -m "this feature was when we added the blinky leds make people think people our product is cool"`

List local tags: 
- `git tag`

See more info about a specific tag
`git show v1.1`

Tag a previous commit (where abc1234 is the start of your commit checksum you want to tag):
- `git tag -a v1.0 abc1234 -m "Original Product Release"`

Push a tag to remote
- `git push origin v1.1`

Or push all tags
- `git push --tags`


# Terminology and References

  - local - your local files not on the cloud
  - remote - the cloud storage solution you chose. (bitbucket, github, etc)
  - origin - a local alias that points to some remote's URL (points to your repository on
      bitbucket you cloned from, unless you change it)

## Gitignore
- include a .gitignore file in your repo to tell git to ignore changes on files with certain patterns (assuming they're not already in your repo)
  - https://www.atlassian.com/git/tutorials/saving-changes/gitignore
