Create GIT Repository
=====================

Initialize Repository Directory

git init [DirectoryName]

Create and initial a bare directory

git init --bare [DirectoryName]

# Clone/Copy existing Repository

Clone/Copy existing repository

git clone Source [http link to repository or local repository]

Clone/Copy existing repository into a specific directory

git clone [http link to repository or local repository] [DirectoryName]

Config Git Repository settings
==============================

Define user name for all commits on this repository

git config user.name "John Doe"

Define user name for current user on all commit statement on this repository

git config --global user.name "John Doe"

Define current user email on this repository

git config --global user.email "John@Doe"

Define shortcuts for git commands(commit,push,etc) on this repository

git config --global alias.<short-name> gitCommand

Git Add Command
===============

# Record changes for next commit

Add a file to repository

git add [fileName.extension]

Add a directory to repository

git add [DirectoryName]

Add files or directory to repository in an interactive staging manner

git add -p 

(press y/Y for Yes to add or n/N for No to ignore file)


Example 

create an initial commit of the current directory

git add .

git commit


Git Commit Command
==================

Commit repository that is in the staged snapshot (git add)

git commit

Commit repository that is in the staged snapshot with a commit message

git commit -m "hello messsage"

Commit a snapshot of all changes in the working directory.

git commit -a

To add to the last commit or ammend to the last commit

git commit -amend
 
Git Status Command
==================

show all files that have been added to the staged snapshot
git status. Shows all changes of all files being tracked by the repositories
(even uncommitted)

git status


Git diff command
================

# Track file(s) in working directory (more detailed git status) 
To show all files tracked changes

git diff

To show all files from a specific commit up current commit

git diff [$id]

To show file(s) changes between commits

git diff [$id1] [$id2]

Git Log Command
===============

show all commit statements

git log

show n number of commit statements

git log -n [number]


show commit statement to a single line

git log -oneline

To show change with diffs

git log -p [file] [path_to_file]


Git Show command
================

To show files affected by this commit

git show [$id]

To show a specific files affected by this commit

git show [$id]:[file]

Git Branch Command
==================

show all branches

git branch 

Create a branch

git branch [name]
 
Deleting a branch without any unmerged change (safe method)

git branch -d [name]

To force deleting a branch irrespective unmerged changes (unsafe method)

git branch -D [name]

To rename a branch

git branch -m <Newname>


Git Checkout Command 
====================

Uses.
The intended use is to traverse along the existing branch (master) or to spawn a new branch and also to traverse to
branch inside master branch.Discarding recent uncommits and Navigating to a different branch. Additionally used for 
detaching any commits or extracting a file from a previously committed state. 

To Extract file from a commit state

git checkout [$id] path_to_file

To detach a commit from the current the branch

git checkout [$id]

To update current change to the current repository branch

git checkout [ExistbranchName]

To create and checkout a new branch

git checkout -b [newBranch]

To return back to current branch

git checkout [master]

To create new branch from existing branch

git checkout -b [old] [new]

To create new branch base on the head branch

git checkout branch [new]

Git Reset command
=================

To discard uncommits and return to last commit state
To delete recent commits
git reset --hard

Git Merge Command
=================

To merge specified branch to the current branch
git merge [branchName]

Note that all of the commands presented below merge into the current branch. 
The current branch will be updated to reflect the merge, but the target 
branch will be completely unaffected. Again, this means that git merge is 
often used in conjunction with git checkout for selecting the current branch 
and git branch -d for deleting the obsolete target branch.

Git Revert Command
==================

To revert a specific commit

git revert [--no-edit] [$id]

To reverse commits previously made

git revert [--no-edit] HEAD

Git Remote Command
==================

Listing remote connections

git remote

same as (git remote)

git remote -v

Create a remote connections

git remote add [name] [url]

Remove a remote connections

git remote rm [RemoteName]

Rename remote connections

git remote rename [oldName] [newName]

Git Fetch Command
=================

Stores remote repositories commits into local repositories

git fetch [remoteConnection]

Stores remote repositories commits only from a specified branch into the local repositories

git fetch [remoteName] [branch]


Git Pull Command (fetch + merge rolled into one)
================================================

To fetch + merge remote repositories into local repositories

git pull [remote]

Git Push Command (the reverse to fetch)
=======================================

Stores local repositories commits to remote repositories

git push [remote] [branch]

Git RM Command 
==============

To delete a file from the repository

git rm [file] 

# Note
The git remote command lets you create, view, and delete connections to other repositories.
Remote connections are more like bookmarks rather than direct links into other repositories.
Instead of providing real-time access to another repository, they serve as convenient names
that can be used to reference a not-so-convenient URL.


Changes to the actual file such as delete, rename and addition require the Git Add command
to be called.

$id : notation used in this sheet to represent either a commit id, branch or a tag name

Steps to creating a repository from scratch

1)initialize repository

2)add files

3)commit repository

4)push repository to remote repository (optional)
