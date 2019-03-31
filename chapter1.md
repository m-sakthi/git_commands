### Introduction to common GIT terms
**GIT Repository**
- is not a server
- it is a container for snapshots and history

**Remote**
  - Connection to another repository
  - Like a URL
  - Can be used for a central server
  - Can also ponint to another repository on same machine

**Commit**
  - is a snapshot
  - Unit of history of changes and metadata
  A Contains following details:
    - Author/time/data
    - Parent commit ref
    - Comment(s)
    - Tree

**Reference** is Pointer to a commit or branch and is easy to create, move, destroy

**Branch** is a type of reference

**HEAD** is special reference which points to the branch you are in i.e., current branch

**Working Directory** is just an another set of files (like copy of your original files). Git always keeps watch of the changes made in it.

**Index** is also called as the staging area. The changes are copied from here to the working directory.

**Merge** is a commit that combines two seperate lines of history.

### Creating a GIT Repository

```
git init <repo-name>
```

To initialize a git repository named 'myproject' : `git init myProject`

You can create a **bare** GIT repo using following command
```
git init --bare <repo-name>
```

To initialise a remote bare repository named 'mybarerepo' : `git init --bare mybarerepo`

## Cloning a Repository

```
git clone <repo-name> [<local-repo-name>]
```

To clone a remote repositiry in Github : `git clone https://github.com/msv300/git_commands.git`

To list the commit graph
```
git log --oneline --graph
```

## Check status

```
git status
```

**Four stages of files**
  - **untracked**: whicn can be a new file that git has no knowledge of
  - **unmodified**: existing file with no changes being made in the index
  - **modified**: something is edited and git has found it
  - **staged**: changes before commit.

**Summerized version of git status**
```
git status -sb
```

where s - summary, b - branch

**To set an alias command**
```
git config --global alias.st=status -sb
```