# Branching Strategies

In version control, a branch is a way to separate parallel thinking about how a piece of code might evolve. A branch always begins from a specific point in the code base.

The branching strategy that you use depends on your release management process. Branches allow you to change the files that are visible in the working directory for your project, and only one branch can be active at a time. Most branching strategies separate the work in your project by coarse ideas. An idea could be the version of your software for example, version 1, version 2, version 3. And spawning from those software versions you might have ideas that are in progress. These ideas are
generally separated into branches according to the name of the feature they represent. They might be a bug fix or a new feature, but they also represent whole ideas on a smaller scale.

## Mainline Branch Development

The easiest branching strategy to understand is the mainline branch method. In this strategy, there are fewer branches to work with. The developers are constantly committing their work into a single, central branch which is always in a deployment ready state. In other words, the main branch for the project should only contain tested work, and should never be broken.

As a team of one, I often work on tiny side projects that only just barely warrant having version control, such as writing an article for a magazine. In these cases, I commit all of my work in the default branch (named master by Git). If I have two unrelated ideas that I am working on, I might be lazy and choose to commit everything, or I might stash some of the work to save it for later. For these simple projects, it doesn’t warrant separating thinking into different branches in order to work efficiently.

**Mainline branch development: storing all commits to a single branch**

![img](./src/mainline-branch-development-storing-all-commits-to-a-single%20branch.png)

As the project matures, there will be more and more to think about, and it will get harder to keep track of ideas. I’ll start adding new branches as I think about new directions I might want to take my project in, but that aren’t as fully thought out as some of the other pieces I’m working on. Perhaps I’ll even expand my team and have
a reviewer or two with their own, independent branches. As the project grows in complexity (and team members), so will the number of branches. But they won’t all be active all the time.

**Mainline development with branching: branches separate the work being contributed by multiple people**

![](./src/mainline-development-with-branching-branches-separate-the-work-being.png)

Perhaps it makes sense for your team to integrate their work into a central branch regularly, but only deploy work occasionally. As soon as you start collecting your work, you need to make a distinction between what you have locally, and what is being used on your production server. If all code is ready for deployment, it shouldn’t be too big of a deal to add a little fix and roll everything out. But what if you have changes committed in your repository that are only mostly finished? This is where we start to move away from a purely continuous deployment strategy, and toward multiple branches in a scheduled deployment strategy.

***There are several advantages to using a branching strategy that encourages regular integration of your work***

- There aren’t very many branches across the entire project. This results in less confusion about where a change disappeared into.
- Commits that are being made into the code base are relatively small. If there is a problem, it should be relatively quick to undo the mistake.
- There are fewer emergency fixes, because any code that is saved into the main branch is ready to be deployed. Deployments can often be stressful for developers as they hold their breath while code goes live in production and wait to hear back from the code’s users. With tiny frequent updates, this procedure becomes practiced, and finally automated to the point where it should be almost invisible to
the end user.

***There are disadvantages to using this strategy as well***
- The assumption is that the main branch contains deployment-ready code. If your team doesn’t have a testing infrastructure, it can be risky to assume that new code won’t break anything, especially as the project becomes more complex over time.
- The notion of a deployment is more appropriate for code that is automatically loaded onto a user’s device (for example, a website). It is less appropriate for software that must be downloaded and installed. While updates that fix problems are welcomed, even I would get annoyed if I had to download and reinstall an application on my phone on a daily basis.
- One of the ways developers can verify code on production is to hide the feature behind a flag or a flipper. Facebook, Flickr, and Etsy are all rumored to use this technique. The potential risk here is that code can be abandoned behind the flags,
resulting in a large technical debt for code that isn’t removed because it is hidden.
