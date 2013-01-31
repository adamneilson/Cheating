# Git Cheatsheet

For the sake of demonstration this repo (project) will be called *Acme-www*.

## Starting from scratch:

Crack open Terminal and start by changing directory to the place you keep all your projects. For example `cd ~/Projects/`

Start by making a local directory to house the project:

`mkdir Acme-www`

Then move into that directory:

`cd Acme-www`

If you haven't already (ie. you'll only have to do this global setting once only):

    git config --global user.name "Adam Neilson"
    git config --global user.email adam@acme.com

Then we need to initialise this directory as a git directory:

    git init
    
Next up we want to add a remote origin. This is the place that is the authoritative 'master' copy that everyone works on.

    git remote add origin git@github.com:Acme/Acme-www.git

Next pull all the files from the remote repository to your local machine:

    git pull origin master

This command broken down is saying git pull everything from the master branch on the project's storage origin.

**You now have a local copy of the repo which you can add, edit, delete files to and from.**

At any point you can check the status of the repo by running `git status` This will show everything you have edited and deleted and also untracked files that need to be added to the repo.

## After adding a file
If you added a file run this to add it to the source control:

    git add -A

## After editing a file


Having edited a file:

    git commit -a
    
The `-a` flag is ALL.

After you have committed and added changes, you can push those changes up to the central repo:

    git push origin master

When multiple people have been working on the same file you may find you have a conflict. In such cases git will normally manage to merge these changes automatically. To do so you need to pull the server's version down first before pushing your changes.

    git pull origin master

## Update to the latest and greatest
As above, pulling down new changes is as simple as running the following command:

    git pull origin master
    
## I screwed up

So you've made a bunch of local changes but broken something in the process. How do you reset your local version to the version on the server?

Like this:

    git checkout -f

If you want to rollback to a specific version on a specific file you can by using the hex code (like this for example: abc123) of that commit:

    git checkout abc123 file/to/restore


And to revert to last committed version, which is most frequently needed, you can use this simpler command.

    git checkout HEAD file/to/restore
