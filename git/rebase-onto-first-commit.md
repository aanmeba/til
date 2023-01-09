# How to rebase onto the first commit

I wanted to rebase my second commit onto the first commit and tried to use `git rebase -i HEAD~2` but in Vim, it showed only the current commit and said `error: cannot 'squash' without a previous commit` when tried to squash it.

The simple way is to use `git rebase -i --root`.
