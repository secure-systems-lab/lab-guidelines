Table of Contents:
1. [Commit Guidelines](#commit-guidelines)
2. [Pull Request Guidelines](#pull-request-guidelines)



# Commit Guidelines
## How to Commit
#### Separate by Concept
It should be possible when skimming the commit summaries (`git log --oneline`)
to have a good sense of what's being changed. For this reason and others
(cherry-picking, organization, etc.), this means that the substance
of each commit should be something you can summarize in a line. If you've made
changes to a module to provide support for some new file format, for example,
you should try to keep those changes in separate commits from completely
unrelated changes (for example, adding testing for an already-supported
file format). You may even want to keep changes that different on distinct
branches and make distinct pull requests for them.

#### Separate Moving and Modifying Files
If you are moving/renaming a file, never make changes to that file in the same
commit. If a file is moved with no changes, it shows up as such in *GitHub*,
and reviewing the move is very easy. If even one minor change is made to the
moved file, the diff in *GitHub* will instead show up as the deletion of all the
lines in the file at the old location and the addition of all the lines in the
file at the new location, which makes reviewing any modifications complicated.
Ideally, moving and modifying should even be in separate branches and pull
requests, to make those changes easy to review.

#### ... but don't spam
While there are some situations in which a commit with a single-character
change might make sense, try not to overdo it. If it becomes difficult to read
the commit history because conceptually simple changes come in too many parts,
or the summaries all look the same, that is counter-productive.


## How to Write Good Commit Messages
Good commit messages are an invaluable tool for understanding the history of a
repository and will also help your project look professional. Good messages
also allow others to taste the soup while it's cooking.

* Be specific:
  * someone with a bit of familiarity with your project should have a rough
  sense of what you're doing after skimming your message
  * someone looking through commit history for changes like yours should be
  able to pick yours out
* Do not exceed 72-80 characters per line. Aim for <=60 in the first line.
* Separate summary from details by using two newlines after the first line.
* Use the imperative (Do xyz), capitalized, and without terminal punctuation
in your first line. Everything before the double-linebreak is treated as the
summary, and the rest as the body/continuation. (There is no need to
duplicate content in summary and body.)

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



# Pull Request Guidelines

Pull requests should be readily reviewable. This means that they should be:
- [well described](#well-described-pull-requests)
- [focused](#focused-pull-requests)
- [self-contained](#self-contained-pull-requests)
- [brief](#brief-pull-requests)
- [frequent](#frequent-pull-requests)

## Pull Request Basics
Pull requests are a *GitHub* feature, not part of *git* itself. They are a way to
build discussion and review around merges, and to help people collaborating.

## Well-Described Pull Requests
#### Pull Request Titles
The title should make it easy to distinguish at a glance from any other pull
requests, and convey the essence of the changes.
[Consider the guidance in the commit message guidelines](#how-to-write-good-commit-messages).

#### Pull Request Descriptions
Provide a summary of the changes made, and the reasons why the changes are
helpful or important.

Repositories should follow this guide to
[create Pull Request templates](https://help.github.com/articles/creating-a-pull-request-template-for-your-repository/),
to aid
those submitting pull requests to provide the necessary information to a
reviewer.

## Focused Pull Requests

## Self-Contained Pull Requests

## Brief Pull Requests

## Frequent Pull Requests
If you spent thirty hours on a PR, it may be too big.

