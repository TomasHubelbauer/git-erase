# Git Erase

Demonstrates erasing traces of files from Git history.
Based on https://stackoverflow.com/a/872700/2715716.

## The Setup

- Make a file/directory in its initial form
- Make changes to it and include changes to other files if you want to as well
- Run the command to erase the traces of the file/directory (replacing `$*_PATH`):

File: `git filter-branch --force --index-filter "git rm --cached --ignore-unmatch $FILE_PATH" --prune-empty --tag-name-filter cat -- --all`

Directory: `git filter-branch --force --index-filter "git rm --cached --ignore-unmatch -r $DIRECTORY_PATH" --prune-empty --tag-name-filter cat -- --all`

[See why `cat`](https://stackoverflow.com/a/21023615/2715716)

- Check the new history: `git push --force --verbose --dry-run`
- Rewrite the history on the remote: `git push --force`

## To-Do

### Fix the workflow not deleting the history
