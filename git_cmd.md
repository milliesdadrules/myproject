# **Basic git commands**
This is the basic git commands to help get you started with the vcs and collaborating with colleagues.
***
### Global config commands
Global setting's like user name and email are used to track who made the changes when code is being worked on by more than one person. The first two commands allow you to set the name and email is they are not already set (This can checked using the --list parameter)
```
git config --global user.name "James McNeil" 
git config --global user.email "jmcneil@collab.com"
git config --global --list
```
The config file is located in the home directory (~/.gitconfig) 

```
mcnei@laptop-cc1 MINGW64 /c/repos/myproject (master)
$ cat ~/.gitconfig
[user]
        name = James McNeil
        email = jmcneil@collab.com
```
***
### Initialise a repository
This allows us to take a local folder (collection of files) and initialise it as a git repo.

```
git init                        // turns location into a local git repository
git add <filename>              // adds files to the staging area to be tracked
git restore --staged <filename> // remove files from staging area 
git status                      // checks the status of file in staging area
git commit -m "Commit message"  // saves "snapshot" of file with an annotation of changes
```
***
### Making local repos remote repositories
Below will allow to take a local repository and add a remote push destination to share and allow for better team/community collaboration.
```
git remote -v                           // list remote push destinations
git remote add origin <repository uri>  // Add the git repo details
git branch -M master                    // specify the current branch
git push -u origin master               // push and remember branch to remote repo

git push        // push to remote repo (branch is remembered)
git pull        // pull from remote repo (branch remembered)
```
***

### Branching
When you want to add a feature or working on the code without making the changes to the main codebase then you can, take a copy of the codebase, or "branch" it off the master, and work on it in isolation. 
```
git branch <BranchName>     // creates a branch of the current codebase (current branch)
git checkout <BranchName>   // switches to different branch codebase (could be master or newly created branch)

git branch      // list local branches
git branch -r   // list remote branches
git branch -a   // list all branches

git branch -d <BranchName>              // Delete local branch
git push origin --delete <BranchName>   // Delete remote branch
```
### Merging
When working with a branch and you are happy to have the new working code become part of the master codebase then from the master you would merge in the feature branch.
```
git merge <BranchName> -m "Message to annotate the changes being made"
```
***
### Other useful git commands and stuff
```
git log                     // lists all the changes with some details
git checkout <commitHash>   // Switches to snapshots of codebase
.gitignore                  // A file containing list files/folders you wish to be excluded
```

To save logging in with usernames and passwords you can add your ssh public key to the remote git system.
```
ssh-keygen              // This creates the ssh public and private keys
~/.ssh                  // The keys are located in the .ssh folder (id_rsa / id_rsa.pub / known_hosts)
cat ~/.ssh/id_rsa.pub   // This displays the contents of the file public key that can be copied to you profile on the the remote git platform
```


