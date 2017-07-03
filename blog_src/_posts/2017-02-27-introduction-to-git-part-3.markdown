---
layout: post
title: "Introduction to Git and GitHub - Part III"
description: "How to resolve Merge Conflicts in Git"
tags: ["Git","GitHub"]
---

* This post deals with the dreaded word of "Resolving Merge Conflicts" and how it isn't as bad as we think it is!<br>
* This often happens when multiple people work on the same branch or when multiple branches are in play and they don't get pushed sequentially!<br>
* The only thing you should remember in Git is you cannot break things. You can always go to your previous state and re-start your work again! It is saved as long as you push it properly! 
* Also, Git Merge Conflicts only occur on local systems not on the Git Server, so in case you are facing a Merge Conflict it will not stop your project, just your progress will be halted.

##### What are Merge Conflicts and how do they occur?
* Git being a Version Control System, the act of 'merging' is simply adding your changes that you've made to your copy of the project repository to the main project repository and almost most of the time this process goes on smoothly.<br> 
* However there is a case when two or more people try to access the same file and make changes to it, there is a chance that Git might not be able to figure out what to do and this is where it leads to Merge Conflicts happenning.<br>  
* Merge Conflicts usually occur in the case where 'Delete Mode' has occurred! If say, one user has deleted a file and another user has modified the contents of that file, then a Merge Conflict occurs!<br>

##### How to resolve a Merge Conflict?

* When faced with a Merge Conflict, the first step is to calm down and believe the end of the world isn't here! After that try to understand what just happened.<br>
* Open up your terminal and enter the command `git status` to see what has happened!
{% highlight git %}
$ git status
# On branch contact-form
# You have unmerged paths.
#   (fix conflicts and run "git commit")
#
# Unmerged paths:
#   (use "git add <file>..." to mark resolution)
#
#       both modified:   src/team.html
#
no changes added to commit (use "git add" and/or "git commit -a")
{% endhighlight %}

* In this example, you can see that since both the users modified the file called team.html in the src folder a merge conflict has occurred. Now you can go to the file and see where the conflict is! If you open the file you will see a line as follows:
{% highlight git %}
<<<<<<< HEAD
<p> This repository is the work of Salman</p>
=======
This repository is the work of Salman and Hrily</p>
>>>>>>> development
{% endhighlight %}
* The contents after the HEAD tilte originate from your current working branch. After the angle brackets, Git tells us where (from which branch) the changes came from. A line with "=======" separates the two conflicting changes.<br>
* Now resolving them is a simple task. All you have to do is remove the angle markers and in place of them place the text that you need. The above text can simply be replaced with the following and the Merge Conflict is solved!
{% highlight git %}
<p> This repository is the work of Salman Shah and Hrily</p>
{% endhighlight %}

* Now after you have done this, you need to mark your file as 'resolved for Git Merge Conflicts' To do that, you need to execute the command `git add <filename>`. In this case the command would be:
{% highlight git %}
git add src/team.html
{% endhighlight %}

* With this we have solved the problem of resolving Merge Conflicts in Git!<br>

* This is all that you need to start using Git and GitHub in your projects and this brings us to the end of this small tutorial series on Git and GitHub!  



