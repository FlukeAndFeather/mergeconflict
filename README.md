# README

## Resolving merge conflicts

Merge conflicts. As the name implies, they're terrifying. No one likes conflict, right? But they're an inevitable part of collaborative coding, so let's get some hands-on experience with resolving them.

## Creating the conflict

1. Fork this repo.
2. Clone the forked repo [make sure you clone your fork, `*yourusername*/mergeconflict`, not mine, `FlukeAndFeather/mergeconflict`].
3. Create a new branch called `dev` and check it out.
4. Edit README.md. Make a note of where you edited it!
5. Check out `main` branch.
6. Make a *conflicting* change. Change the same line as you did in step 4, but do it differently.
7. Return to the `dev` branch.
8. Merge `main` into `dev`

## Resolving the conflict

You should see an error message that includes something like:

> `CONFLICT (content): Merge conflict in README.md`

If you open README.md, you'll see git inserted text to explain the merge conflict.

```
<<<<<<< HEAD
[The changes you made in the dev branch]
=======
[The changes you made in the main branch]
>>>>>>> main
```

You have three options now.

1. Accept the current change (i.e., the one in `dev`).
2. Accept the incoming change (i.e., the one in `main`).
3. Use your judgement to merge the changes manually.

For option 1, delete `<<<<<<< HEAD`, and everything from `=======` to `>>>>>>> main`. This only leaves the changes from the dev branch.
For option 2, you'd do the complement. Delete everything from `<<<<<<< HEAD` to `=======`, then delete `>>>>>>> main`.
For option 3, you merge the two changes as you see fit. Write the new code you want, then delete the text added by git (i.e., everything from `<<<<<<< HEAD` to `>>>>>>> main`).

After you've finished editing the text, let git know you're done by committing.

`git commit -a -m "merge main into dev"`

Then call `git log` to verify it worked.

## Summary

Congratulations, you've resolved a merge conflict! See, they're not so bad. Here are the core ideas.

* Git can automatically merge code changes when they occur on different lines.
* Merge conflicts happen when two branches have different changes to the same code.
* Follow git's decorators (`<< HEAD`, `>> [other branch]`) to find the conflict.
* Resolve conflicts manually, then commit to finish the process.
