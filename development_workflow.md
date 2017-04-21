# Lab Development / Contribution Guidelines

## Using git and GitHub
See the following guide (to be moved to this repository later):
[GitHub and Git](https://github.com/SeattleTestbed/docs/blob/master/Archive/Local/RepoAccess.md)


## General Development Workflow in the Lab
The lab's general workflow for contributing to a project involves:
- Forking the repository
- Creating a branch on your fork related to the particular feature you wish to add, with an expressive name (e.g. not "feature1", but instead "secure_client_using_xyzlib")
- Make commits to that branch in accord with the commit guidelines below.
- Make a pull request (PR) on GitHub to pull your branch on your fork into the main repository's main branch.
- Request review for that PR.




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

### PR Titles and Descriptions
* Summary
* Template
* Examples

Pull requests should be readily reviewable. This means they should be:
- focused
- brief and frequent
- descriptive



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

