# Git LFS Auto-Unlock

This git hook script that will automatically unlock your locking files in a Git LFS repository when those changes are pushed or merged to a remote branch. 
This is useful when your team uses Git LFS file locking to prevent conflicts on binary files.

## Feature

Unlock changed files automatically in the following cases:
- Push your file changes to tracking remote branch
- Fetch tracking remote branch that contains your file change

## Installation

Run following command in your git working directory:

```bash
curl https://raw.githubusercontent.com/negokaz/git-lfs-auto-unlock/master/git-hooks/reference-transaction -o .git/hooks/reference-transaction && chmod +x .git/hooks/reference-transaction
```

## Customize

You can customize the remote ref (branch) to track by editing the `track_ref` variable in the hook script.
By default, it is set to `origin/main`.
You can change this to any other branch for your team workflow.

```bash
# .git/hooks/reference-transaction

# Remote ref to track
readonly track_ref='origin/develop'
```
