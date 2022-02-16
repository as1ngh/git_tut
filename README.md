Git & GitHub Workshop
=====================

Welcome to the workshop. Feel free to use this guide as reference.

Setup User Configuration
------------------------

First thing to do is to setup your identity.

    $ git config --global user.name "Your Name"
    $ git config --global user.email your.email@example.com
    
Initialize your Repository!
--------------------------

Go to your project folder and initailize a git repo using init.

    $ git init

You can connect to your central Repo using git remote.

    $ git remote add origin "http_url_central_repo"

To list remote repos

    $ git remote -v
    
OR you insteal of all the above steps you can simply do

    $ git clone "http_url_central_repo"

Moving your changes to Staging Area
-----------------------------------

After you are done with your changes, you can add those changes to Staging Area.

    $ git add "filename"
    
For adding all the files in the current directory

    $ git add .
    
Committing
----------

You are now ready to commit. The `-m` flag allows you to enter a message
to go with the commit at the same time.

    $ git commit -m "I am adding two new files"
    
Log
---

We should now have a new commit. To see all the commits so far, use
`git log`

    $ git log
    
Branching
---------

The `git branch` command, when used by
itself, will list the branches you currently have

    $ git branch

The `*` should indicate the current branch you are on, which is
`master`.

If you wish to start another branch, use
`git checkout -b (new-branch-name)` :

    $ git checkout -b exp1
    
Comparing Branches
------------------

Lets say you want compare exp1 branch to master branch, use
`git checkout exp1` to switch to exp1 branch and use `git diff` to compare it to master.

    $ git diff master
    
Merging Branches
----------------

Eventually you will want to merge two branches
together after the conclusion of work.\
`git merge` allows you to do that.

We now want to merge our `exp1` branch into `master`. First, switch to
the `master` branch.

    git checkout master

Next, we merge the `exp1` branch into `master` :

    $ git merge exp1
    
Resolving Conflicts
-------------------

Conflicts are caused by merges which affect the same block of code.
The output will be something like:

    <<<<<<< HEAD
    hello
    =======
    test
    >>>>>>> practice
    
The top part of the block, which is everything between `<<<<<< HEAD` and `======` is
what was in your current branch. The bottom half is the version that is present from the `exp1` branch.
To resolve the conflict, you either choose one side or merge them as you see fit.
Once I have done that, I can then mark the conflict as fixed by using
`git add` and `git commit`.

    $ git add .
    $ git commit -m "Fixed conflict"

Syncing a Fork
--------------

    $ git remote add upstream "upstream_http_url"
    $ git fetch upstream
    $ git checkout master
    $ git merge upstream/master
    
Opening a PR
------------

Head on over to the repository on GitHub where your project lives. You'll see a banner indicating that your branch is few commits ahead of `"upstream_repo":master`. Click Contribute and then Open a pull request.

GitHub will bring you to a page that shows the differences between your fork and the upstream repository. Click Create pull request.