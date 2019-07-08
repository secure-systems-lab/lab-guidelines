# Code Review Guidelines

Code reviews are important, both to ensure code quality, and to learn from each
other. To get the most out of it, code authors should voice their expectations
of a review, and reviewers should state the performed actions and areas of
focus.

The necessary prerequisite for a *line-by-line* review is that code authors
make sure that the changes they propose actually make sense and work at a basic
level. *Corollary: It should never happen that neither the author nor the
reviewer actually tests the fix.* It is still okay to request feedback on work
in progress, but especially then it is important to be explicit about the depth
of the desired review.

__As code author (pre-review):__

1. Make sure your proposed change does what you think it should do. This also
   means that it conforms to the [code
   style](https://github.com/secure-systems-lab/code-style-guidelines) etc. *Do
   not waste the reviewer's time with things you can easily get right in the
   first place!*

1. Send a PR, that follows our [PR
   guideline](commits.md#pull-request-guidelines-wip), and describe what you
   think are the aspects that require the largest share of a reviewer's
   attention:
   > "Please do / look for / look at the following: ...."

1. Feel free to suggest the review to someone, e.g. by using [GitHub's *review
   request*](https://help.github.com/en/articles/requesting-a-pull-request-review)
   feature or by leaving a comment. Don't don't be afraid to remind them, if no
   one has been on it after a couple of days.


__As code reviewer:__

1. Inform the world about your review intent, e.g. by using [GitHub's
   *self-assign*](https://help.github.com/en/articles/assigning-issues-and-pull-requests-to-other-github-users)
   feature, or by leaving a comment.

1. [Perform the
   review](https://help.github.com/en/articles/reviewing-proposed-changes-in-a-pull-request).
   Be diligent, but also remember that the goal is not to demonstrate your
   review skills but to integrate the proposed bug fix or feature. And be
   respectful.

1. Mention the areas (topical, regional) you focused on. Feel free to mention
   areas you cannot review as well:
   > "Here's what I did to review your code: ...."


__As code author (post-review):__

1. Address **all (!)** review comments. *Do not waste the reviewer's time by
   having them leave the same comment twice!*

    - Reply to the comment, if it is unclear, or you think the reviewer got
      something wrong.

    - Push new commits that address the comment, otherwise. These commits
      follow the same [guidelines as regular commits](commits.md). Also see
      notes about [rebasing in an open *pull request*](git-history.md).

1. Start over with *"As code author (pre-review)"* above...
