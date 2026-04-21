# How to Create and Switch Branches

Branches are one of the most powerful features in Git. They allow you to create a separate "workspace" to try out new ideas, fix bugs, or build new features without affecting your main project code.

Here is the sequence of commands you will use to create a new branch, switch to it, make changes, and save them. Below, we explain what each command does step-by-step:

```bash
git branch my-new-feature
git checkout my-new-feature
echo "Some new ideas" > idea.txt
git add idea.txt
git commit -m "Add new idea to feature branch"
git push -u origin my-new-feature
```

*(Tip: You can also use `git checkout -b my-new-feature` or `git switch -c my-new-feature` to create and switch to a branch in one single step!)*

## Step-by-Step Explanation

* **`git branch my-new-feature`**
  This creates a new branch named `my-new-feature`. Think of it as creating an exact copy or snapshot of your project at this current moment. However, this command *only* creates the branch; it doesn't move you there yet.

* **`git checkout my-new-feature`**
  This switches you from your current branch (e.g., `main`) over to your new `my-new-feature` branch. Any changes you make from now on will only affect this new branch. *(Note: Newer versions of Git also use `git switch my-new-feature` for this).*

* **`echo "Some new ideas" > idea.txt`**
  This is a standard terminal command representing you doing some work—in this case, creating a new file named `idea.txt` on your new branch.

* **`git add idea.txt`**
  Just like we did previously, this places your new work into the staging area so it's ready to be saved.

* **`git commit -m "Add new idea to feature branch"`**
  This saves the changes permanently to your new branch. The original branch you started from is completely untouched by this new work!

* **`git push -u origin my-new-feature`**
  Finally, if you want to sync your new branch to GitHub so others can see it (or just as a backup), you push it. The `-u` flag helps set up the connection, so the next time you need to push changes to this branch, you can just type `git push`.

## What to do When You Are Done

Once you are finished working on your branch, you have two main options: merge your changes into your main project, or delete the branch if the experiment didn't work out.

### Option 1: Merging Your Branch (Success!)

If your feature works perfectly and you want to add it to your main code:

```bash
git checkout main
git merge my-new-feature
git push
```

* **`git checkout main`**: First, you must switch back to the branch you want to merge *into* (usually `main`).
* **`git merge my-new-feature`**: This takes all the hard work from your `my-new-feature` branch and permanently combines it into the `main` branch local to your computer. 
* **`git push`**: Finally, upload your newly merged `main` branch to your remote GitHub repository.

*(Tip: After a successful merge, your old `my-new-feature` branch still exists! It is safe and usually a good practice to delete it so your workspace stays clean. You can delete a successfully merged branch using `git branch -d my-new-feature`).*

### Option 2: Deleting Your Branch (It Didn't Work Out)

If you made a mess or the idea just didn't work, you can safely delete the branch and pretend it never happened. Your `main` branch is still completely fine!

```bash
git checkout main
git branch -D my-new-feature
```

* **`git checkout main`**: You cannot delete the branch you are currently standing on, so switch back to `main` first.
* **`git branch -D my-new-feature`**: The uppercase `-D` flag *forcefully* deletes the branch and all its unmerged changes. Poof!

### What is the difference between `-d` and `-D`?
Git provides a built-in safety net when deleting branches to prevent you from accidentally losing work.

* **Lowercase `-d` (Safe Delete)**: It will only delete the branch if you have already successfully merged its changes into your main project. If you try to use it on a branch with unmerged changes, Git will stop you and show an error. Use this to clean up a branch *after* a successful merge.
* **Uppercase `-D` (Force Delete)**: It will delete the branch *no matter what*. Use this only when you are 100% sure you want to permanently throw away the work on an unmerged branch because you will not be able to easily get those changes back.

### Deleting a Branch on GitHub (Remote)
When you delete a branch using `-d` or `-D`, it only deletes the branch *locally* on your computer. If you previously pushed that branch to GitHub, it will still exist there!

To tell GitHub to also delete the branch on the remote server, you have to run a special push command:
```bash
git push origin --delete my-new-feature
```
