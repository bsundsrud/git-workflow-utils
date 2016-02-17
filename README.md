# git-workflow-utils

## git cleanup
Bash script to clean up merged branches.  Install somewhere on `$PATH` and invoke with `git cleanup`.

### Usage

```
Usage: git-cleanup [<options>] [<BRANCH>]

  BRANCH      Base branch name.  Branches that have been merged into this branch will be deleted
              Defaults to current branch.
  -s          Simulate.  Prints commands it would run instead of actually running them
  -r          Delete branches from remote
  -f          Force. Does not prompt for confirmation
  -h          Print this help text
```


### Config

You can use the environment variable `$GIT_CLEANUP_BLACKLIST_BRANCHES` to stop branches from being cleaned up.  It is a space-separated list that defaults to `master`.

## git upstream
Bash script to fetch all remotes and merge a matching named branch from upstream into the current branch, and then pushes to your origin.  This is based on naming conventions only so if you're doing something fancy with your branch tracking then this is very dangerous.

Assumes that the upstream remote is named `upstream`.  Useful if you're using a forking workflow where you create an issue branch, push to your fork (`origin`), and open a PR to the main repository.  The standard dance is:

```
  # Assuming on branch 'master'
  git fetch upstream
  git merge upstream/master
  git push origin master
```

Which is basically all this script does anyway, with some checking that an upstream branch of the same name actually exists.
