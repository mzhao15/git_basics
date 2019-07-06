# **git_basics**

This article covers the basic operations of git and help beginners start their version control of projects.

## Check version
After installation of git on your machine, you can check the version of your git in the git bash
```
git --version
```

## Config git, set up the user name and email in git
```
git config --global user.name <your name>
git config --global user.email <your email>
```
You can check the config values by
```
git config --list
```

## Need help?
```
git help config
git config --help
```

## Get started (Two common scenerios)
- Initialize a repo from existing code

Simply run the init command within the directory from the terminal
```
git init
```
Then we can create a remote directory in any remote git server, such as github, gitlab, bitbucket and so. In order to link the local directory with the remote directory, we need to add the remote repository to the remote
```
git remote add origin <git repo url>
```
- Cloning a remote repo

We can use the following command to clone a remote repo to our local working directory
 ```
 git clone <url> <where to clone>
 ```

View information about the remote repository
```
git remote -v
```
List all branches
```
git branch -a
```

## Simple git workflow

1. Make changes in the local working directory
2. Before commit

- See tracked and untracked files in the directory
```git status```
- Check the changes in the files
```git diff```
- Add `gitignore` file (optional). 
```touch .gitignore```
In `gitignore`, simple put the names of the files and folders you don't want to track. For example,
```
.DS_Store
venv
.*pyc
```

3. Add files to staging area
```
git add -A
git status
```
`-A` means staging all modified files. You can also specify the file name to add the specific file.

4. Remove files from staging area
```
git reset <filename>
git status
```
If you omit `<filename>`, git will unstage all files.

5. Commit the changes
```git commit -m <commit message>```
Commit message needs to be detailed and concise. You can also use `git log` to show the details of the commit.

6. Push changes
```
git pull origin master
git push origin master
```
`origin` is the name/alias of the `remote` repository. `master` is the name of the `remote branch`. *Always `pull` first before you `push` changes to the remote* because your collaborators may have made changes to the remote repository and you want to make sure your local repository is up-to-date. Otherwise, you may produce conflicts when you `push`.


A quick recap of how git works:
```
git diff
git status
git add -A
git commit -m <commit message>
git pull origin master
git push origin master
```
