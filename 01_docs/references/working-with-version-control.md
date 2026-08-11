# Working with version control

## Clean new repo

To turn a downloaded GitHub template into a new repo, you usually make a fresh
Git repository from the template files, then connect it to a new GitHub repo.
The safest path depends on whether you want to keep the template’s Git history
or start clean. Common workflow

1. Copy or rename the downloaded template folder to your new project name.
2. Remove the existing Git metadata if you want a clean repo.
3. Initialize a new Git repo.
4. Commit the files.
5. Create a new empty repository on GitHub.
6. Add the GitHub remote and push. Clean new repo From inside the template
   folder:

```bash
rm -rf .git
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/your-username/new-repo.git
git push -u origin main
```

That makes the project a brand-new repository with no link to the original
template’s commit history.

### Keep history instead

If you want to preserve the template’s Git history, do not delete  .git .
Instead, change the remote to your new repo:

```bash

git remote set-url origin https://github.com/your-username/new-repo.git
git push -u origin main

```

## Remove a file that has been pushed

This removes it going forward; it still exists in earlier commits if anyone
checks history.

```zsh
git rm path/to/file
git commit -m "Remove path/to/file"
git push
```
