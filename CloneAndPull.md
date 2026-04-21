# How to Clone a Repository and Pull Changes

Sometimes you don't want to start an entirely new project; instead, you want to download an existing project from GitHub to work on it, and later fetch any new updates that others have added. 

Here is the common sequence of commands you will use to copy an existing repository to your computer and keep it up-to-date. Below, we explain what each command does step-by-step:

```bash
git clone <repository_url>
cd <repository_name>
git fetch
git pull
```

## Step-by-Step Explanation

* **`git clone <repository_url>`**
  This creates a complete copy (or "clone") of an existing Git repository from the internet (like GitHub) onto your local computer. It downloads all the files, the entire project history, and all branches. Just replace `<repository_url>` with the actual link provided by GitHub.

* **`cd <repository_name>`**
  Once cloned, you need to "change directory" (`cd`) into the new folder that was just created so you can start using Git commands inside it.

* **`git fetch`**
  This command securely checks GitHub to see if anyone else has made changes or added new commits since you last downloaded them. It quietly downloads the necessary data but *doesn't* actively merge those changes into the files you are currently looking at. It's a safe way to check for updates.

* **`git pull`**
  This is how you actively update your project. It fetches the latest changes from GitHub *and* immediately merges them into your current local branch. Use this when you are ready to apply remote updates directly to your working files!

## Helpful Cloning Tips

### 1. Cloning into a Custom Folder
By default, Git creates a new folder with the exact same name as the repository you are downloading. If you want to download it into a folder with a different name, you can simply write your preferred folder name at the end of the clone command:

```bash
git clone <repository_url> <my_custom_folder_name>
```

### 2. Forking vs. Cloning
When you want to contribute to someone else's public project (where you don't have permission to modify their code directly), you will often hear about "Forking":
* **Forking** is a GitHub feature. Clicking the "Fork" button on GitHub creates a complete copy of their repository and puts it onto *your* GitHub account, giving you full control over it.
* **Cloning** is the step you take *after* forking to download your new copied repository to your computer.

Always **Fork** first if you don't have write access to the original repository, and then **Clone** your fork!
