# Addressing Common Git Errors and Mistakes

Everyone makes mistakes, especially when learning Git! The good news is that Git is designed to keep a robust history, meaning you can almost always retrieve or undo things.

Here are a few common commands and strategies used to handle errors, undo mistakes, or see what went wrong.

```bash
git log
git status
git restore <file_name>
git commit --amend -m "Updated commit message"
```

## Step-by-Step Explanation of Common Fixes

* **`git log`**
  If you are lost or confused and need to see the history of what has happened in your project, `git log` shows you a list of all your past commits. It displays the commit message, the author, and a unique ID for each commit. You can press `q` to exit the log view.

* **`git status`**
  When in doubt, always run `git status`. If a command fails or you aren't sure what to do next, this command frequently provides helpful hints (right in the terminal) on how to resolve conflicts, unstage files, or continue an operation.

* **`git restore <file_name>`**
  Did you make changes to an untracked file but you hate them and want to revert back to exactly how the file looked at your last commit? Use this command to discard your recent uncommitted local changes to that specific file. Be careful, as these discarded changes generally cannot be recovered!

* **`git commit --amend -m "Updated commit message"`**
  Did you accidentally make a typo in your last commit message, or forget to add one file to it? If you stage the forgotten file (`git add`) and then run this command, it will attach the file to your previous commit and let you easily update the message, rather than creating a brand new messy commit!

*(Tip: Always read the terminal output when Git gives you an error. It very often tells you exactly which command to run to fix the problem!)*
