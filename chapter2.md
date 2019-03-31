### Add changes to Staging

To add a single file or multiple files to staging area.
```
git add <file1> [<file2>]
```
To add all files
```
git add .
```
Advanced git add
```
git add -p .
```
This command will add changes to staging area in chunks. It will prompt to with several options like below
`Stage this hunk [y,n,q,a,d,e,?]?`
```
y - stage this hunk
n - do not stage this hunk
q - quit; do not stage this hunk or any of the remaining ones
a - stage this hunk and all later hunks in the file
d - do not stage this hunk or any of the later hunks in the file
g - select a hunk to go to
/ - search for a hunk matching the given regex
j - leave this hunk undecided, see next undecided hunk
J - leave this hunk undecided, see next hunk
k - leave this hunk undecided, see previous undecided hunk
K - leave this hunk undecided, see previous hunk
s - split the current hunk into smaller hunks
e - manually edit the current hunk
? - print help
```

### Save the changes to GIT
To record or save changes to the repository
```
git commit -m "commit description"
```
Stores the current contents of the index in a new commit along with a log message.
Make sure your log or commit message best describes the changes in the current index.

To replace the tip of the branch by creating new commit i.e., to add your changes to the current HEAD or commit.
```
git commit --amend
```
Here the message from the original commit will be used in the start and your can choose to edit or leave it.

To add all changes and commit in a single command
```
git commit -am "commit description"
```

### To reset changes

To unstage staged changes
```
git reset [<file> | <path> | <file1> <file2>]
```

**To reset your current HEAD or commit**
**--soft** will move your HEAD to the specified commit and does not touch the index file or working directory
```
git reset --soft <commit-hash>
```
**--hard** will reset your index and the working directory
```
git reset --hard <commit-hash>
```

### See difference between commits
To see the changes made in the current directory before adding it to the staging area i.e., the changes made after the last commit.
```
git diff
```
To see changes between two commits
```
git diff <commit1> <commit2>
```
Once the changes are added to the staging area using `git add` command your could use the `--staged` option like below
```
git diff --staged
```

### Remove files from working tree and index
Remove files from the index. 
```
git rm <file>
```
This will not remove the file from your file system but from the index. You could use your Operating system specific commands to remove it from the file system.

To remove folder
```
git rm -rf <folder>
```
where **-r** is recursive and **-f** is force.

### Move or rename file
To move or rename a file
```
git mv <source-file> <destination-file>
```
`git mv git_basics git_intro` will rename the file named `git_basics` to `git_intro`

You could move a file from a directory to another directory which has the same file name using the **-f** option.

To move or rename a directory
```
git mv <source-directory> <destination-directory>
```
