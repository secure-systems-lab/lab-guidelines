# Development Guidelines

The [Secure Systems Lab](https://ssl.engineering.nyu.edu) is a highly
collaborative and distributed workspace. To allow everyone to keep track
of everyone else's work, we use the version control system
[*git*](https://git-scm.com/) and publicly host our *repositories* on
[*GitHub*](https://github.com/).

Basic knowledge about *git* and *GitHub* is key for contributing not only
to our lab projects but also with many other open source projects. If you
strongly prefer to contribute by other means than *git*/*GitHub* [please let us
know](https://ssl.engineering.nyu.edu/collaborate).
Otherwise, use our general development workflow below.

## General Workflow
1. **Fork the repository you want to contribute to**. Our projects are
distributed over many *GitHub* organizations. You can find the relevant
links in the
[projects section on our website](https://ssl.engineering.nyu.edu/projects).
Read more about
[forking on *GitHub* here](https://help.github.com/articles/fork-a-repo/).
1. **Create a branch**. Whether fixing a bug or adding a new feature, in *git*
creating new branches is cheap and makes collaboration easy. Make sure to
chose an expressive branch name, and try to make each branch self-contained.
1. **Follow our
[code style guidelines](https://github.com/secure-systems-lab/code-style-guidelines)**
when you write code, please.
1. **Commit early and often**. Make commits to your branches. Split commits
up so that different changes for different reasons are in different commits.
Write concise and descriptive commit messages. This helps you and others
understand the commit itself and commit history at a glance. See our
[guidelines for commits](commits.md).
1. **Push early and often**. Don't be afraid to publish your
*chef-d'œuvre* even if it's a work in progress. You can add something like
*`(WIP)`* in your commit message if functionality is incomplete. Pushing
on a regular basis ensures that nothing gets lost and allows others to
easily jump in and help you.
1. **Submit a pull request**. If you want your contribution to be
integrated in one of our projects, you have to *request* that it gets *pulled*
from your fork
into the base repo. Take a look at [Creating a pull request from a
fork](https://help.github.com/articles/creating-a-pull-request-from-a-fork/)
for further instructions. And beware of the following pitfalls:
    - Choose the correct *base* branch and make sure that the PR contains all
    and only the intended commits.
    - Sort out conflicts if they appear. This usually happens if the base
    repo moved forward while you were working in your fork. [Keeping your fork
    in sync](https://help.github.com/articles/syncing-a-fork/) with the base
    (or *upstream*, as it is often called) is a good way to avoid huge
    conflicts.
    - As with docstrings, comments, and commit messages, make
    sure your PR title is concise and the description tells the reader enough
    to really understand what the PR is about. This is really important for
    reviewers!
    - Read our [git history guidelines](git-history.md) for more details.

1. **Review tests**.  After submitting a pull request to most lab projects,
continuous integration (CI) should run automated test builds (commonly via
Travis-CI and AppVeyor) and report the results in the pull request page itself.
This helps identify possible problems in pull requests, or point to indicate
where test code needs to be modified due to the changes.  If builds fail for
your pull request, look through the output and see if you can fix the problems.
You can also run tests locally!  Check the `.travis.yml` or `appveyor.yml` files
to see what commands the build systems run.

1. **Request a review**. You can request reviews directly in *GitHub*. Also,
don't be afraid to re-ask if no one has been on it after a couple of days.
