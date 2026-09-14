# Commits In Detail

- `git commit -m "commit message"`
- `git commit -<< -EOF` "commit message" `<<EOF`

### Atomic Commits
When possible, a commit sohuld encompass a single feature, change, or fix. In other words, try to **keep each commit focust on a single thing.**

This makes it much easier to undo or rollback changes later on. It also makes your code or project easier to review.

### Commit Messages: Present Or Past Tense?
Present-Tense Imperative Style?

From the Git Docs: 
>Describe your changes changes in imerative mood, e.g. "make xyzzy do frotz" instead of "[This patch] makes xyzzy do frotz" or "I changed xyzzy to do frotz", as if you are giving orders to the codebase to change its behavior.

#### Imperative (a.k.a present tense)
- Should read like: `Make foo do something`
- Git uses the same imperative style and it shows when you do merges with commit messages: `Merge pull request #666 in kek from lord`
- It tells someone what applying thatt commit will do, so it should read something like `If I apply this commit, it will [make foo do something...]`
- More concise

### Git Commit
Running **git commit** will commit all staged changes. It also opens up a text editor and prompts you for a commit message.

### Git Log
- `git log`
- `git log --abbrev-commit` - Instead of showing the full 40-byte hexadecimal commit ojbect name, shows a prefix instead.
- `git log --oneline` - Shows every commits one line each.

### Amending Commits
Suppose you just made a commit and then realized you forgot to include a file! Or, maybe you made a typo in the commit message that yo want to correct.

Rather than making a brand new separate commit, you can "redo" the previous commit using the --amend option

> This is only if you made a mistake just one commit ago.

- `git add file.txt` - If you forgot to add a file after the last commit.
- `git commit --amend`

### Ignoring Files
We can tell Git which files and directories to ignore in a given repository, using a **.gitignore** file. This is useful for files you know you NEVER want to commit, including:
- Secrets, API keys, credentials, etc.
- Operating System files (.DS_Store on Mac)
- Log files
- Dependencies & packages (e.g., Node packages)

Create a file called .gitignore in the root of a repository. Inside the file, we can write patterns to tell Git which files & folders to ignore:
- `.DS_Store` will ignore files named .DS_Store
- `folderName/` will ignore an entire directory
- `*.log` will ignore any files with the `.log` extension