# Git

Git Fundamental 

<div align="center"><img src="hero.svg" width=100%></div>

By far, the most widely used modern version control system in the world today is Git.

Git is a mature, actively maintained open source project originally developed in 2005 by Linus Torvalds, the famous creator of the Linux operating system kernel.

A staggering number of software projects rely on Git for version control, including commercial projects as well as open source. Developers who have worked with Git are well represented in the pool of available software development talent and it works well on a wide range of operating systems and IDEs (Integrated Development Environments).

Having a distributed architecture, Git is an example of a DVCS (hence Distributed Version Control System).

Rather than have only one single place for the full version history of the software as is common in once-popular version control systems like CVS or Subversion (also known as SVN), in Git, every developer's working copy of the code is also a repository that can contain the full history of all changes.

In addition to being distributed, Git has been designed with performance, security and flexibility in mind.

https://git-scm.com

## Table of Contents

- What is GIT
- Access Models
- Branching Strategies
- Git Basic Command

<!-- 
# Access Models

If you have been using version control for a long time, you may remember systems like CVS or Subversion with a centralized repository. demonstrates how changes were made in Subversion’s centralized system. In this system, each time you wanted to save a snapshot of your work to the repository, you were potentially saving to the same place as someone else. Just when you thought you were ready to share your work, or request a code review, you would sometimes be prevented from doing so if someone else had recently updated the same branch with their own work.

**Working with files in Subversion**

<p align="center"><img src="src\work-with-file-in-subversion.png" width="300px">
</p>

Git, on the other hand, is a distributed version control system. This means instead of having one central place that everyone must use if they want to have their changes recorded, each person works independently from the centralized code hosting system, and is responsible for making commits to his or her local copy of the repository. This means changes from other developers are never forced into your work; instead, it is your decision of when to incorporate outside work, and when to share your own

Every time you sit down to work with Git, you are sort of working in a centralized fashion as far as your computer is concerned; your repository of changes is entirely self-contained on your local machine. You do some work, and then save that work to your local repository. Then, when you’re ready to share your work with others, you make a connection to a remote repository and push your copy of a specific branch to it.

**Working with files in Git**

<img src="src\work-with-git.png" width="300px">

Keeping your work entirely local would be very limiting! Instead, we make connections to other systems, and share our code through the remote repositories.

Git does not have the ability to control access—instead, it allows any developer full read/write access to the repository. At the most coarse level, you limit this control through login controls. I develop on my machine, to which you don’t have access, and therefore you cannot change my repository. As soon as we put the repository in a shared location, such as a centralized code hosting server, we need to agree on how we will govern our access to the repository.

Some Git hosting systems, such as Bitbucket, allow fine-grained, per-branch access
controls; however, most force you to limit control on a per-repository basis. In other words, you either are a committer for any branch on the repository, or you are limited to making your contributions through pull requests.

**The three most popular models**

- [Single Repository; Shared Maintenance](/AccessModel.md#shared-maintenance-model), wherein everyone on the team is considered a maintainer and is granted access to upload changes to the project repository.
- [Collocated Contributor Repositories](/AccessModel.md#collocated-contributor-repositories-model), wherein contributing developers create a remote copy of a project, and have their changes accepted by project maintainers.
- [Dispersed Contributor Repositories](/AccessModel.md#dispersed-contributor-model), wherein code is shared via a text-based patch file.

## Branching Strategies

In version control, a branch is a way to separate parallel thinking about how a piece of code might evolve. A branch always begins from a specific point in the code base.

The branching strategy that you use depends on your release management process. Branches allow you to change the files that are visible in the working directory for your project, and only one branch can be active at a time. Most branching strategies separate the work in your project by coarse ideas. An idea could be the version of your software for example, version 1, version 2, version 3. And spawning from those software versions you might have ideas that are in progress. These ideas are
generally separated into branches according to the name of the feature they represent. They might be a bug fix or a new feature, but they also represent whole ideas on a smaller scale.

- [Mainline development](./Branching.md#mainline-branch-development)
- [Branch-per-feature deployment](./Branching.md#branch-per-feature-deployment)
- [State branching](./Branching.md#state-branching)
- [Scheduled deployment](./Branching.md#scheduled-deployment)

 -->
