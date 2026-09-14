# Working With Branches

### Critical
- Branching...why is it? why use it?
- Understanding Git HEAD
- Git Branch
- Git Switch
- Git Checkout

### Important
- Deleting & Renaming Braches
- Master vs. Main Branch

### Nice To Have
- HEAD & Refs behind the scenes

## Contexts
On large projects, we often work in multiple contexts:
1. You're working on 2 different color scheme variations for your website at the same time, unsure of which you like best
2. You're also trying to fix a horrible bug, but it's proving tough to solve. You need to really hunt around and toggle some code on and off to figure it out.
3. A teammate is also working on adding a new chat widget to present at the next meeting. It's unclear if your company will end up using it.
4. Another coworker is updating the search bar autocomplete.
5. Another developer is doing an experimental radical design overhaul of the entire layout to present next month.

Bracnhes are an essential part of Git!

Think of branches as alternative timelines for a project.

They enable us to create separate contexts where we can try new things, or even work on multiple ideas in parallel.

**If we make changes on one branch, they do not impact the other branches (unless we merge the changes)**

## Master Branch
In 2020, Github renamd the default branch from **master** to **main**. The default Git branch name is still **master**, though the Git team is exploring a potential change.

### (HEAD -> master)
We'll often come acroos the term **HEAD** in Git.  
HEAD is simply a pointer that refers to the current "location" in your repository. It points to a particular branch reference.  
So far, HEAD always points to the latest commt you made on the master branch, but soon we'll see that we can move around and HEAD will change.

## Viewing Branches
Use `git branch` to view your existing branches. The default branch in every git repo is master, though you can configure this.  
Look for the `*` which indicates the branch you are currently on.

## Creating Branches
Using `git branch branch-name` to make a new branch based upon the current HEAD  
This just creates the branch. It does not switch you to that branch (the HEAD stays the same)

## Switching Branches
Once you have created a new branch, use `git switch branch-name` to switch to it.

### Another way of switching
Historically, we used `git checkout branch-name` to switch branches. This still works.  
The checkout command does a million additional things, so the decision was made to add a standalone switch command which is much simpler.  
You will see older tutorials and docs using checkout rather than switch. Both now work.

#### Git Docs
> `git-checkout` - Switch branches or restore working tree files

### Creating & Switcing
Using `git switch` with the `-c` flag to create a new branch AND switch to it all in one go.  
Remember `-c` as short for "create"

Older way of **Creating & Switching** is `git checkout -b branch-name` 

#### Note
- If there are CHANGES that will be overwritten when you try to SWITCH, Git abort switching and will notify you to commit or stash those changes first.
- If there are CHANGES that will not overwrite any files, that unstanged file will follow you whenever you switch branches.

## Deleting Branches
`git branch -d branch-name`

### Note
- You cannot delete a branch you're currently active.
- If you switch branch and try to delete unmerged branch using `-d` it will abort and notify you to use `-D` instead if you're so sure.

## Renaming Branches
1. Switch to the branch that you want to rename.
2. `git branch -m new-branch-name`
