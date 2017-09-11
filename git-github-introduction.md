# GitHub and Git
The majority of projects in our lab are hosted on [github.com](https://github.com/).
GitHub is a web application that can be used for collaboration, code review, and code management.
It is popularly used in open source projects and by distributed developers.  Contributions to
our projects are expected to be made using [pull requests](https://help.github.com/articles/using-pull-requests)
to repositories of their GitHub organization.  For example, the Seattle repositories
are hosted on the [SeattleTestbed](https://github.com/SeattleTestbed) organization.

Git is a free and open source distributed [VCS](https://en.wikipedia.org/wiki/Version_control_system)
(Version Control System).  A VCS helps manage changes made to files.  Users can run Git on their local
computers and upload changes to remote repositories and files hosted on GitHub.  Contributors can edit files
locally, upload their changes to GitHub, and then initiate a pull request. The following document
covers the basics of using Git and submitting a pull request to one of our project's GitHub repository.





## Git Installation
[git-scm.com](https://git-scm.com/) provides platform-specific installers for
[Mac](https://git-scm.com/download/mac),
[Linux](https://git-scm.com/download/linux), and
[Windows](https://git-scm.com/download/win) users.

## Configure Git Identity

After installing Git, the next step is for the user to configure his/her
identity (username and email address) so that Git can fully log the author of a
commit.  All Git commits include the user's username and email address.

To configure your Git identity, open the Terminal and type `git config
--global user.name "user's name"`, which will allow you to configure Git on
your local machine.  The user.name is arbitrary, but it is customary to use
your full name.

Each repository you create will use the same user (author)
configuration if you use the global flag (as in the provided example).

```
$ git config --global user.name "John Smith"

$ git config --global user.email "john.smith@example.com"
```

You can check your user information by typing the following command:

```
$ git config --list
```

## Configure Git to sign commits

If [GPG](https://gnupg.org/) is installed on your system, you can configure Git
to sign your commits.

```
$ git config --global user.signingkey <your GPG key ID>
```

GitHub provides more thorough [instructions on how to tell Git about your GPG
key](https://help.github.com/articles/telling-git-about-your-gpg-key/).

There is also a convenient Git command to automatically sign all of of your
commits:
```
$ git config commit.gpgsign true
```

Note: The command above requires Git version >= 2.0.0.



## GitHub User Account
Before a pull request can be submitted to a
[Secure Systems Lab](https://github.com/secure-systems-lab) repository, a user account
(free) must be created on GitHub.  This user account is also needed to create
new repositories and fork ones that already exist on GitHub.

A GitHub user account can be created at https://github.com/join

Once users create their accounts, user-specific home pages are created. For
example: `https://github.com/<username>`.  A user-specific home page can contain
repositories that the user has created or forked, contribution activity, and
organizations he/she has joined.

## Fork a Repository

Forking refers to making a copy of a GitHub repository and saving it to your
GitHub user homepage. GitHub provides general instructions on [creating and
managing forks](https://help.github.com/articles/fork-a-repo) and [pull
requests](https://help.github.com/articles/about-pull-requests/).

Forking a repository, [SeattleTestbed](https://github.com/SeattleTestbed) in
this example, requires clicking the `fork` button on the selected
repository's GitHub page, which creates a copy of the repository and saves it
to a repository directly controlled by the user (on the user's GitHub home
page).  The URL of the forked repository can then be used with Git to create
and save a local copy.

Navigate to the [repy_v2](https://github.com/SeattleTestbed/repy_v2) repository
and click on the `fork` button in the upper right-hand corner of the page.

![GitHub Fork](/images/fork_sm.png)

## Clone a Git Repository

The `git clone` command creates a local copy of a remotely hosted GitHub
repository.  So far, the `repy_v2` repository has only been copied and saved
to the user's GitHub home page.  In the following example, the `repy_v2`
`SeattleTestbed` repository is cloned to create a local Git repository.

```
$ git clone https://github.com/<username>/repy_v2
Cloning into 'repy_v2'...
remote: Counting objects: 1547, done.
remote: Total 1547 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (1547/1547), 1.06 MiB | 0 bytes/s, done.
Resolving deltas: 100% (778/778), done.
Checking connectivity... done.
```

A `repy_v2` folder is created in the local, current working directory.
Before issuing Git commands pertaining to this repository, you need to
change directories to either the cloned repository's directory, or to one
of its sub-directories. For example:

```
$ cd repy_v2/
```

### Keep your Fork in Sync with the original Repository
Setting an alias for a repository can help developers better manage repository
changes and keep local and remote repositories in sync.  The alias is a string
that refers to the repository by name instead of the repository's full URL.  In
the example below, the original
[repy_v2](https://github.com/SeattleTestbed/repy_v2) repository is given the
`upstream` alias:

```
$ git remote add upstream https://github.com/SeattleTestbed/repy_v2.git
```

Fetching and merging the latest changes of `upstream` (remembering that the
`upstream` alias points to the original repository) can be done with Git's
`pull` command.  The `pull` command fetches changes made to the remote
repository and merges them into your local repository.  Branches are multiple
working versions of a master project (or document). The main branch is the
master repository and multiple, local branches of this master may be created by
users so that they can work on the project before committing their work to the
master document.  The pull command expects to see a (by default, the master)
branch name, which the user will find on the project's [main
repository](https://github.com/SeattleTestbed/repy_v2).  Information on
creating a new branch is in the next section, `Add a New Branch Locally`.

![GitHub Branches](/images/branches_sm.png)

Additional information on [syncing a
fork](https://help.github.com/articles/syncing-a-fork/) is recommended.

```
$ git pull upstream master
From https://github.com/SeattleTestbed/repy_v2
 * branch            master     -> FETCH_HEAD
  * [new branch]      master     -> upstream/master
  Already up-to-date.
```

### Add a New Branch Locally

First, list all known local branches of the repository, by typing the following:

```
$ git branch
* master
```

Next, to add a new branch, which is the preferred method for working on and
adding new features, type `git branch new_branch`, where `new_branch`
is the name of the new branch:

```

$ git branch new_branch
```
The next step is to switch to the newly created branch:

```
$ git checkout new_branch
Switched to branch 'new_branch'
```
Note: ```git checkout -b [branchname]``` is a shortcut to create and checkout a
new branch.

### Commit a New File to the Branch

Create a `LICENSE` file and save it to the local machine. You do this by
opening a new document in a text editor and saving as `LICENSE` in the current
directory. In the `LICENSE` file you can include an open-source license for the
project.  The [MIT license](https://choosealicense.com/licenses/mit/)
is typically used for most of our lab's projects.

The next step is to ask Git if it can find the `LICENSE` file, by asking it to
identify all untracked files (on the local repository):

```
$ git status
On branch new_branch
Untracked files:
  (use "git add <file>..." to include in what will be committed)

  LICENSE

    nothing added to commit but untracked files present (use "git add" to track)
```

Git indicates that the `LICENSE` file is untracked, so the first command (git
add) will add it. The second command (git status) will tell us whether the file
has been added successfully.

```
$ git add LICENSE

$ git status
On branch new_feature
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   LICENSE
```

After adding the file it must be committed. By committing a file, Git creates a
message about the file that will be transmitted once the file is ready to be
pushed to the master branch.  A Git message should be descriptive and mention
the reason for the change, or changes, to be committed.  In the following
example, the `-m` flag (for message) is used and a commit message is appended
in quotes.

```
$ git commit -m "Add a LICENSE file to the project"
[new_branch 7660f34] Add a LICENSE file to the project
 1 file changed, 1 insertion(+)
  create mode 100644 LICENSE
```

If you want to check to see that all files have been added and committed, type
`git status` again. The status should show that the directory is clean, as in
the example below:

```
$ git status
On branch new_branch
nothing to commit, working directory clean
```

To get a list of commit messages made thus far, type `git log`.  This will show
the user's information and the commit message (in this case `Add a LICENSE to
the project`):

```
$ git log
commit 3c9b1d0068075fdac6ed928f8e5a27ac3253ca5e
Author: <username>  <username@example.com>
Date:   Tue Sep 2 14:46:36 2014 -0400

    Add a LICENSE to the project.
```


### Push the Commit to the Remote (Forked) Repository

This step will push the branch to the remote repository controlled by the user
(the forked version that you created earlier). The changes committed in the
"Commit a New File to the Branch" so far exist on the local repository.  The
earlier commit message, along with the file, are pushed to the user's remote
repository.

```
$ git push origin new_branch

Username for 'https://github.com': <username>
Password for 'https://<username>@github.com':
Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 308 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To https://github.com/<username>/repy_v2
 * [new branch]      new_branch -> new_branch
```


### Pull Request

After the files are pushed, you (the user) can initiate a pull request
to suggest your changes for inclusion in the original upstream repository.

Continuing with the example of `SeattleTestbed/repy_v2`,
visit the forked `repy_v2` repository and click on the "New pull request" button next to
the drop-down list of branches.  The next page is where you will preview the
commits and write/post a summary or comments about the changes you made. The
image below shows where to locate the pull request button.

![GitHub Pull Request](/images/pull-request_sm.png)

A page (containing the user's Pull Request) is generated by GitHub and viewable
by both the user and developers of the `repy_v2` repository.  A
[repy_v2](https://github.com/SeattleTestbed/repy_v2) developer can review the
user's changes and either accept, decline, or ask that the user addresses
issues with the pull request.    The pull request's page provides a section to
enter comments and allow the user and
[repy_v2](https://github.com/SeattleTestbed/repy_v2) developers to collaborate.
The user can make additional changes to the pull request (for example, to
address an issue raised) by pushing commits to the user's forked repository.
In the following example, the user edits the `LICENSE` file and saves the
changes before issuing `git add LICENSE`:

```
$ git add LICENSE

$ git commit -m "Add missing section to LICENSE noticed by reviewer"

$ git push origin master
```

### Resolve a Merge Conflict

Merge conflicts might occur with Git's push or pull actions if multiple
contributors attempt to modify the same section of a file, and merge their
conflicting modifications to the server’s “master" branch. For example, suppose
one contributor wants "foo" to appear in the first three characters of a file,
while another contributor desires "bar". When a merge conflict occurs, the
affected contributors must mutually resolve the conflicting section. That is,
the file in the previous example must be edited to produce one unique version
of the file; either "foo" appears in the first three characters, or "bar" does.

If Git detects a merge conflict after a pull or merge action, it inserts
special markers in the conflicting section(s) of the file to indicate what
needs to be resolved:

```
    <<<<<< HEAD
    foo
    ======
    bar
    >>>>>>
```

The text between `<<<<<< HEAD` and `=====` is what is currently on the server’s
“master” branch.  The text between `=====` and `>>>>>>` is what is being merged and
causing the conflict.  To resolve the merge conflict, a contributor must open
the file in a text editor and manually remove the merge conflict markers and
either keep what is currently on the “master” branch or what is being merged.
In the merge conflict example above, a contributor would keep either the text
“foo” or “bar”, and remove the rest of the markers inserted by Git.  To
finalize the merge conflict, the contributor must commit the resolved changes.

**Steps to resolve the merge conflict:**

Edit the file containing the merge conflict in a text editor.
To discard what is currently on the server and replace it with “bar”, delete “foo” and the three inserted markers.

1. Save the file.

2. ```$ git add```

3. ```$ git commit```

4. ```$ git push```

The following page provides a comprehensive guide on resolving merge conflicts:
https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line/

## Miscellaneous Git commands

Typing `git help -a` on the command-line outputs the full list of commands
supported by Git.  Consult Git's help pages for more information about each
command.  [Zackperdue.com](http://zackperdue.com/tutorials/super-useful-need-to-know-git-commands)
is another resource that covers useful Git commands.

The section below lists some useful, common Git commands.

To show changes/differences in the `LICENSE` that have not been committed:

```
$ git diff LICENSE
diff --git a/LICENSE b/LICENSE
index 70a3d0f..93bce69 100644
--- a/LICENSE
+++ b/LICENSE
@@ -1 +1,2 @@
 LICENSE file.
 +new line added here.
```


To mark `LICENSE` as removed and stage it for removal:

```
$ git rm LICENSE
```

To unstage the modified `LICENSE` file and reset its contents to the current
version on the repository:

```
$ git reset HEAD LICENSE
```

To rename a file or to move it to a new location and let Git know of the change:

```
$ git mv source_file destination_file
```


To temporarily store modified files in order to change branches:

```
$ git add temporarily_modified_files
$ git stash save "Temporary commit message for modified files"
```

To display stashed contents and apply them on the current branch:

```
$ git stash list
$ git stash pop
```
