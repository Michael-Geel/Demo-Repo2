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

Have now moved into the new branch names "feature-readme-instructions".
Terminal feeds back upon branch creation that have moved into the new branch.
Using git branch again shows that we're on the new branch named feature-readme-instructions.
If we wanted to switch back to the master branch, we'd say "git checkout master"
-The general syntax for branch switching is "git checkout 'branch name'"
You can use tab to autocomplete your commands when branch names are getting long to save time.

## New Branch Notes.

This line is just for proof of concept on updating the branch and pushing to git.
Checking it in git status.
-Shows modified as per usual.
So we'll now use git add to stage the changes.
Functions normally, will have to re-add to stage these notes.
Will then commit and push accordingly, will first make notes then run the code.
Looks like no push gets done so will do commit now.

Having done the commit, can observe that all the above notes made in this branch don't show up in the master branch.
If you do a git checkout to switch to the master branch, all the notes made in this branch disappear.
When switching back to the master branch, I can merge the 2 branches locally using the "git merge" command.
Before we do that though, we'll double check what we're merging in using the "git diff" command, referred to as diffing.
It compares 2 versions of the code and shows all of the lines that have been changed.
-Roughly shows this in GitHub with the red - lines showing what's been removed and the green + lines showing whats been added.
When using git diff, you use this syntax: "git diff 'branch name'".
-Here branch name is the name of the branch you're comparing to the branch you're currently in.
Will do a fresh commit now, then switch to master branch and run a diff.

Have checked the diff, so when running a diff, what is in the branch you're comparing to the one you're in that isn't in your current branch appears in red, what is in the branch you're in that isn't in the branch you're comparing to, is in green.
When done, it highlights (END) in white, all you do is press 'q' to exit and return to a new command line.

Could then merge after confirming the diff locally. But what's done more commonly seen pattern is pushing these changes on that branch up to GitHub, then making a PR (Pull Request).

If want to push to GitHub, will ask to tell it what branch to push to, it'll output that there's no upstream branch. By standard, you'll almost always name the branch of GitHub the same as on your local machine. You would then push the new branch and set a remote upstream branch using the following code: "git push --set-upstream origin 'branch name'".
But here the '--set-upstream' is the same as the '-u' we've previously used. -u is just the shorthand.

Will now commit and push to the new upstream branch.

So a Pull Request (or PR) is basically a request to have your code pulled into another branch.
In this instance, run a PR from the Feature Branch to the Master Branch (Ie pull from feature-readme-instructions to the master branch).
Once made a PR, anyone can review our code, comment on it, ask us to make changes or updates.
Note that after you make a PR, you can update the code jsut by making additional commits and pushing them to github as long as it's on the same branch that you're making the PR with.
Once the PR is merged, you'll generally delete your feature or source branch.
Then when you want to make additional changes to the master branch, you'll create a new branch and start the entire process over of making commits, pushing updates, make a PR from the new branch, merge again and then deleting it.

So now with a PR, we could use the URL supplied in terminal, but we'll first do it manually on github.
GitHub auto picks up on the new branch pushed though and gives you a button to compare the branches and create a pull request.
On the screen the button takes you to, base is the branch you'll pull changes into from the "compare" branch.
You then get a title and description fields for the pull request, where you can name the pull and give a detailed description outlining what changes you've made, why and how you made them.
After that you create the pull request, which takes you to an interface where you can see conversations regarding your pull and comments on it, and look through the commits you've made that you're trying to add to the master branch.
You can also get a preview of the files that've been changed along with what's been changed.
When reviewing your changes, you can hover over a particular change and will see a blue plus button to the left of the line where you can comment on a particular update.
If you're happy with everything in the pull you can go ahead and merge the PR, and if any comments have been added, you'd need to confirm resolution of the comments to confirm the merge. If you're the owner you don't have to and can merge without resolving conversations.
Once merged, you can go back to view the master branch and should see all the updates merged into the master branch.
Having done the changes in GitHub, when you switch to the master branch locally, they won't appear on your local machine yet.
Will need to pull them down to local environment, and will need to use a git pull: "git pull origin master" but if have upstream set, then can just do "git pull".
Then should see updates on local master branch.
At this point will still see the branch there, but by convention we don't re-use branches.
So we can go ahead and delete the branch: "git branch -d 'branch name'"

Have successfully merged and pulled the updates into the master branch, which I'm working on now again.
Will now delete the feature-readme-instructions branch.
feature-readme-instructions successfully deleted.

In real life, won't always have such an easy time merging.
Will come across merge conflicts in git.
This arises when multiple people are all working on branches of the same master branch and multiple people change the same files.
So git won't know what code you want to keep, what codes is redundant and what code you'd want to get rid of.
You'll have to manually do that.

We'll now try this out.
Create a new branch called "quick-test". Will make the notes on that and merge after this.

## On quick-test branch

Will add some content to the index.html (including adding the index.html file)
Do now a git status to check and a git diff to check.
Can do a shorthand commit in git to skip over the add when you're only modifying files. 
Instead of -m in your commit, with having done a git add, you use -am in commit.
In -am, the 'a' stands for add, and 'm' for message.
-So you add and state a message for the commit.
--NOTE: this only works for modified files, as a new file would need to be staged in git first.

Will now update the master branch in the index.html file with a similar update to what was made in index.html on the quick-test branch.
Have made the updates now in the master branch, so will now begin creating the error.
The error here is the following: made changes in the master branch, didn't commit them and then attempted to change back to the alternate branch where the master branch changes conflict with the feature branch changes.
There's a method called stashing where you stash your changes without committing them, but it won't be covered in this tutorial.
-You stash your changes somewhere and then can retrieve them later, like a temporary holding place.

In this case however, simply ran a git commit on the master document to resolve the error, and be able to switch back to the feature branch.
Will now run a diff locally with master and then merge.
Git diff syntax: "git diff master" where master refers to the master branch.
Git merge syntax: "git merge master" where master refers to the master branch.
--Note this merges the master branch updates into the feature branch. (Ie from master to feature)
-Now generally merging locally isn't the regular pattern, and it isn't for merging branches into master.
-But master gets updated as you go along as you're working on your project, because other people are merging into master and you don't have those changes in your branch.
-You don't want to get too far behind the master as you're working becaue then it's going to be really difficult to merge later.

So as changes are made to master in the GitHub repo, you're going to want to pull those down to your local master branch.
Then whatever feature branch you're working off of, you use "git merge master" to keep your feature branch up to date with what's going on in master.
Will now git merge master.
Conflict came up: merge conflict in index.html doc
There are a couple of ways to fix merge conflicts: GitHub provides an interface to fix them.
You can fix it in the terminal.
But the easiest way to fix merge conflict is directly in the code.
Good code editors like VS Code let you choose what action you want to take on the merge conflict using a range of buttons.
But you can also just directly edit it yourself.
It also indicates on the error what your current code on the branch is and what the incoming change that it would become is as well.
In this case we'll delete the additional lines and save both changes.
This lets get know how we want to handle the conflict.
Now we need make a commit as we've fixed the merge conflicts.

Will now commit.
Committed successfully.
Feature branch is now aligned again with master branch.

## Undoing in Git:

