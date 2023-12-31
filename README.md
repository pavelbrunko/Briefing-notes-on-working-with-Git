This is a breafing notes about main Git and GitHub commands. You can use it when you forget some of them.
Let's start from some basic bash commands, which can help you to work with your machine throught the terminal.
- Check where are you now on your machine:
```bash
$ pwd
```
- Change the directory:
```bash
$ cd 'new_path'
```
- Make a folder:
```bash
$ mkdir <folder_name>
```
- Make a .txt file:
```bash
$ touch <file_name.txt>
```
- Remove file:
```bash
$ rm <file_name>
```
- Remove folder:
```bash
$ rm -rf <folder_name>
```
---
Now we are ready to do some Git things
## Making new repository
- Initialize repository:
```bash
$ git init 'project_name'
```
- Download repository:
```bash
$ git clone 'url_of_the_project'
```
---
## State of your repository:
- List of uncommited files:
```bash
$ git status
```
- List of uncommited files + igrored files:
```bash
$ git status --ignored
```
- Changes, which still don't added to file's index:
```bash
$ git diff
```
- Changed in already added files:
```bash
$ git diff --cached
```
- All changes:
```bash
$ git diff HEAD
```
- Changes between two commits:
```bash
$ git diff hash1 hash2 
```
- Receive the dates of the changes and their authers:
```bash
$ git blame <file_name>
```
- Receive a list of changes in file in certain commit:
```bash
$ git show hash:file 
```  
- List of commits:
```bash
$ git log
```
- Show the story of changes, including diffs:
```bash
$ git log -p <file_or_folder_name>
```
- Call an abbreviated log:
```bash
$ git log --oneline
```
---
## Connect remote and local repository
- Bind a remote repository to a local one:
``` bash
$ git remote add origin 'github_ssh_key'
```
- Check if the repositories are connected:
``` bash
$ git remote -v
```
---
## Work with branches
- A list of local branches:
```bash
$ git branch
```
- A list of all branches:
```bash
$ git branch -av
```
- Switch to the branch mybranch:
```bash
$ git checkout mybranch
```
- Craeate branch mybranch and switch to it:
```bash
$ git checkout -b mybranch 
```
- Delete branch mybranch:
```bash
$ git branch -d mybranch
```
- Merge branches a and b:
```bash
$ git chechout b && git merge a
```
- Create a tag for current commit:
```bash
$ git tag 'tag_name'
```
- Merge branches:
```bash
$ git merge mybranch
```
- Delete branch after merging:
```bash
$ git branch -D mybranch
```
---
## Save changes
- Add file to an index:
```bash
$ git add <file>
```
- Add all files in the folder:
```bash
$ git add .
```
- Commit added files to an index with message:
```bash
$ git commit -m 'your_message'
```
- Commit all files with the message:
```bash
$ git commit -am 'your_message'
```
- Edit the last commit:
```bash
$ git commit --amend --no-edit
```
- Change the message in the last commit:
```bash
$ git commit --amend -m 'new_message'
```
- Perform unstage of changes (delete the file):
```bash
$ git restore --staged <file_name>
```
- Delete changes in file:
```bash
$ git restore <file_name>
```
- Delete changed file from the index, leaving changes in it:
```bash
$ git reset <file_name>
```
- Cancel all changes in the folder and return to the last commit:
```bash
$ git reset --hard <commit hash>
```
---
## Update
- Download changes from the remote repository:
```bash
$ git fetch
```
- Download changes from the remote repository and merge them:
```bash
$ git pull
``` 
- Download changes from the remote repository and overlay not running commits on top of downloaded ones:
```bash
$ git pull --rebase
```
- Send local commits to remote repository:
```bash
$ git push
```
- Forced pushing:
```bash
$ git push --force
```
---
## And the main ones!
- Don't forget to use help
```bash
$ git 'commands_name' --help
```
___
## Life-cycle of the files in project on GitHub
```mermaid
graph LR;
Untracted -- "git add" --> Staged+Tracked
Staged+Tracked -- "git commit" --> Tracked
Tracked -- "changes" --> Modified
Modified -- "git add" --> Staged+Tracked
```
___
## Feature branch workflow

The most popular approach to working with Git in a team is feature branch workflow. It creates a branch for each task (for example, for new functionality or bug fixes), and when everything is ready, they pour a new branch into main.

The important stages of this process are the pool request and the review of changes. The request pool is an interface where you can discuss changes. A review is a review of changes by other participants and one of the ways to check the quality of such changes.

If you are already a member of the project (or a collaborator in GitHub terms), you can clone the repository directly. And if not, you need to make a "fork" beforehand. The Merge button is also available for participants after the review, but not for non—participants.