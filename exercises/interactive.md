# Interactive Rebase - Squashing Commits on your current branch
## Visual Summary
```
Go from this git history, numbers representing unique commit hashes
(0)--(1)--(2)--(3)

To this
(0)--(4)
```
Notice, the hash of 4 is a brand new hash.  All the changes in the original 1, 2, and 3, are now in a new hash.

## Summary
Why would I want to squash my commits together?  This gives you an opportunity to clean up your commits and messages.  Say you made multiple commits, but one was just a typo fix in a commit.  You can now remove that useless commit by combining it with others.

* Make commits on current branch
* Run the rebase command
  * `git rebase HEAD~3 -i`
* Squash your commits together with Interactive Rebase

# Exercise

## Make commits on the current branch
On your current branch make as many commits as you wish to combine

## Run rebase command interactively
Run the following command to interactively combine them into one commit.  This will open an editor 1 or more times depending on the options you choose (see example of the possible options in image below)

```
git rebase HEAD~[x number of commits you made] -i
```
Example to combine your last 3 commits you would use:
```
git rebase HEAD~3 -i
```
## Squash your commits together with Interactive Rebase
See the image below for what you will see in your editor or terminal, in this step you have to edit the word/command to the left of each commit hash.  In this example we'll look at `reword`, `squash`, and `fixup`
![Image of terminal](/images/InteractiveRebase.PNG)

The options I chose above will do the following, (working top to bottom order)
1. `reword` - open a terminal to reword the commit message, then adds it to the `work in progress` rebase
1. `squash` - adds the commit and its message into the `work in progress` rebase
1. `fixup` - adds the commit to the `work in progress` rebase, and discards the commit message
1. Opens an editor to allow any final changes before commiting the rebase

So I'm essentially saying to rebase... "Use the first commit's code, but let me change the message.  Then merge 2nd commit's code changes and commit message to the first.  Then, for the 3rd commit, only merge the code changes and omit the message into the previous commit".

Once you follow the console prompts and finish your interactive rebase, your commits involved will all be in the one as desired.  Use `git log` to check how it looks.  Your commit message will also be merged together, based on your edits and selections.
```
(0)--(4)
```