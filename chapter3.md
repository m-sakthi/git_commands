### Branching
**List branches**

To list local branches
```
git branch
```

To list all branches i.e., local and remote
```
git branch -a
```
or 
```
git branch --list
```
**--merged** will list all merged branches
**--unmerged** will list all unmerged branches

**Create branch**
The folowing command will create a git branch
```
git branch <branch-name>
```
ex: `git branch feature/users`

The above command will create a git branch and you'll have to manually swith to the created branch by using the `git checkout <branch-name>` command.

GIT also provides a shortcut to create a branch and switch to it by using 
```
git checkout -b <branch-name>
```
ex: `git checkout -b feature/users`

**Delete branch**

Deleting a branch means that you delete all the changes made in it.
```
git branch -d <branch-name>
```
ex: `git branch -d feature/users`
The above command checks whether the branch is fully merged in its upstream branch, or in HEAD if no upstream was set with `--track` or `--set-upstream-to`.

To force delete a branch
```
git branch --delete --force <branch-name>
```
GIT provides a shortcut as below to force delete a branch
```
git branch -D <branch-name>
```
ex: `git branch -D feature/users`

**Rename Branch**

To rename a the current branch you could use `-m` option
```
git branch -m <branch-name>
```
and to rename some other i.e., non HEAD branch
```
git branch -m <current-branch-name> <new-branch-name>
```

### Switch branches or restore working tree files

To switch between branches you could use
```
git checkout <branch-name>
```
ex: `git checkout feature/users`
To create and switch branch with in a same command:
```
git checkout -b <branch-name> 
```
ex: `git checkout -b feature/users`
To create a branch even it already exists and change its latest commit to HEAD you could use
```
git checkout -B <branch-name>
```

To switch a branch even if the index or the working directory differs from HEAD.
```
git checkout -f <branch-name> 
```
**Caution**: This will delete the changes made in the working directory.

Interactive switching mode
```
git checkout -p <branch-name>
```

Set up an **upstream tracking** with remote while creating a branch with `-b` option:
```
git checkout -b -t <branch-name>
```
or `--track` can alse be used.
To unset the remote upstream tracking use `--no-track`.


### Merge
To join two or more development histories or changes together

```
git merge <branch-name>
```
ex: `git merge feature/users` will merge `feature/users` branch to your current branch.

Option we could pass with merge :
`--commit` will add a commit after the merge is made
`--no-commit` will not add a commit while merging. This is by default.
`-m` can be used to set the commit message for the merge commit.

If there is a conflict while merging branch you could resolve the conflict and then add the changes using `git add <path>` go on with merging using using
```
git merge --continue
```
or you could cancel the merge with
```
git merge --abort
```

## Save uncommited changes
Git allows us to save uncommited changes or changes in a dirty working directory.

```
git stash
```
To list the stashed changes
```
git stash list
```
To view a particular stash changes
```
git stash show <stash-id>
```
To drop stash
```
git stash drop [<stash-id>]
```
If `<stash-id>` is not passed, it will drop the lastest stash by default.

To delete all the stashed changes
```
git stash clear
```
To save a stash with your own message
```
git stash save -p "<message>"
```

### Tags
To create, list, verify tag objects signed with GPG.

**Create** a tag with following command
```
git tag [-a | -s | -u <keyid>] [-f] [-m <msg> | -F <file>] [-e] <tagname> [<commit> | <object>]
```
Options: 
`-a` or `--annotate` : an unsigned, annotated tag object

`-s` or `--sign` : a GPG-signed tag, using the default e-mail address’s key.

`-u <keyid>` or `--local-user=<keyid>` : a GPG-signed tag, using the given key.

`-f` or `--force` : Replace an existing tag with the given name (instead of failing)

**List** tags
```
git tag --list
```
`v-*` option will list only the tags that match the pattern(s).

**Delete** a tag
```
git tag -d <tagname>
```
will delete an existing tag with given name.