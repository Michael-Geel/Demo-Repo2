# Demo 2

This is a new README for the new repository I'm creating for the git push portion of the video.

Will continue my push notes here.
If I want to turn a new file/folder into a repository, in the command line, I'll write: "git init"
This initializes the repository in github.
So we can add and commit the updates, but when we try to push, we get an error because this repository wasn't cloned from github, but created locally.
The error is git saying it does not know where to push the updates to.
The easiest solution to this is to create a new git repository in github manually, then get the link to the repository.
We then use "git remote", "remote" meaning somewhere else not on the local computer.
The full syntax being: "git remote add origin 'repo link'"
And this provides a link to push the updates to when we push to origin.
Once this is done, can use "git remote -v" to view all the remote repositories currently connected to.

Is a shortcut for origin master. But need set up what's called an "upstream" meaning that's where I want to push to by defualt.
To set up an upstream, use this syntax: "git push -u origin master"
This way, if we're pushing to that location, we can just say "git push" without having to specify where to push to every time.

Take note that in creating this repo, my commits and pushes reflect correctly on github, which implies there's something 
on the original Demo-Repo that interfered with my information reflecting correctly.

Will do a push and set up an upstream now.

## Git Branching

For future reference: # = Heading in README and ## = Subheading in README

So far in git, we've been on the master branch, in Git, master is a name convention for the main/default branch in a repository.
If you're just working in one branch, that's where everything will live, all code and commits.
Called branching as starts to look more like a tree when have multiple branches.

When you first create a new branch (feature branch) the code on the master and feature branch will be exactly the same.
But as you make updates to the feature branch, those updates will only be seen on the feature branch.
So when commit changes to a feature branch, if you then change back to the master branch, none of the updates made to the feature branch will reflect.
Each individual branch has no way of know or tracking what changes and commits are made on other branches, and only tracks the changes and commits made on its own branch.
In this way, if you were to update the master branch, those changes won't reflect on a feature branch at all.
This is useful because in time you'll be adding features that'll be either incomplete or break your code, and you don't want to save those changes into the main master branch.
You want to work on them in a type of sandbox area so you can write all the code you need to and get it into a properly working condition before merging it back into the main master branch of the code base.
Very helpful when have many people working on a single repository or many different branches going on at once.
A common finding is that you'll work on a feature branch for a week or more, then you'll find a major bug you have to fix real quick.
Then you'll make what's called a "hotfix branch" to address the bug you've found, where you fix the root cause of the bug, ensure it's working correctly, and then merge back into the master branch.
Typing in "git branch" will display all branches currently in the git repository.
In the branch list, you'll see a star next to one of the branches, and that * indicates which branch I'm currently on.
We use "git checkout" to switch between branches, but also to create new branches.
To create a new branch, we type: "git checkout -b 'branch name'".
-Note that when working on a real application with people, you'd make the name as descriptive as possible.
--Can use dashes to lengthen the name of the branch.

Will save these notes and then move into the new branch.