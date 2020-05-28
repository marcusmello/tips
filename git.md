# Cheat Sheet Git commands


## To stabilish a ssh connection

    eval $(ssh-agent -s)  
    ssh-add ~/.ssh/[key_file]  

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
