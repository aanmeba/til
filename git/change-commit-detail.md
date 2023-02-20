# How to change commit detail

```
git commit --amend
```

This command allows us to modify the most recent commit with additional flags, like `-m` for commit messages.

If you forgot to add one of the files so you just want to add the file without changing the commit message. Add `--no-edit` flag.

1. Edit hello.js & main.js files
2. `git add hello.js` and then `git commit`
3. Realise you forgot to add the changes from main.js
4. `git add main.js` and then `git commit --amend --no-edit`

If you needed to modify a specific commit, you can use this command line with `git rebase -i`.

1. `git log` to find the previous hash value that you want to amend.
2. `git rebase -i HASH_VALUE` and in the terminal, change `pick` to `edit` after pressing `i` in the keyboard which makes the insertion possible. And then `esc` and `:wq` to exit the vim.
3. `git commit --amend` with flages you want. For example, if you want to edit the date of the commit, add `--date=<date>`.
4. `git rebase --continue`
5. `git push -f origin main` to push the rebased commit.

Reference:

- https://git-scm.com/docs/git-commit
- https://www.atlassian.com/git/tutorials/rewriting-history
