# git-cleanup
Bash script to clean up merged branches.  Install somewhere on `$PATH` and invoke with `git cleanup`.

## Usage

```
Usage: git-cleanup [<options>] [<BRANCH>]

  BRANCH      Base branch name.  Branches that have been merged into this branch will be deleted
              Defaults to current branch.
  -s          Simulate.  Prints commands it would run instead of actually running them
  -r          Delete branches from remote
  -f          Force. Does not prompt for confirmation
  -h          Print this help text
```

## Config

You can use the environment variable `$GIT_CLEANUP_BLACKLIST_BRANCHES` to stop branches from being cleaned up.  It is a space-separated list that defaults to `master`.
