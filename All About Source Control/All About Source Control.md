# All About Source Control

Wrote a code for development, defined variables performed a dry run, and undertook multiple code revisions only to discover that the previously written code was better than the latest one. Reverting to the previous code well is not an easy thing to do. At times, it was a difficult task on the developer's end.

The **modification, update, reversion** formulated **Version Control System**. Version Control System keeps track of files modification, deletion of files, or folder in a working director.
Let's discuss the version control Systems more in detail.

## Version Control System

What is **Version Control System?** Essentially, Version Control Systems allows recording changes to files over time to view specific versions of those files later on.

Version Control Systems, or VCS, are specialized software. The primary purpose is to manage the codebase changes whenever changes are applied. Also, with the help of a *Version Control System*, we can recall a specific version later.

## Why do you need one?

Did you work on a project that required recalling the specific changes made to each file? If yes, how did you manage and control each version? Maybe tried to duplicate and rename the files with suffixes like **“review,” “fixed,” or “final”**, as shown in the below image.

![https//devtouploadss3amazonawscom/uploads/articles/tns0euslbixw4yia4ppzpng](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tns0euslbixw4yia4ppz.png)

All those problems can solve by using a Version Control System or VCS. A Version Control System tracks each change made to every project file and provides a simple way to compare and roll back those changes.

## Types of Version Control system

Version Control Systems have three types, which are following.

**1. Local Version Control System**

**2. Centralized Version Control System**

**3. Distributed Version Control System**

### Local Version Control System

In the **Local Version Control System**, the user manages and controls all the file changes within the local system. All changes are saved in a local database. Revision Control system (RCS) is one of the most common Versions Control System tools. As seen in the image below, each developer has their version control history, and they are only limited to the local databases.

![https//devtouploadss3amazonawscom/uploads/articles/ruhlws0e5fi468fcds1ypng](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ruhlws0e5fi468fcds1y.png)

### Centralized Version Control System

A **Centralized Version Control System** contains one repository in which users have stored a working copy of the project they are working on. Users need to commit their changes to the repository to update and reflect its changes.

![https//devtouploadss3amazonawscom/uploads/articles/j9vr4j6ppd5etbiacf5bpng](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/j9vr4j6ppd5etbiacf5b.png)

### Distributed Version Control System

A **Distributed Version Control System** contains multiple repositories. All users have their repositories and working copies. Committing the changes will not give other users access to the changes because the commit will only reflect in the local repository. The user needs to push the changes to the central repository. The most popular distributed version control systems are **Git** and **Mercurial**.

![https//devtouploadss3amazonawscom/uploads/articles/bthgl1k5ecc02xpz0xa4png](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bthgl1k5ecc02xpz0xa4.png)

## Source control systems

### • TFVC

• Git
• Subversion

# Branches

**Git branching** allows developers to diverge from the production version of code to fix a bug or add a feature. Here is an **example** of how git branches are helpful. Let's say you need to work on a new website feature, create a branch and checkout to the new branch, and start working. Once you complete new features, you can merge your changes to the **master branch**.

![https//devtouploadss3amazonawscom/uploads/articles/2x7qrgsfcowmj5c55oorPNG](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/2x7qrgsfcowmj5c55oor.PNG)

As shown in the image above, we have a default branch, the **master branch**. To add new features to the project, we can easily create a new branch and start working; someone else from the team member can also contribute to the Repository by creating a **new branch.**

## How to create a branch

### Option 1: Creating a branch & Checkout

You can create your new branch with the following command.

```
git branch <new_branch>
```

> Replace <new_branch> with whatever name you want.

and with the following command, you can list the branches

```
git branch
```

> The current local branch will be marked with an asterisk (*).

If the asterisk is not visible on your new branch, it means you are not on the new branch. With the following command, you can easily check out the new branch.

```
git checkout <new_branch>
```

Now, you can use the `git branch` to check which branch you are currently using. The current branch will be marked with an asterisk(*).

### Option 2: Creating a branch using checkout

Through this command, you can easily create a new branch and checkout to the branch simultaneously.

```
git checkout -b <another_branch>
```

And with the `git branch` you can check on which branch you are currently. The current branch will be marked with an asterisk(*).

### delete a branch

To **delete the local branch**, use the following command.

```
git branch -d my-branch-name
```

The `-d` option only deletes the branch if it has already been merged. The `-D` option is a shortcut for --delete --force, which deletes the branch irrespective of its merged status.

```
git branch -D my-branch-name
```

## Merging

Once you complete your work with the branches, you need to use the Merge method. Merging takes your branch changes and merges them to the main branch, the master branch, by default. Depending on the commit history, git performs two ways of merging.

1. Fast-forward or two-way merging
2. Three-way merging

### Fast-forward

In the **Fast Forward method,** where merging includes only snapshots, let me clear more with an example. Let's say you have completed your work on the feature branch (which is your new branch), and you merge the changes with the master branch, which is the default branch in git. Assume that the master branch has no more commits from the time you created a new branch.

![https//devtouploadss3amazonawscom/uploads/articles/j7nu9ae20n7fkjes1y7hpng](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/j7nu9ae20n7fkjes1y7h.png)

When the feature branch has to be merged with the master branch, the two of the most recent commits on either of these branches, C3 and F2, compare and merge automatically, unless no merge conflict error occurred—called **fast forward or two-way merge**

.

### Three-way merge (or recursive)

The **Three-Way process** involves three snapshots, two of the snapshots are involved in the two-way process (Fast-Forwarding) as already discussed. The third one is the base file or the Parent, with which two files are compared.

![https//devtouploadss3amazonawscom/uploads/articles/3sd3qfi8rqcoa36z8zbkpng](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3sd3qfi8rqcoa36z8zbk.png)

As you see, C3 is the Parent with which C4 and F2 files are compared for merging.

### How merging works

As we have already discussed Merge in detail, let's do some practical hands-on. We have also learned how to create a new branch, the file created inside the new branch will not be accessible to the master branch, which is our default branch in Git, until we merge the **new branch** with the **master branch**.

### Merging branches in a local repository

Use `git checkout` to switch the branch you want to merge into to merge locally. The branch we usually switch first is typically the master branch, which is the default branch. Next, use the `git merge` and specify the branch name to merge the new branch with the master branch. This method is also called Fast Forward Merge.

Create a new branch using the command `git branch new branch` you can change the `new branch` name specifically to your project feature, for example, `dev branch` and you can easily checkout using the `git checkout` command when you create a new file in the new branch you need to follow the `staging and committing` procedure. Once the process is completed, you can follow the commands given below;

```
git checkout master

git merge <newbranch>
```

### Aborting merge

You can also abort the merging process in case of merge conflict issues with the following command.

```
git merge --abort
```

## Merge only one specific commit

Sometimes we need to merge a specific commit; use cherry-pick. Let's discuss what cherry-pick is.

### Cherry-pick

**Cherry-pick** allows you to choose the specific existing commit to include in another branch, and with the help of cherry-picking, you can merge a particular commit of exiting.

![https//devtouploadss3amazonawscom/uploads/articles/0e3hzw0svehplkfzkhf3png](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0e3hzw0svehplkfzkhf3.png)

Create a new branch, checkout to the new branch, add the files, stage, and then commit your changes in the new branch. Use the following command to get the specific commit ID.

```
git log --pretty=format:"%h %s"
```

You can easily merge the specific commit ID to the default branch master using commit ID. Once copied, the commit ID is then checked out to the master branch and used the following command.

```
git checkout master
git cherry-pick 12670fd
```

## Merge Conflict

Merge conflicts may occur if completing changes are made to the same line of a file, or if the file that someone else is attempting to edit is deleted. We will discuss further how to resolve to merge conflict issues using Github.

## What is Rebase?

If you are collaboratively working on a project with other developers, then you would notice very quick changes on the repository, and it would not be the same repository you have started to work with, as new features and changes would be added. This is where rebasing comes into action. Rebasing takes commits and stores them in a temporary location. It takes the latest version and adds the commit on top of the latest version. So in this way rebasing ensures that your commits are added to the current state of the project, and not to the old state of the project.

### Rebase Vs Merge

Rebasing and rebasing both are designed to integrate change from one branch to another branch but in different ways.

Let's say we are working on a project with a repository having committed. Merge will result as combinations of commits, whereas rebase will add changes in the feature branch starting from the last commit of the master branch.

1. When you rebase a feature branch onto the master, you move the base of the feature branch to the master branch's ending point.
2. Merging takes the content of the feature branch and integrates it with the master branch. As the result, only the master branch is changed. The feature branch remains the same.
3. Merging adds a new commit to your repository history.

### How Rebase Works

To Rebase the feature branch onto the master branch, use the following commands:

```
git checkout feature
git rebase master
```

## Squash

Git squash is a technique that helps you to take a series of commits and consider it to a few commits. for example, Assume that you have a series of commits with the help of git squash we can me all the n number of commits to a single commit.

Squashing is mainly used to describe a large number of commits, to make it to a small number of meaningful commits so that you can make the git history clean.

Git squash is also used for the merging of branches. Most developers also advise you to always squash the commits and rebase them with the parent branch(master).

So when you are squashing and rebasing with the parent branch, the history of the master branch will be way clean, and you will have meaningful commits.

### How to do git squash

First, we will use the following command to print the logs in one line.

```
git log --oneline
```

Let's squash the last three commits. These commits explain that we have added a new file. We can use the following command to squash the last three commits.

```
git rebase -i HEAD~3
```

The Interactive -i command will open up the editor which will have the three commits. Just add the

**`s`** word to the last commit as shown in the image below and save the file.

After writing and quitting your file using vim, the editor will open another editor having the commits, you can change the commits, as shown in the image below. And when you are done with your changes, git squash will merge the commits to one.

You can check whether the last three commits are merged by the git squash using the command below:

```
git log --oneline
```

## .gitignore

**`.gitignore`** file is a file that specifies the files or folders that we want to ignore.

1. Let's say we want to ignore a text file; with the help of the **.gitignore file**, we can easily ignore the text file. Assume that you created a `readme.txt` file in my working directory, and you want to ignore the file; write the readme.txt file to the `.gitignore` file.
2. And if you want to ignore files using the extensions, write the `.txt` to the `.gitignore` file.
3. Let's say you want to ignore a folder. Assume that you are working on a python project and usually use the venv environment in python. You can write the `venv/` to the `.gitignore` file to overlook this folder.

### How does gitignore work?

From the Git bash terminal, we can easily create the .gitignore file.

```
touch .gitignore
```

While using Vim to edit the .gitignore file, you can edit the file from the terminal with this command,

```
vi .gitignore
```

> Press I key to insert text into the .gitignore fileto quit :wq to successfully write and leave from the vim editor.

With the `git status` command, you can check whether the file is ignored or not.

## releases & version tags

**Tags** are a simple aspect of git; they allow you to identify specific release versions of code. You can think of a tag as a branch that does not change. Once you create the tag, it loses the ability to change the history of commits.

There are two types of git tags.

1. Annotated tags
2. Lightweight tags

### Annotated tags

**Annotated tags** store metadata such as author name, release notes, tag message, and data stored as an object in the git database. All this data is important for the public release of the project.

To create a tag using the following command.

```
git tag -a v1.0.0
```

In case if you want to add a tag message, then use the following command.

```
git tag -a v1.0.0 -m " Release version v1.0.0"
```

### Lightweight tags

**Lightweight tags** are the simplest way to add a tag to your git repository because they store only the hash of commit as lightweight tags do not contain extra information.

> Lightweight tags are essentially bookmarks to a commit; they are just a name and pointer to commit. - Bitbucket

To create lightweight tags, you can use the following command.

```
git tag v2.0.0
```

# Branch policies

Finally, it is possible to enforce one or more policies on pull requests to a specific branch. The interface for branch, policies is shown in the following screenshot and can be accessed by choosing the Branch policies option while managing the authorizations on a repository branch:

![Untitled](file://C:\Users\ashehzad\Downloads\Export-eee29308-1b9a-410a-8db0-e60fe765f9bb\All%20About%20Source%20Control%20f955a160f04d4f359bdebcbaf9c1f2c7\Untitled.png)

### Other tools for source control

• GitHub
• GitLab
• Subversion

# Complete Learning Resources

- [https://learn.microsoft.com/en-us/training/paths/az-400-get-started-devops-transformation-journey/](https://learn.microsoft.com/en-us/training/paths/az-400-get-started-devops-transformation-journey/)
  
- [https://learn.microsoft.com/en-us/training/paths/az-400-work-git-for-enterprise-devops/](https://learn.microsoft.com/en-us/training/paths/az-400-work-git-for-enterprise-devops/)