# Gits
## Before start
 please read [Generate new SSH Key and add it to agend](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) and [Add the key to your github](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account). Otherwise you may see this [permission-denied-error](https://stackoverflow.com/questions/12940626/github-error-message-permission-denied-publickey)

## Setup a new repo
This is summarized from this [blog](https://kbroman.org/github_tutorial/pages/init.html).
* Go to github.com
* Log in to your account 
* Click the new repository button and make a nice name
* Locally, make dir for your project 
* git init
* make README.md and edit it
* git add --a
* git commit --m "Add README"
* git remote add origin git@github.com:user_name/new_repo
* git push -u origin master
```git
git init
vi README.md
git add --a
git commit --m "Add README"
git remote add origin git@github.com:HJSang/EatGit
git push -u origin master
```
## Add Git Ignore Files
This is summarized from [ignore files](https://help.github.com/en/github/using-git/ignoring-files).
* Create a .gitignore file for your repo
```
touch .gitignore
```
* Edit and configure your .gitignore file. For example, see [this file](https://gist.github.com/octocat/9257657)
* If you want to ignore a file that is already checked in, you must untrack the file before you add a rule to ignore it. From your terminal, untrack the file.
```git
git rm --cached FILENAME
```
## Add files to staging area
```git
git add -A
git status
```
* -A is to add everything 
* if you want to remove file from the stage area, you can use 
```git
git reset
git status
```

## Clone
This is summarized from [Cloning a repository](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository).
```git
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY .
```
clone the remote address to the locale dir. 

## Sync
This is summarized from this [blog](https://www.atlassian.com/git/tutorials/syncing).
* git remote: The git remote command lets you create, view, and delete connections to other repositories.
```git 
git remote add <name> <url>
```
Create a new connection to a remote repository. After adding a remote, you’ll be able to use <name> as a convenient shortcut for <url> in other Git commands.
```git
git remote rm <name>
git remote rename <old_name> <new_name>
```
* git fetch: The git fetch command downloads commits, files, and refs from a remote repository into your local repo. Fetching is what you do when you want to see what everybody else has been working on.
```git
git fetch <remote>
```
Fetch all of the branches from the repository. This also downloads all of the required commits and files from the other repository.
```git
git fetch <remote> <branch>
```
Same as the above command, but only fetch the specified branch.
```git
git fetch --all
```
A power move which fetches all registered remotes and their branches:
```git
git ftech --dry-run
```
The --dry-run option will perform a demo run of the command. I will output examples of actions it will take during the fetch but not apply them.

Git fetch examples:
```git
git remote add coworkers_repo git@bitbucket.org:coworker/coworkers_repo.git
git fetch coworkers feature_branch
git checkout coworkers/feature_branch
git checkout -b local_feature_branch 
```

Synchronize origin with git fetch:
```git
git fetch origin
```


