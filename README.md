About
=====

git-lp is a tool that allows you to use git to work with Launchpad.net.

Tutorial
========

Create a new repository that for working with a single Launchpad.net project:

    $ git lp init checkbox && cd checkbox

Get the initial code from Launchpad.net. This can be accelerated if you have an
existing bzr branch somewhere (pass the --cache option)

    $ git lp fetch

You can start working on a feature/bug in a branch

    $ git lp branch feature-foo

While you want:
 - Hack on your code
 - Commit with git
 - Rebase, squash, etc

At any time you can push your branch to Launchpad for review
This will push the code to lp:~yourlaunchpadusername/project/feature-foo

    $ git lp push

You may need to pass --overwrite to push if you've been rewriting history

    $ git lp push --overwrite

Installation
============

1. Download https://raw.github.com/zyga/git-lp/master/bzr.patch 
2. Apply it to your system (reinstall bzr to revert)

    You may want to read the outcome of this merge request
    to know if this patch has been accepted or well reviewed
    by the Bazaar maintainers.

    https://code.launchpad.net/~zkrynicki/bzr/find_ancestors/+merge/127610

3. Put git-lp somewhere in your PATH
