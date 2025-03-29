# Merge Conflict Practice

Don't worry, it's not as scary as it sounds!

## What is a merge conflict?
When collaborating on code, sooner or later you're going to get something
called a merge conflict. A merge in general is simply the process of
integrating changes from another branch to our current working branch.

In most cases, Git know what to do in merge process but there are some
cases when "conflicts" happens and we have to enter in action. Generally
speaking, a conflict occurs when two people changed the same lines
in the same file, or if one person decided to delete it while the other person 
decided to modify it, or any sort of similar scenario. In these kinds of situations,
Git simply cannot know what is correct. So, Git will then mark the file as having a conflict - which you'll
have to *resolve* before you can continue your work.

## Let's make a conflict!
1. Clone this repository if you haven't already
2. cd into the project from your command line (`cd merge-conflict-practice`)
3. Enter command `git status` and make sure you are on the master branch
4. Open up VsCode and navigate to the animals.md file.
You should see something like:
![](/img/recipe.png)
5. Add two or three other animals to the list, right below "5. Lion"
6. Add and commit your changes, but don't push!
7. After you have added and committed, run command `git merge origin/partner`.
The branch "partner" is a branch we already made which will create a conflict with
the changes you just made. After running the merge command you should see something
like this:
![](/img/conflict.png)
8. Move on to the next step to resolve this conflict!

## Now how do we resolve this conflict?

1. In VsCode open up animals.md file. 
You should see a bunch of weird markers like `>>>`, `===`, and `<<<`:
![](/img/conflicting-file.png)
*NOTE: the actual animal names and what not will differ based on what you added!*
2. The file markers are telling us that Git has found that there are changes made
to the same place in the file by two different branches, and it wants to know
who's changes to take. In between `<<<<< HEAD` and `=======` are your changes.
3. These are the changes we want, so all we need to do is delete what's in between 
`=======` and `>>>>>>> origin/partner`.
4. Now get rid of the extra markers  `>>>`, `===`, and `<<<`
5. Save the file
6. Go to terminal and enter `git status`, you should see that animals.md
has been modified
7. Add, commit, and push your changes
8. Pat yourself on the back, you resolved a merge conflict!


