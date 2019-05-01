# Cheat Sheet Git commands

## Command line instructions for ssh connectios.

You can also upload existing files from your computer using the instructions below.

### To stabilish a ssh connection:

    eval $(ssh-agent -s)  
    ssh-add ~/.ssh/[key_file]  

### Git global setup

    git config --global user.name "[your_git_user]"  
    git config --global user.email "[your_git_login_email]"  

### Create, locally, a new repository mirroring your remote repository

Create README.md or any other file(s) or folder (s)

    git clone git@gitlab.com:[path]/[project_name].git  
    cd [project_name]  
    touch README.md  
    git add README.md  
    git commit -m "add README"  
    git push -u origin [branch]  

### Push an existing folder (not yet a git repository) to your remote

    cd existing_folder  
    git init  
    git remote add origin git@gitlab.com:[path]/[project_name].git  
    git add .  
    git commit -m "Initial commit"  
    git push -u origin [branch]  

### Push an existing Git repository

    cd existing_repo  
    git remote rename origin old-origin  
    git remote add origin git@gitlab.com:[path]/[project_name].git  
    git push -u origin --all  
    git push -u origin --tags  