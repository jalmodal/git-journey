# Merging Branches

### Critical
- Fast Forward Merges
- Git Merge & Commits
- Resolving Merge Conflicts

### Nice To Have
- Using VSCode to Resolve Conflicts

## Merging
Branchhing makes it super easy to work within self-contained contexts, but often we ant to incorporate changes from one branch into another!  
We can do this using `git merge` command

### Common Workflow
```
- Master branch/
  - Feature branch
```

The merge command can sometimes confuse students early on. Remeber these two merging concepts:
- We merge branches, not specific commits
- We always merge to the current HEAD branch

### Merging Made Easy
**To merge, follow these basics steps:**

1. Switch to or checkout the branch you want to merge the changes into (the receiving branch)
2. Use the `git merge` command to merge changes from a specific branch into the current branch.

```
git switch master
git merge bugfix 
```

**This is called A Fast-Forward**  
Master simply caught up on the commits from Bugfix

### Not All Merges Are Fast Forwards
This happens all the time. Imagine one of your teammates merged in a new feauture or change to master while you were working on a branch  

**What happens when I try to merge?**  
Rather than performing a simple fast forward, git performs a "merge commit"  
We end up with a new commit on the master branch.  
Git will prompt you for a message.

## Merge Conflicts
Depending on the specific changes you are trying to merge, Git may not be able to automatically merge. This result in **merge conflicts**, which you need to manually resolve.

When you encounter a merge conflict, Git warns you in the console that it could not automatically merge.

**It also changes the contents of your files to indicate the conflicts that it wants you to resolve.**

```
<<<<<<< HEAD
I have 2 cats
I also have chickens
=======
I used to have a dog :(
>>>>>>> bug-fix
```

### Conflict Markers
The content from your current HEAD (the branch you are trying to merge content into) is displayed **between the <<<<<<< HEAD and =======**

### Resolving Conflicts
Whenever you encounter merge conflicts, follow these steps to resolve them:
1. Open up the file(s) with merge conflicts
2. Edit the file(s) to remove the conflicts. Decide which branch's content you want to keep in each conflict. Or keep the content from both.
3. Remove the conflict "markers" in the document.
4. Add your changes and then make a commit!
