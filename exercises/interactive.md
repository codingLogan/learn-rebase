# Interactive Rebase - Squashing Commits on your current branch
## Visual Summary
```
Go from this
(0)--(1)--(2)--(3)

To this
(0)--(123)
```

## Summary
* Make commits on current branch
* Run rebase command interactively
* Make edits during interactive session

# Exercise

## Make commits on the current branch
On your current branch make as many commits as you wish to combine

## Run rebase command interactively
Run the following command to interactively combine them into one commit.  This will open an editor 1 or more times depending on the options you choose

```
git rebase HEAD~[x number of commits you made] -i
```
## Make edits during interactive session
See the image below for what you will see in your editor or terminal
![Image of terminal](images/InteractiveRebase.PNG)

The options I chose above will do the following
1. `reword` - open a terminal to reword the commit message, then adds it to the `work in progress` rebase
1. `squash` - adds the commit and its message into the `work in progress` rebase
1. `fixup` - adds the commit to the `work in progress` rebase, and discards the commit message
1. Opens an editor to allow any final changes before commiting the rebase

Once you save and quit your commits involved will all be in the one as desired.  Use `git log` to check how it looks.
```
(0)--(123)
```