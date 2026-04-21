# How to Stage and Commit Your First File

Now that you have a Git repository set up, it's time to learn how to track the files you are working on. In Git, saving your work is a two-step process: first you **stage** the files, and then you **commit** them.

Here is a common sequence of commands you will use when adding and saving your work. Below, we explain what each command does step-by-step:

```bash
echo "Hello Git" > my_first_file.txt
git status
git add my_first_file.txt
git status
git commit -m "Add my first file"
```

## Step-by-Step Explanation

* **`echo "Hello Git" > my_first_file.txt`**
  This is a basic terminal command that creates a new text file named `my_first_file.txt` and puts the text "Hello Git" inside it. This simply represents you creating or editing a file in your project.

* **`git status`**
  This command is your best friend in Git! It tells you exactly what is going on in your repository at any given time. Right now, it will tell you that there are "untracked files", because you just created a new file that Git isn't watching yet.

* **`git add my_first_file.txt`**
  This is the first step of saving. It places `my_first_file.txt` into the **Staging Area**. Think of the staging area as a moving box. You are telling Git: *"I want to pack this specific file into the next box."* 
  *(Tip: If you want to stage all the files you've changed at once, you can use `git add .`)*

* **`git status`**
  Running this again will show that your file is now in the staging area (it usually shows up in green text as "changes to be committed").

* **`git commit -m "Add my first file"`**
  This is the final step of saving. It takes a permanent snapshot of everything you put into the staging area and saves it to your Git history. 
  The `-m` stands for message. You should always provide a short, descriptive message describing what you changed, so you and others can easily understand the history of your project later on.
