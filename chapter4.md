## Sharing and Updating
### Fetching
To download refs from remote repository
```
git fetch [<options>] [<repository> <ref(s)>]
```
ex: `git fetch origin feature/users`
The above command will download `feature/users` branch i.e., a remote ref to your local repository.
**Note**: The `fetch` commmand will only download the refs and will not checkout the index and working directory. You should explicitly checkout to the fetched ref or branch to see the changes.

Fetch will update the local branch only if the local branch is the descendent of the remote branch. You can override this behaviour by using `-f` option.

You could also use `--multiple` option to fetch multiple refs from the remote repository.

To fetch all the refs from remote repository
```
git fetch --all
```

Options:
`-f` or `--force` will update the local branch even if it is not the decendent of the remote branch.
`-p` or `--prune` will remove any remote-tracking references that no longer exist on the remote
`-t` or `--tags` to fetch all the tags from the remote
`-n` or `--no-tags` to fetch ref objects other than tags.

### Pulling changes from remote repository
To fetch from and integrate with another repository or a local branch use
```
git pull origin [option] [<refs> | <path>]
```

ex: `git pull origin master` will pull all the changes from remote repository to our local machine.

It is actually a shorthand for `git fetch` and `git merge FETCH_HEAD`.

Commonly used option is
```
git pull --rebase origin <branch-name>
```
`--rebase` is used to place all the commits from the remote branch below the current HEAD commit.

### Push changes to remote
Update remote refs along with associated objects
```
git push [options] [<remote-name>] <ref>
```
ex: `git push origin master`

But if the `<remote-name>` is not specified git checks the `branch.*.remote` config and decides to which repo to push. If the configuration is missing it defaults to `origin`.

If the command line is specifying what to push then by default the current branch is pushed but as a security check git verifies whether the current branch's and upstream branch name are same.

Options:
**--all**: Pushes all the branch.
**--tags**: to Push all the tags.
**-f** or **--force** : To force push a ref.

### Managing Repositories
To manage a set of remote repositories.

List the repositories
```
git remote -v
```
To add remote repository
```
git remote add <name> <url>
```
To rename a added remote
```
git remote rename <old> <new>
```