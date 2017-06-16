# Git and GitHub Practice

Here is everything I have learned about Git:

## 3 Git States:
1. Working directory (where we edit and work in our projects)
2. Staging area (We decided which files are ready to go to the third state and which are not) 
3. Repository (where is located the record of all of our project)


## Basic Comands:
`$ git init` => Initialize an empty repository   
`$ git status` => Determine the current state of the project   
`$ git add` => Move all your changes since your last commit to the staging area  
`$ git commit -m "first commit"` => Store the saved changes in the repository and add a message "first commit"  
`$ git log` => how a list of all the commits that have been made 
`$ git remote add origin [SSH key - something like git@github.com…]` => to add a remote repository  
`$ git push -u origin master` => to push it to master  
`$ git pull origin master` => Take a git project from GitHub to your local machine to work on it  
`$ git help` => To get help

### Branches
`$ git checkout -b <branch_name>` => To create a new branch   
`$ git branch` => To list all the branches  
`$ git checkout <branch_name` => to change of branches  
`$ git branch -d <branch_name>` => Delete a branch  
`$ git branch -a` => It show us the hidden branches

### Git Reset & amend
`$ git reset --soft` => el más sencillo ya que no toca el working area, es decir nuestro código   
`$ git reset --mixed` => este git reset borra el Staging Area sin tocar el working area  
`$ git reset --hard` => el git más peligroso porque borra todo, TODO!
`$ git commit --amend -m <new message"` => to change the message of a commit
After making an amend, it's necessary to `$ git push origin master -f` to force the changes (git knows is the same commit)

### Git remote
`$ git remote -v` => To find the remote conection of the repository
`$ git remote remove origin` => To delete the remote connection
`$ git remote add origin [https://github.com...]` => To add a new connection to a remote repository

### Merging
`$ git merge <branch_to_be_merged>` => To merge a branch

### Rebasing
`$ git rebase <branch_to_be_rebased>` => Taking all the changes that were made to one branch and reapplying them on another.

La ventaja es que hay una historia de commits más limpia que cuando se hace merge.

Rebasing reproduce los cambios de un commit a otro  en el orden en que fueron introducidos. Merging toma los puntos finales y los fusiona.   

*STEPS*

`Delete conflicts`   
`$ git add `   
`$ git rebase --continue`

# GitHub
ISSUES: they are a way to continue, improve or solve an error in our repositories.

LABELS: a way to organize different tipes of problems

`$ git clone [repository]` => To clone a remote repository

### Tags
TAGS LIGERAS: `$ git tag v1.0`   
TAGS ANOTADAS: `$ git tag -a v1.0 -m "message"`  
TAGS ESPECIFICAS DE UN COMMIT: `$ git tag -a v0.1 -m "message" [SHA]`

Para subir un tag a GitHub: `$ git push origin v1.0`  
Y si tenemos muchas tags: `$ git push origin --tags`

## Workflow
Own projects, projects in teams, another's person project.

You can create a **new organization** for different people to work on a repository

**Git Fetch**  
`$ git fetch origin` => To pass the commits from a remote repository to the hidden branch origin/master

`$ git merge origin/master` => to have the commit from the hidden branch origin/master to our local repository

**Fork** [When we are not colaborators]  

 When you fork a project, you download your forked project not the original!

`$ git fetch upstream` => to be updated with the original repository (it's a hidden branch)  

`$ git fetch orign` => in our forked repository, we will have this hidden branch, to be updated with our local forked repository.

When we make a change in our forked reposotory  
`Create the change`  
`$ git add .`  
`$ git commit -m "message"`  
`$ git push origin <branch_name>`  
`new pull request`  
`create new pull request`  