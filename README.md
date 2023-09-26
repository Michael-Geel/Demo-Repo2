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