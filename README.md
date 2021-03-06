# GitConfigs

_Prepared By: Danny Godbout_

_Date: January 2019_

A repository of useful Git commands.

--------------------------------------------------------------------------------

## Aliases

**graph**: List of commits:

```
git config --global alias.graph 'log --all --graph --oneline --branches'
```

**unstage**: The following alias can be used to unstage specific files:

```
git config --global alias.unstage 'reset --'
```

**newremotebranch**: Create a remote branch:

```
git config --global alias.createremotebranch 'push origin --'
```

**deleteremotebranch**: Delete a remote branch:

```
git config --global alias.deleteremotebranch 'push origin --delete --'
```

--------------------------------------------------------------------------------
## Clone

**single-branch**: Clone single/specific branch:

```
git clone --single-branch --branch <branchname> host:/dir.git
```
--------------------------------------------------------------------------------

## Workflow

### Status Check

To view the status of any file changes and staging, use:

```

git status
```

### Tagging

To add a tag at some point in your workflow, use:

```

git tag "Label"
```

With an annotation:

```

git tag -a "Label" -m "My message"
```

To push the tags to remote:

```

git push --tags
```

### Staging

To stage all files, use:

```

git add -A
```

With the unstage alias defined above, we can unstage specific files with:

```

git unstage example.txt
```

Or unstage all with:

```

git unstage .
```

### Commit

Store a commit with:

```

git commit -m "My commit message"
```

### Push

To push the commit(s) to remote:

```

git push
```

### Branching

To see which branch you're in:

```

git branch
```

To create a branch:

```

git branch new-branch-name
```

To move HEAD to the new branch:

```

git checkout new-branch-name
```

After making changes, merge them back into another branch (e.g. master):

```

git checkout master git merge new-branch-name -m "Merge message"
```

To delete a branch:

```

git branch -d new-branch-name
```

### Remote Branches

To create the remote branch, push to a new remote:

```

git push origin newbranch
```

To view the remotes:

```

git branch -r
```

To track a remote branch:

```

git checkout --track origin/newbranch
```

To delete a remote branch:

```

git push origin --delete newbranch
```

--------------------------------------------------------------------------------

## Merge Conflicts

When a merge conflict occurs, look at the output to determine which file(s) encountered a conflict:

```

git status
```

Make changes to the conflicted files manually, the use _git add_ to stage the resolution.

--------------------------------------------------------------------------------
