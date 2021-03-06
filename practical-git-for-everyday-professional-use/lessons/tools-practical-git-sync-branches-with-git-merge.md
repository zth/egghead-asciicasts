We're inside of a directory called `utility-functions`, which is a Git repo. Our project needs a new feature where we can take a string like `"My Favorite Songs"`, and convert it into a string that's lower case with dashes in between, to be used in a URL, `"my-favorite-songs"`.

To work on this new feature let's create and check out a new branch called `url-slug`, `git checkout -b url-slug`. Now I'll run `git branch` to make sure we are on our new branch as expected. Next, I'm going to create a new file in our directory called `getURLSlug.js`, `touch getURLSlug.js`, and we'll open that file in our code editor.

Now, I'll work on this new feature, so I'm going to create a `function` called `getURLSlug`. 

#### getURLSug.js
```javascript
function getURLSlug(words){
    return words
        .replace(/\s+/g, '-')
        .toLowerCase();
}
```

I'm going to open the `README.md` file for the project in my code editor. I'm going to add to our documentation of examples with a new example for the function that we just wrote.

#### README.md
```javascript
getURLSlug('My Favorite Songs');
//=> 'my-favorite-songs'
```

Now our new feature is complete, let's save and close this file. Back on our command line, let's run `git status`. We can see that we do have our modified `README.md` as well as the new function. Our feature is ready to go.

Let's stage the new feature, and then we'll `commit` it to our current branch. Now that our feature has been built and it's stable, it's ready to be combined back into our main `master` branch. The way we do that is first, we need to `checkout` the branch that we want to combine our current feature into, `git checkout master`.

Then we can run the `git merge` command, and give it the name of the branch that we want to merge into our currently checked out branch. In this case that's the `url-slugs` branch, `git merge url-slugs`. When we run the `git merge` command, Git automatically determines what type of algorithm to use to merge the two branches together.

In this case, our project history was linear enough that Git could use a `Fast-forward` merge to combine the histories together. If Git can't do this, then it uses what's called a three-way merge, where it will create a new commit based on the merge.

Your code editor will pop up, and all you need to do is save and close the file, and a new commit will be created, and the merge will be finished. Now that our merge is complete, let's run `git status`.

It looks like everything is good to go, and we can run `git push` to push to our remote. If we want, we can delete this extra branch by running `git branch -d` for delete, and the name of the branch, because it's been safely merged into our main master branch, `git branch -d url-slugs`.