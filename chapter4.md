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