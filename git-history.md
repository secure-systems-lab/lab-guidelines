# Git History Guidelines

All of our projects follow a *fork + feature branch workflow*. That is, every
project has a main *upstream* repository (e.g.
[in-toto/in-toto](https://github.com/in-toto/in-toto)), with a *main* branch,
called `master` or `develop` (e.g.
[in-toto/in-toto@develop](https://github.com/in-toto/in-toto/tree/develop)).
Contributors work on their own *fork* of the *upstream* repository (e.g.
[lukpueh/in-toto](https://github.com/lukpueh/in-toto)). For every feature or
fix they are working on, they create a *feature* branch, with a descriptive
name (e.g.
[lukpueh/in-toto@threshold-comment-fix](https://github.com/lukpueh/in-toto/tree/threshold-comment-fix)).
A *feature* branch of a *fork* is incorporated into the *main* branch of the
*upstream* repository by submitting a *pull request*.

The rest of this document presents some guidelines to keep our projects' git
histories clean.

__*TL;DR*__
Avoid merge commits in your *feature* branch. You can use `git rebase` to sync
your *feature* branch with the *main* branch in *upstream* and also to keep
your git history clean.


__Choose the right base for your *feature* branch__
In most cases you will base your *feature* branch on the *main* branch of your
*fork*. Make sure that the *main* branch of your fork is in sync with the
*main* branch of *upstream* so that you don't work on outdated code.
Updating the *main* branch of your fork should not require *merge* commits,
unless you have commited directly to your *main* branch, which you shouldn't!

__Keep the base of your *feature* branch in sync with *upstream*__
While you are working on your *feature* branch the *main* branch might move
forward, because some other work was merged into the *main* branch. Check
regularily, especially before you submit a *pull request*, if the
base of your *feature* branch has moved forward. If it has, use `git rebase`
to update the base and fix conflicts as they occur.

__Tricks to keep the history of your *feature* branch clean (bonus task)__
A clean history also means that you split your work into sensible chunks, i.e.
commits (see [our commit guidelines](commits.md) for more details). You don't
even need to worry about this while coding. You can use `git add` in
`interactive` or `patch` mode to create multiple logically separated
commits from a huge diff. Or use `git rebase` in `interactive` mode to rewrite
the history of your *feature* branch to your hearts content.

__Resolve conflicts in an open *pull request*__ Once you have submitted a *pull
request* and you are receiving reviews and comments, you should avoid rebasing,
as it makes it harder to follow your changes on GitHub. However, if GitHub
notifies you about conflicts, you should rebase and fix the conflicts. Ideally,
you would do that after you addressed all review comments.

#### Further reading
Consider reading the resources listed below, especially if some of above
is unclear, you can also always reach out to someone on the lab.

__Git branching and rebasing__
- [Branching basics](https://git-scm.com/book/en/v1/Git-Branching)
- [Rebasing basics](https://git-scm.com/book/en/v1/Git-Branching-Rebasing)
- [`git rebase`](https://git-scm.com/docs/git-rebase)

__Workflows__
- [Feature branch Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)
- [Forking Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow)
- [Syncing forks on GitHub](https://help.github.com/articles/syncing-a-fork/)

__Bonus material__
- [Interactive staging](https://git-scm.com/book/en/v1/Git-Tools-Interactive-Staging)
- [Rewriting history](https://git-scm.com/book/en/v1/Git-Tools-Rewriting-History)