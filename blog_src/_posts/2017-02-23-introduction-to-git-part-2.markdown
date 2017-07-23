---
layout: post
title: "Introduction to Git and GitHub - Part II"
description: "Introduction to Branches in Git"
tags: 
- Git
- GitHub
- Version Control
languages:
- Git
---

A lot of times it is difficult to coordinate changes in a project while using Version Control especially when there are more than one contributors in a particular repository! At such times it is important to use a particular feature of Git called <b>branch</b>. 

##### What are branches and how to use them?

![git branch commands](/images/post2_img1.png)

Branches are a feature of Git used when multiple collaborators are working on the same project, but want to work on different parts of the project. This is where the concept of branches in Git is particularly useful. A branch is like a copy of the original code which runs parlallely with other branches in the code repository! The default branch in a GitHub repository is called __master__. To create a new branch you need to execute the following command:

```bash
git checkout -b <branch_name>
Switched to a new branch 'salman'
```

In case you are looking to switch back to your __master__ branch on your local repository, type in the following commands to get back again:
```bash
git checkout master
git checkout <branch_name>
```

If you are looking to delete a branch first make sure you aren't currently on that branch! Use <b>git checkout</b> to move to another branch and then use the following commands to delete the branch.
```bash
git branch -d <branch_name>
```

In case your branch is not being deleted because you have certain unmerged changes and you really want to delete them without merging your changes, you can use the following instructions!
```bash
git branch -D <branch_name>
```


##### How to sync your branch with the Master branch
 
If you are looking to sync your branch with your master, as in update the online changes that someone else has made to the __master__ branch to your branch, type in the following commands:
```git
git pull origin master
```

P.S. This can be extended to all branches and isn't restricted to the __master__ branch alone!

```bash
git pull origin <branch_name>
```

##### How to push branches on GitHub

![Create GitHub Account](/images/post2_img2.png)

Once you have your local changes made and committed, it is essential for you to push them on GitHub so that ohers can review them as well! To do this you can simply push your branch on to GitHub just like you would push the master branch to GitHub! After you're done working on them use the following commands to push your new branch on to GitHub.

```bash
git add --all
git commit -m "<your_message>"
git push origin <branch_name>
```

Check out the next tutorial to see how to resolve Merge Conflicts as and when you encounter them using Git.