# SSL Style Guide for Creating Scholarly Documents

The Secure System Lab prides itself on documenting all of its research in
conference papers or journal articles that are well-written, and
well-organized. This attention to detail begins with creating a
writing/editing structure for the paper that facilitates successful
collaboration with other authors in and out of the lab.

Note, there is a [useful collection](paper_template/) of files available 
for students to start with.

Here are a few guidelines for preparing an SSL document:

**1. All SSL projects are composed in LaTex and hosted on GitHub:** Avoid
writing/editing your papers on other collaborative writing sites (i.e.
Overleaf, MS-Word). GitHub is used by all lab personnel and so provides a
common interface for writing projects.  

**2. Set up a private Github repo file for your project, and give it a
sensible name:** It’s important to establish the repo early on so you and
your collaborators have a platform on which to work. Try to avoid the
impulse to be “cute” in your naming conventions. A good rule of thumb to
follow for repo names is as follows: your name, plus the name of the part
of the project you are publishing, separated by underscores.  So,
delong_lind_popular_paths or torres_in-toto_overall_framework would serve
well as repo names.  Avoid including a conference or a date in the name,
since the paper may be submitted multiple times.

**3. The sensible name rule applies to files as well:** File names within
the repo should be utilitarian, and should describe their purpose (i.e.
Makefile, abstract.tex, etc.). 

**4. Divide your publications/projects into logical chunks and make each a
separate file:** If you are writing a paper, each section should be a
separate file. The file name should be a lowercase name that would be easy
to guess from the section title.  So, abstract.tex, introduction.tex,
design.tex, etc. are good names.  Similarly, if you are creating a web
site, each page should be a separate file. This practice insures fewer
conflicts when multiple authors may be working at the same time. As already
mentioned above, make sure the titles of your sections describe what they
actually contain. Make everything as clear to your collaborators as
possible.

**5. Pay special attention to your bibliography/reference files:**
Reference lists should be put together using
[Bibtex](http://www.bibtex.org/). Described as both “a tool and a file
format,” Bibtex “describes and processes lists of references, mostly in
conjunction with LaTeX documents.”

**6. Make sure your repo contains the following files:** a [gitignores
file](https://git-scm.com/docs/gitignore), which specifies files that Git
should ignore, such as paper.pdf or paper.tex, and  a functioning
[Makefile](https://gist.github.com/isaacs/62a2d1825d04437c6f08) that will
build the paper, putting all files in the correct order and formatting it
according to publication/conference specifications.

**7. Set up macro files to make in line commenting easier:**  The macros
assign colors to each individual working on the paper. Any comments made
using these macros will then appear in the PDF, making it easy to determine
their source.

**8. Place line breaks for text at about 75 chars.** If lines run too long,
it affects the quality of editing in many editors, such as VIM.  You are
likely to end up with large, unrelated diffs as other authors try to move
your content to a format they can easily edit.

**9. Commit names and/or comments should highlight changes made.** Alert
the others working on your project as to what you have changed within the
document, particularly if you made changes in more than one section.

**10. Commit sooner rather than later:** It is not a good idea to keep
commits open for too long. Once you have completed work in a section,
commit and push.

**11. Notify collaborators when you need to “lock” a section:**
Particularly as a deadline looms, you may need to “lock” a given section so
copy can be finalized without creating conflicts. A quick email to
collaborators, warning them to stay away from that section for a given
period of time, will insure that crucial changes are not undone. In
general, it is a good practice to keep your collaborators posted when you
are working on the document in git. Depending on the number of
contributors, you may want to establish a schedule or order for
writing/editing to the file.

**12. Be sure to post a .pdf of the final version** of the paper submitted
to the conference or journal on the repo as SUBMITTED.pdf
