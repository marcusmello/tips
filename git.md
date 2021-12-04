# Cheat Sheet Git commands

## SSH

### To generate ssh keys

You can create and configure an ED25519 key with the following command:

    ssh-keygen -t ed25519 -C "<comment>"

The -C flag, with a quoted comment such as an email address, is an optional way to label your SSH keys.
You’ll see a response similar to:

    Generating public/private ed25519 key pair.
    Enter file in which to save the key (/home/user/.ssh/id_ed25519):

### To establish a connection

    eval $(ssh-agent -s)  
    ssh-add ~/.ssh/[key_file]  

You'll need to do this, for each terminal session, unless you add to a config file, in the same keys folder:

```sh
# GitLab.com
Host gitlab.com
Preferredauthentications publickey
IdentityFile ~/.ssh/gitlab

# GitHub.com
Host github.com
Preferredauthentications publickey
IdentityFile ~/.ssh/github
```

## Git global setup

    git config --global user.name "[your_git_user]"  
    git config --global user.email "[your_git_login_email]"  

## Create, locally, a new repository mirroring your remote repository

    git clone git@[your_git_host]:[path]/[project_name].git  
    cd [project_name]  
    touch README.md  
    git add README.md  
    git commit -m "add README"  
    git push -u origin [branch]  

## Push an existing folder (not yet a git repository) to your remote

    cd existing_folder  
    git init  
    git remote add origin git@[your_git_host]:[path]/[project_name].git  
    git add .  
    git commit -m "Initial commit"  
    git push -u origin [branch]  

## Push an existing Git repository

    cd existing_repo  
    git remote rename origin old-origin  
    git remote add origin git@[your_git_host]:[path]/[project_name].git  
    git push -u origin --all  
    git push -u origin --tags

## Git repository "inside" a git repository

    git submodule add <git_remote_url> <local path>

## Delete branch

### delete branch locally

    git branch -d localBranchName

### delete branch remotely

    git push origin --delete remoteBranchName

### Synchronize branch list

    git fetch -p

## Untrack ignored file

    git rm --cached <file_1> ... <file_n>

## Solve merge conflicts locally

### Step 1. Fetch and check out the branch for this merge request

    git fetch origin
    git checkout -b <issue_branch_name-merge-conflict> origin/<issue_branch_name>

### Step 2. Review 

Review, save and commit the changes locally

### Step 3. Merge the branch and fix any conflicts that come up

    git fetch origin
    git checkout <issue_branch_name>
    git merge --no-ff <issue_branch_name-merge-conflict>

### Step 4. Push the result of the merge to your issue branch

    git push origin <issue_branch_name>
