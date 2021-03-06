We're inside of a directory called `utility-functions`, which is a git repo. Let's run `git branch` to create a new branch on our repo. We need to give this a name so we'll say `new-feature`. Now we can review all of our branches in our repo by running `git branch` command by itself.

This shows that we have two branches in our project. We have the `master` branch and we have the `new-feature` branch that we just created. The asterisk next to `master` shows us that the `master` branch is what we have currently checked out.

![Master branch is checked out](../images/tools-practical-git-isolate-feature-development-with-git-branch-master-checked-out.png)

What that means is if we make commits right now, they're going to get added to the `master` branch and not any of the other branches in our repo. Because of this, git branches are useful for developing features on their own. When we ran the git branch command with a name, it created a new branch by copying the currently checked out branch.

We can switch to a different branch by running `git checkout` and then the branch name. Let's switch to the `new-feature` branch. If we run `git branch` again, we can see that `new-feature` is the checked out branch. Since we haven't added any commits to the new feature branch, it's currently identical to the `master` branch.

Let's create a new file called `newFeature.js`. Now when we stage and commit, the commit gets added to this branch instead of the `master` branch. If we look at the contents of this directory, we see our `newFeature.jf` file, but when we check out the master branch or any other branch, that file is not in the directory.

Git branches are extremely useful for developing features, bug fixes, or anything in isolation. Once that work has been finished and is stable, we can merge them back into the central branch.

Since we frequently check out branches immediately after they're created there's a shortcut command to do both at the same time. We run `git checkout -b`, and then the name of the branch. If we run `git branch` we can see that this worked as expected. It created a new branch called `new-feature-2` and checked out that branch.

Another useful shortcut command is `git checkout -`. This will switch to the branch that we had checked out last. We're currently on `new-feature-2`, and if we run this command we will be on `master`. If we run it again we'll switch back to `new-feature-2`.