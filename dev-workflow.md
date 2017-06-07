# Development Guidelines

The [Secure Systems Lab](https://ssl.engineering.nyu.edu) is a highly
collaborative and distributed workspace. To allow everyone to keep track
about  everyone else's work we use the version control system
[*git*](https://git-scm.com/) and publicly host our *repositories* on
[*GitHub*](https://github.com/).

Basic knowledge about *git* and *GitHub* is key for contributing not only
to our lab projects but also with many other open source projects. If you
prefer to contribute by other means [please let us
know](https://ssl.engineering.nyu.edu/collaborate).
In all other cases use our general development workflow below.

## General Workflow
1. **Fork the repository you want to contribute to** Our projects are
distributed over many *GitHub* organizations. You can find the relevant
links in the [projects section on our website
](https://ssl.engineering.nyu.edu/projects). Read more about
[forking on *GitHub* here](https://help.github.com/articles/fork-a-repo/).
1. **Create a branch** Whether fixing a bug or adding a new feature, in *git*
creating new branches is cheap and makes collaboration easy. Make sure to
chose an expressive branch name.
1. **Commit early, commit often** And don't forget to write descriptive
commit messages. This does not only help people who didn't write your code
to understand it at a glance, it also helps yourself when you revisit a
commit. A little bit like docstrings and comments. Apropos docstrings and
comments, be sure to follow our [code style guidelines
](https://github.com/secure-systems-lab/code-style-guidelines) when you write
code.
1. **Push early, push often** Don't be afraid to publish your
*chef-d'œuvre* even if it's work in progress (you can add something like
*``(WIP)''* in your commit message. Pushing on a regular basis ensures that
nothing gets lost and allows others to easily jump in and help you.
1. **Submit a pull request** If you want your contribution to be
integrated in one of our projects -- and that's what you are here for
-- you have to *request* that it gets *pulled* from your fork
into the base repo. Take a look at [Creating a pull request from a
fork](https://help.github.com/articles/creating-a-pull-request-from-a-fork/)
for further instructions. And beware of the following pitfalls:
    - Chose the right *base* branch and make sure that the PR contains all
    and only the intended commits.
    - Sort out conflicts if they appear. Which usually happens if the base
    repo moved forward while you were working in your fork. [Keeping your fork
    in sync](https://help.github.com/articles/syncing-a-fork/) with the base
    (or *upstream*, as it is often called) is a good way to avoid huge
    conflicts.
    - As with docstrings, comments, and commit messages, make
    sure your PR title is concise and the description is descriptive (oh
    really?!). This is really important for reviewers.

1. **Request a review** You can request reviews directly in *GitHub*. Also,
don't be afraid to re-ask if no one has been on it after a couple of days.




## Commits

### How to Split Up Commits

### Commit Messages
Good commit messages are an invaluable tool for understanding the history of a
repository and will also help your project look professional. Good messages
also allow others to taste the soup while it's cooking.

* Be specific:
  * someone with a bit of familiarity with your project should have a rough
  sense of what you're doing after skimming your message
  * someone looking through commit history for changes like yours should be
  able to pick yours out
* Do not exceed 80 characters per line. Aim for <=60 in the first line.
* Separate summary from details by using two newlines after the first line.
* Use the imperative (Do xyz), capitalized, and without terminal punctuation
in your first line.

More detailed guidelines and examples worth reading:
* [Quick and dirty guidelines from erlang's wiki](https://github.com/erlang/otp/wiki/Writing-good-commit-messages)
* [Detailed commit message guidelines from Chris Beams](https://chris.beams.io/posts/git-commit/)

Examples of good commit messages:

```
Correct typos in README.md
```

```
Redirect user to the requested page after login

https://trello.com/path/to/relevant/card

Users were being redirected to the home page after login, which is less
useful than redirecting to the page they had originally requested before
being redirected to the login form.

* Store requested path in a session variable
* Redirect to the stored location after successfully logging in the user
```

```
Order ECU Manifests deterministically in ASN.1 Vehicle Manifests

Conversion of a dictionary of lists of ECU Manifests into a list of
ECU Manifests allowed unpredictable ordering previously. Now, the
ECU Serials are sorted. As a result, the ASN.1 (and thus DER) generated
will not vary based on that order.
```



## Pull Requests

Pull requests should be readily reviewable. This means they should be:
- focused
- brief
- frequent
- descriptive

#### PR Titles

#### PR Descriptions

#### PR Templates
[This PR](https://github.com/uptane/uptane/pull/79) demonstrates how to add pull request
templates to your repository, so that when a user creates a pull request, it will be
populated with default values that encourage more descriptive PR text.


## Code Review
* How often to ask for code review
* Normal reviews cover the modified code and don't require total understanding of the project
* Design/structural reviews may require deeper understanding
* How to do a code review



## Issues
### When to create issues

### Issue Titles and Descriptions
* Template
* Examples



## Testing / tests
* When to write tests. TDD options
* Unit tests and Integration tests



## Continuous integration
* travis / coveralls





## Rarer topics
### Repositories, Dependencies, and Submodules
* When to split things into multiple repos
* Demo and normal/reference implementation splitting?

