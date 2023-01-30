# Update the forked repo's main branch

Do `git fetch upstream`, not `git pull`.

When working on an open source project, we need to make the main branch up-to-date. In this case, `git pull` doesn't work as we expect, since it pulls the main branch of our forked repository, not the original repo.

What we need to do is to set the original repository as the upstream, `git remote add upstream ORIGINAL_REPO_URL`, make sure it is added properly `git remote -v`. It'll show you the urls of origin and upstream.

Once it's done, FETCH the updates from the original repo, `git fetch upstream`. This is it!
