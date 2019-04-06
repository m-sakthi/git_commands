## Inspection and Comparison

### Show Objects
Shows one or more blobs/trees/tags/commits.
```
git show [<options>] [<object>]
```
ex: `git show <commit-hash>` by default is shows the `HEAD` commit.

### List commits

To get the list of commits or simply called commit logs
```
git log [<options>] [<path> | <commit--revision>]
```
ex: git log --oneline

Options
- `-n` or `--max-count` : Limit number of commits.
- `--skip` to skip the number of commits to list
- `--since` or `--after` to show commits after the given date.
- `--until` or `--before` to list older commits than the given date.
- `--oneline` to list the commits and description in short. It is the short form of `--pretty=oneline --abbrev-commit`

### Show changes
To show changes between to working directory and index or tree, changes between two trees or commits, changes between files.
```
git diff [<options>] [<commit1> [<commit2>]] [--] [<path>]
```
ex: `git diff` to list the unstaged changes.
You could also do the following to apply the above command
```
git diff --cached
git diff HEAD
```
To check the staged changes you could use
```
git diff --staged
```