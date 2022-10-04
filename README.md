# Git

Git Fundamental 
<img src="hero.svg">
By far, the most widely used modern version control system in the world today is Git. Git is a mature, actively maintained open source project originally developed in 2005 by Linus Torvalds, the famous creator of the Linux operating system kernel. A staggering number of software projects rely on Git for version control, including commercial projects as well as open source. Developers who have worked with Git are well represented in the pool of available software development talent and it works well on a wide range of operating systems and IDEs (Integrated Development Environments).

Having a distributed architecture, Git is an example of a DVCS (hence Distributed Version Control System). Rather than have only one single place for the full version history of the software as is common in once-popular version control systems like CVS or Subversion (also known as SVN), in Git, every developer's working copy of the code is also a repository that can contain the full history of all changes.

In addition to being distributed, Git has been designed with performance, security and flexibility in mind.

https://git-scm.com

## Access Models

If you have been using version control for a long time, you may remember systems
like CVS or Subversion with a centralized repository. demonstrates how
changes were made in Subversion’s centralized system. In this system, each time you
wanted to save a snapshot of your work to the repository, you were potentially saving
to the same place as someone else. Just when you thought you were ready to share
your work, or request a code review, you would sometimes be prevented from doing
so if someone else had recently updated the same branch with their own work.

**Working with files in Subversion**

<img src="src\work-with-file-in-subversion.png" width="300px">

Git, on the other hand, is a distributed version control system. This means instead of
having one central place that everyone must use if they want to have their changes
recorded, each person works independently from the centralized code hosting sys‐
tem, and is responsible for making commits to his or her local copy of the repository.
This means changes from other developers are never forced into your work; instead,
it is your decision of when to incorporate outside work, and when to share your own

Every time you sit down to work with Git, you are sort of working in a centralized
fashion as far as your computer is concerned; your repository of changes is entirely
self-contained on your local machine. You do some work, and
then save that work to your local repository. Then, when you’re ready to share your
work with others, you make a connection to a remote repository and push your copy
of a specific branch to it.

**Working with files in Git**

<img src="src\work-with-git.png" width="300px">
