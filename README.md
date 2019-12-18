Useful scripts to extend git functionality.

## Installation

Copy the main scripts into a directory named in $PATH.

```
cp -av git-* ~/bin/
```

## Usage

1. `git-release`  # Like that from `git-extras` only more automatic
```
git release        # Creates a new semver release with an annotated tag
git release point  # Create a point release e.g. v0.1.0 -> v0.1.1
```

2. `git-changelog`

```
git changelog              # List commit messages since last "tag"
git changelog HEAD~4 HEAD  # List commit messages between two revisions
```

3. `git-bar`

```
source ~/bin/git-bar   # NOTE: This is not an executable script but a
                       # collection of bash aliases/functions.

gh          # list the help screen

```

### Committing

```
gd file     # git diff file - file is now "remembered"
ga          # git add file  - NOTE file is not specified as it was remembered
gca My elaborate commit message   # Commit. NOTE no quotes needed.

gd .        # git diff .
gca My other well-formed commit message

gdc         # git diff --cached
```

### Branches

```
gbr          # What branch am I on?
gb           # Use fzf to select branch
gco audit    # Checkout branch matching 'audit' anywhere in branch name
gco master   # Checkout master
gco          # Checkout last branch _a la_ cd

gba          # git branch --all --verbose
```

### Syncing

```
gp          # git pull
gP          # git push
gPA         # git push --all --tags  # Useful after a release
gsync       # git fetch --all && git pull .. useful before merge/rebase
            #                                from other branches
```

### Saving

```
gwip        # Create a WIP commit like a stash but pushable to remote
            # Useful before you go on vacation
gundo       # Undo the WIP commit (git reset --mixed HEAD~1)

gwipe       # Commit and then do a git reset --hard
            # Why? So you can always recover even this work via the reflog
```

... And many other goodies. Most commands support tab-completion too.

