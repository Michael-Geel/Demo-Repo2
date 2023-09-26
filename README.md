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