## Patching

### Apply existing changes
Apply changes introduced by an existing commit and we could use
```
git cherry-pick <commit-hash>
```
This requires your working directory to be clean.

There are chances that a conflict arises while cherry-pick-ing a branch. You could use one of below options
- `--continue` to continue applying the changes. Make sure you've already added the changes to staging area.
- `--quit` to clear the current operation progress.
- `--abort` cancel the operation.

### Revert
To undo existing or a given commit
```
git revert [<options>] <commit>
```
The above command will undo the changes made in the given commit and add a new commit to record them.

**Caution**: this will discard changes in your working directory.

if conflict arises you could use `--continue`, `--quit` or `--abort` to do the required.

### Reapply commits
To reapply commits on top of another base tip.
```
git rebase [-i] [<options>] [<branch> | <upstream-branch>]
```
will to an interactive rebase with the given branch i.e., it will apply the commits of the given branch below the current HEAD coommit.

This is exact same as the
```
git reset --hard <upstream>
```

Other useful options are
```
git rebase --continue | --skip | --abort | --quit
```