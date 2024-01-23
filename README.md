# git-tools

Contains git convenience scripts and hooks.

# Setup

clone the branch, preferably within a toplevel folder in your project called .mess, since that's how I use this.

Copy the contents of the hooks directory into your project hooks directory at .git/hooks and ensure they are executable.

If you are already using any of the same hooks, you should instead append the repository hooks (or whichever ones you want) to your existing hooks.

# stale-branches

Lists/deletes branches that haven't been locally checked out in a while.

Depends on the post-checkout hook.

The post-checkout hook logs the last time you checked out a branch. Make sure that is also executable (`chmod +x <git repo>/<wherever>/stale-branches`). I am pretty sure it can be placed anywhere in the git repo, I put it in the .mess directory which is conveniently already gitignored.

The meaning of "stale" can be adjusted to your taste by editing line ~3~ 4 of stale-branches.

### Usage

```
.mess/stale-branches [-l|--list] [-d|--delete [--force]]
```
Note: the --force parameter should be used with caution, as it will delete unmerged branches.

