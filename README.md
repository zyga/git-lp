About
=====

git-lp is a tool that allows you to use git to work with Launchpad.net.

Tutorial
========

Create a new repository for working with a single Launchpad.net project:

    $ git lp init checkbox && cd checkbox

Get the initial code from Launchpad.net. This can be accelerated if you have an
existing bzr branch somewhere (pass the --cache option)

    $ git lp fetch

Start working on a feature/bug in a dedicated branch:

    $ git lp branch feature-foo

While you want:
 - Hack on your code
 - Commit with git
 - Rebase, squash, etc

At any time you can push your branch to Launchpad.net for reviews. This will
push the code to lp:~yourlaunchpadusername/project/feature-foo.

    $ git lp push

You can easily react to review feedback: commit new patches, rework and amend
existing patches, anything that you want to. Once you are ready share your code
again just run push again. You may need to pass --overwrite to push if you've
been rewriting history though (but that is okay as you're working on a merge
request and it has not yet landed)

    $ git lp push --overwrite

Installation
============

This has been tested on Ubuntu 12.10 Quantal with bzr trunk but I believe it
should apply cleanly to packaged versions as well.

1. Download https://raw.github.com/zyga/git-lp/master/bzr.patch 
2. Apply it to your system (reinstall bzr to revert)

    You may want to read the outcome of this merge request to know if this
    patch has been accepted or well reviewed by the Bazaar maintainers. Once
    this is fixed then you won't have to patch your bzr anymore obviously.

    https://code.launchpad.net/~zkrynicki/bzr/find_ancestors/+merge/127610

3. Put git-lp (https://raw.github.com/zyga/git-lp/master/git-lp) somewhere in
   your PATH.
4. Install bzr-fastimport (sudo apt-get install bzr-fastimport)
