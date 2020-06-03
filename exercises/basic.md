# Basic Rebase - Moving your branch's base to another
## Visual Summary
Go from this
```
-(0)--(1)--(2) master
    \ 
    (R1)--(R2) rebase1
```
To This
```
You'll get something like this:
-(0)--(1)--(2) master
                \ 
                (R1)--(R2) rebase1
```
Bonus: after a clean rebase, you can merge `rebase1` to `master` cleanly
```
You'll get something like this:
-(0)--(1)--(2)--(R1)--(R2) master
```
## Summary
* Make a feature branch
* Make commits on feature branch
* Make commits on master
* Rebase feature branch (move the branch start to the tip of master)
* Move the feature branch into master (merge, with no extra commit)

# Exercise

## Make a feature branch
Create a new `rebase1` branch off of `master`

```
git checkout master
git branch rebase1
git checkout rebase1
```
## Make commits on feature branch
Make a few commits while on the `rebase1` branch.  For convenience, make commit messages something like the following so you can easily follow your own messages from each branch

```
rebase1 R1
rebase1 R2
etc...
```
## Make commits on master
Make a few commits on the `master` branch.  This will allow us to see how our history moves when we rebase.  Follow a similar commit message format
```
master 1
master 2
```
Stop and observe what your commits currently look like.  You can use `git log` while on each branch to see the recent commits.  I'm a very visual person so here's a diagram of what it should be
```
-(0)--(1)--(2) master
    \ 
    (R1)--(R2) rebase1
```
## Rebase feature branch (move rebase1's base to the tip of master)
Rebase `rebase1` to the `master` branch.  What you're really asking git to do is _"attempt to move the start of my branch to the current HEAD of master"_
```
git checkout rebase1
git rebase master

You'll get something like this:
-(0)--(1)--(2) master
                \ 
                (R1)--(R2) rebase1
```
- Using `git log` while on `rebase1` you'll see all 5 commits in that order
## Move the feature branch into master (merge, with no extra commit)
Once you've done a rebase successfully with no conflicts, you can now do a `merge` and it won't leave any extra commits in your history since no additional change was made
```
git checkout master
git merge rebase1

You'll get something like this:
-(0)--(1)--(2)--(R1)--(R2) master
```
- use `git log` to checkout your commit messages if you want to verify this really happened