# How to Create and Connect a Git Repository

This short guide will help you create a new repository (a project folder tracked by Git) on your computer and connect it to GitHub.

Here is the entire sequence of commands you will use. Below, we explain what each command does step-by-step:

```bash
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin <your_repository_url>
git push -u origin main
```

## Step-by-Step Explanation

* **`echo "# test" >> README.md`**
  This creates a new file called `README.md` and adds the text `# test` into it. A README file is typically used to describe what your project is about.

* **`git init`**
  This is how you start using Git in your project. It initializes a brand new, empty Git repository in your current folder.

* **`git add README.md`**
  Git doesn't automatically track your files. This command tells Git to start tracking the changes you made to the `README.md` file and prepares it to be saved.

* **`git commit -m "first commit"`**
  This takes a "snapshot" of the files you have added. The `-m "first commit"` part attaches a short, descriptive message to this snapshot so you know what changes were made.

* **`git branch -M main`**
  Git uses "branches" to keep track of different versions of your project. This command ensures your primary branch is named `main` (the standard name for the primary branch).

* **`git remote add origin <your_repository_url>`**
  This step connects your local repository (on your computer) to the remote repository on GitHub. We give this connection a shortcut name called `origin`. **Make sure to replace `<your_repository_url>` with the actual URL of your repository!**

* **`git push -u origin main`**
  Finally, this command uploads (pushes) your committed changes from your local `main` branch to the `origin` repository on GitHub. The `-u` tells Git to remember this connection, so next time you can just type `git push`.
