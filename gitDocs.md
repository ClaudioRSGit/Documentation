# First Configs
```bash
git config --global user.name "nome"
git config --global user.email "email@email.com"
```
<hr>

# Iniciate a repo

```bash
git init
```
<hr>

# Clone repo

```bash
git clone url
```
<hr>

# Branches

```bash
git branch
```       
> list every branch on the repo 

```bash
git branch branchName
```       
> create new branch

```bash
git checkout anotherBranch
```       
> change branch

```bash
git checkout -b anotherBranchButNew
```       
> create new branch and change

```bash
git branch -d branchIsGone
```       
> delete branch after commit

```bash
git branch -D branchIsGoneButForced
```       
> force a branch delete

<hr>

# Working with changes

```bash
git status
```       
> show all the changes

```bash
git add test.txt
```       
> add to staging area

```bash
git add .
```       
> add every change to staging area

```bash
git reset -- test.txt
```       
> removes test.txt from staging area

```bash
git revert
```       
> undo the last commit

```bash
git commit -m "message"
```       
> commits every change on staging area with a message

<hr>

# Merging and Conflicts

```bash
git merge aRandomBranch
```       
> merges a branch with the actual branch

```bash
git diff
```       
> show the changes between the current and last commit

```bash
git diff --staged
```       
> show the changes between the staging area and the last commit

<hr>

# History

```bash
git log 
```       
> shows history

```bash
git log --oneline
```       
> shows history line by line

<hr>

# Remote vs Local

```bash
git remote -v 
```       
> show configured remote repos

```bash
git remote add < name > < url_do_repo >
```       
> add new remote repo

```bash
git push < remote > < branch >
```       
> send changes to remote repo

```bash
git pull < remote > < branch >
```       
> pull all changes from repo

```bash
git diff HEAD~1
```       
> show all the differences made between last and second to last

```bash
git rm < file >
```       
> removes file from staging area and directory

```bash
git clean -n 
```       
> shows the files that are not staged and that will be removed

```bash
git clean -f   
```       
> removed the unstaged files