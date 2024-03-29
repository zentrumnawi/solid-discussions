# s.o.l.i.d. Coding Rules 

This guideline is meant for *every* programming task, no matter if it is a new release, a hotfix, a ptach, a new feature or just some experiment.

### Rule No.1: NEVER code on the `dev` branch!

The `develop` or `dev` branch is the working basis of our staging systems and acts as **a source of truth** for all developers. 

If you begin working on a new task, *always* start from `dev` and create a new branch (see [Git workflow](solid-git-workflow.md)). 
Name it carefully and comprehensively: The name should contain information about what will be worked on and the branch should be named with your initials, e.g. `bb/component-fix` or `bb/audio-feature`. 

As a rule, all programming tasks within a branch should be independent from other programming endeavours. Sometimes it makes sense to collect smaller tasks in one branch or to fix a few small issues in the next feature branch.

It goes without saying that the `master` branch is also **taboo**.

The only branch that will _ever_ be merged into `master` is `dev`!

### Rule No. 2: Transparency is key!

Commit often and use short but comprehensive commit messages. Avoid huge commits. You may use [GitHub's automated fix/close syntax](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword)

As a rule of thumb: A commit should encompass one self-contained sub task. E.g. if you change a variable name and alter three files - those three files should be in the commit. 

Even if you work on several independent things in parallel, it may be a good idea to commit them separately: An independent Reviewer should be able to easily understand what you did.

As soon as you have made some progress on your task and commited some new code, create a **Pull Request** and assign a **Reviewer** on GitHub, *even if the task is not yet finished*. You can continue pushing and the reviewer can comment, ask questions and hint at solutions.

You do not need to push every single commit, though. But if you have something completed that works and/or can be shown, push it. It is good practice to push your code at the end of your workday.

It makes sense to commit half-automated tasks (like formatting code) separately.

### Rule No. 3:  Communicate!

Please do communicate proactively with your colleagues or supervisors. 

A supervisor will be happy to know you are still alive and working on the project. Try to avoid the situation that you are being asked what you are doing (outside of meetings) - be sure not to find yourself in a defensive position.

It is no problem if you have to cancel a meeting or face any issues with your work or get behind schedule, we are all human. But it becomes a problem if nobody knows, so please be transparent. See rule No. 2.

### Rule No. 4: Ask questions!

Learning new things and figuring out ways to solve problems - oftentimes on your own - is part of your job. But do not wait too long before you ask questions.

It is a good feeling if you finally cracked a problem by yourself - but it is a bad feeling if you find yourself behind schedule after experimenting for days without any real progress and nobody knows about it. See rules No. 2 and 3.
