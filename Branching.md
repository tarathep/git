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

## Branch-Per-Feature Deployment

To overcome some of the limitations of the single branch strategy just described, you can introduce two additional types of branches: feature branches and integration branches. Technically, they aren’t different kinds of branches; it’s just the convention of what type of work is committed to the branch that differs.

In the branch-per-feature deployment strategy, all new work is done in a feature branch, which is as small as it can be to contain a whole idea. These branches are kept up to date with the work being done by other developers via an integration branch. When it is time to release software, the build master can selectively choose which features to include in the build and create a new integration branch for deployment. A build does not necessarily include all of the work completed since the last build.

**Branch-per-feature: feature branches are kept up to date via an integration branch**

![](./src/branch-per-feature-feature-branches-are-kept-up-to-date-via-an-integration.png)

By adding feature branches and an integration branch, you can continue to have deployment-ready code, but also a pause before deploying the code. The most popular description of this model is by [Adam Dymitruk.](http://dymitruk.com/blog/2012/02/05/branch-per-feature) A slightly earlier description of this model was by Scott Chacon and is named the [GitHub Flow](http://scottchacon.com/2011/08/31/github-flow.html). With a few minor
updates, this process is still used by GitHub today.

In the GitHub Flow branching model, anything in the master branch is deployable. When working on new code, GitHub Flow has the developers create a descriptively named feature branch and commit their work regularly to this branch. This branch is kept up to date with master and is regularly pushed to a branch on the shared repository, allowing others to see which features are actively being worked on. When developers think their work is complete, or when they need help with their work, they will
issue a pull request to the master branch. In the ticketing system, there will then be a conversation about the work that is being proposed.

Up to this point, the GitHub Flow is virtually the same as the Dymitruk model. Where they differ is in how the deployment happens. In the Dymitruk model, a build is made by selecting which features are ready to be incorporated. In the GitHub Flow model, once a pull request is accepted, the work is immediately ready to be deployed from its feature branch. This makes the strategy closer to mainline development. Originally, GitHub merged its feature branches into the master branch and then deployed the master branch. Nowadays, the feature branch is deployed and if there are no errors, it is merged into master as shown in Figure 3-4. This means that if there are problems with a feature branch, master can immediately be redeployed because it is proven to be in a working state.

**GitHub Flow: feature branches are deployed after a review and then merged into master**

![](./src/githubflow-feature-branches-are-deployed-after-a-review-and-then-merged.png)

***There are several advantages to using a branch-per-feature deployment strategy:***

- Much like mainline development, the focus is on rapid deployment of code.
- Unlike the mainline development, there is an optional build step. When the build step is used, there is the option to select which features should be incorporated into the master branch for deployment.

***There are disadvantages to using a branch-per-feature deployment branching strategy as well:***

- If code is kept on a feature branch, but it is not immediately rolled into master, there is an extra maintenance requirement for developers who need to keep their features up to date while waiting to be rolled into the deployed branch.
- The semantic naming of the branches helps those who are familiar with the system, but it also represents an insider language that can make onboarding more difficult if there are a lot of open features.
- There is now a housekeeping requirement for developers to remove old branches as they are rolled into master. This isn’t a large burden, but it is more than would be required from working out of a single master branch.

The branch-per-feature strategy offers a nice middle ground between mainline development and scheduled deployment. In some ways, scheduled deployment extends the branch-per-feature strategy, but with specific naming conventions.

