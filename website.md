# Secure Systems Lab website

This document describes how to make changes to the Secure Systems Lab website
and make them available at
[http://ssl.engineering.nyu.edu](http://ssl.engineering.nyu.edu).

## Modify the sources
The SSL website is generated using [`Ruby`](https://www.ruby-lang.org)'s static
site generator [`Jekyll`](https://jekyllrb.com/).

Making changes to the website is similar to contributing to any other of the
lab's *GitHub* projects and includes:

 1. *forking* the corresponding source code repository [secure-systems-lab/ssl-site](https://github.com/secure-systems-lab/ssl-site),
 1. creating a *branch*,
 1. *committing* and *pushing* changes, and
 1. submitting a *pull request*.

Please refer to the lab's [*development guide*](dev-workflow.md) for more
details about this workflow. Instructions on how to build the website locally can be found in the
[secure-systems-lab/ssl-site README.md](https://github.com/secure-systems-lab/ssl-site/blob/master/README.md).

## Push to production

 1. Make sure your changes have been merged into
    [secure-systems-lab/ssl-site](https://github.com/secure-systems-lab/ssl-site)'s
    `master` branch and your local `master` branch is up-to-date (see GitHub's
    [*Syncing a Fork*](https://help.github.com/articles/syncing-a-fork/)
    for more details).

 1. Make sure the deployment server is available as remote URL in your
    local repo *(you only have to add the URL once)*.
    ```shell
    git remote add deploy deployer@telesto.poly.edu:/var/www/ssl.engineering.nyu.edu.git
    ```

 1. Push your local `master` branch to the deployment server. This activates
    a server-side hook, which builds the static pages so that the web server can
    serve them.
    ```shell
    git push deploy master
    ```
    **Important Note:** Your ssh public key will need to be added to the .ssh/authorized_keys file on 
    deployer@telestro.poly.edu for you to have permission to push directly.
