# learn-rebase
If you would like to add an exercise, see [CONTRIBUTING.md](CONTRIBUTING.md)

## Objective
Learn how to use features of the `git rebase` command.  The features are organized into exercises so you can pick which you'd like to learn.

## Key Takeaways about rebase
- It is not the same as `git merge`, and it does not replace it
- You end up `rewriting history` when using rebase
    - Be deliberate and careful when rebasing work that has already been pushed to a remote repository.  If others are working in the same branch your work can become diverged and difficult to handle if not done correctly.
- Don't avoid using `rebase` because of the pitfalls, gain an understanding instead to know when and when not to use it.
## How To Use This Repository
In any git repository, just follow the exercises you wish to gain experience with.

## Exercises
* [Basic Rebase - Moving your branch's base to another branch's tip](exercises/basic.md)
* [Interactive Rebase - Squashing Commits on your current branch](exercises/interactive.md)
