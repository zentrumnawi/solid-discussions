# s.o.l.i.d. Git Workflow

This short guide introduces the standard workflow we adapted during our work at the s.o.l.i.d. Frontend. The basic idea may also apply to the backend development process.

Please keep in mind the rules defined in the [s.o.l.i.d. Programming Rules](solid-coding-rules.md).

**This instruction is no replacement for reading into the Git collaboration concept!** 

This is just a reminder to avoid merge conflicts and confusion.

#### Prerequisites

1. GitHub needs to be set up correctly on your machine for this to work, e.g. a connection to your GitHub Account should be established, preferably with [SSH authentication](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).
2. You should already have cloned the repository into a folder on your local machine. 
3. You should have installed the `yarn package manager` (at least for Frontend development; refer to the [Frontend setup manual](solid-frontend_de.md)).
4. You should have an IDE installed - if you have no other preferences, we recommend VSCode.
5. You should be able to open and use a terminal.

These are just the basic instructions - it is less likely to run into problems if you follow them closely. Git is far more powerful, of course, and you can do a lot more with this tool. Feel free to enhance this manual.

The standard flow will be described by git console commands. You can, of course, use your IDE's (e.g. VSCode) Git tools which is at least recommended for commiting. In practice, you may end up using both in parallel - which is no problem since the IDE buttons just invoke the console commands. But using the commandline is sometimes more transparent.

## How to Git in s.o.l.i.d.

If you are going to work on a new task, follow these steps:

#### 1. Create a new branch from `dev`

Switch to the `dev` branch and _pull_ the actual version from the server to ensure that your local `dev` branch is at the same version as on the server:

​	```git checkout dev```

​	```git pull```

Now, create a new branch with an adequate name (the flag `-b` will create a new branch):

​	```git checkout -b <new-branch>```

Start coding! 

### 2. Commit your changed files

As soon as you have finished some smaller sub task and saved your files, _commit_ your changes.

It is helpful to use the Git UI of VSCode, which makes things rather comfortable - especially if you want to put your changed files in different commits.

You can also commit all your changes by using

​	```git commit -a ```

This command will take all changed files, add them to the index and commit them in one go. You will be asked to type a commit message - try to be short and precise. You may use  the [Git automation keywords](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword) - but keep in mind that it should only be used if an issue is really fixed and can be closed.

### 3. Push your changes to the server

As soon as you have made enough changes to show them to others (this should be as early as possible), push them to the server:

​	`git push`

If your new branch is yet unknown to the server it will tell you to use `git push --set-upstream origin <branch name>`. Follow these instructions - it's sufficient to remember `git push`.

### 4. Create a Pull Request on GitHub

If you want others to take a look at your code (yes, you want! See rule [No. 2](solid-coding-rules.md)), go to GitHub and create a pull request (**PR**). 

Newly pushed branches show up on the code tab and the button `create pull request` should be right there, so it's very simple.

Write a PR message and explain what this branch is for. Assign a _reviewer_.

Continue working and pushing - all new commits will be integrated in the pull request. 

GitHub Actions will even start to test and/or build the project after each push. If something fails, you will be notified and can take action. If the reviewer has comments or suggests changes, apply the changes, commit and push again.

If you want to work on another branch, **make sure all your changes are committed** and follow the above instructions to start to a new branch or switch to an existing one with `git checkout <another-branch>`. If you do not want to commit (why wouldn't you?), you may [stash](https://www.git-scm.com/docs/git-stash) your changes.

### 5. Collaborating

If you are collaborating with colleagues (co-authoring) on a PR, others may push commits to the same branch, resulting in an `origin` branch which is never than your local branch. 

This is going to result in merge conflicts if you try to push your next commit. You will then have to `pull` the branch and merge it into your local branch. Usually, this is a guided process and works fine, but sometimes it can get a little messy or confusing. 

So remember to `git pull` **before** you continue working if someone else has been pushing changes.

Doing so may save you some trouble, although the procedure is perfectly git standard and considered normal.

### 6. Adjust the version

#### s.o.l.i.d. Frontend

s.o.l.i.d. adheres (however loosely) to the [SemVer](https://semver.org/) concept to display and maintain version numbers. The version **must** be adjusted manually with every merge to `dev`. Since the Frontend does not expose an API where others depend on, it's not that critical. It is more of a helper for our internal accounting.

The version is in the main repository's `package.json` (Line 3), please follow the `Major.minor.patch_tag` to the best of your knowledge.
- `patch_tag` should be bumped upon smaller changes like typos, corrections of existing components etc.
- `minor` version should be increased upon new features, medium changes, dependcy or framework upgrades
- `major` version should be increased upon "breaking" changes, e.g. changes in connection with endpoints, major strategy changes etc.

I in doubt, ask a colleague.

~Since the s.o.l.i.d. Frontend is a monorepo but the apps are released and deployed independently, there is a difference between the s.o.l.i.d. version (i.e. the actual status of the repository's `dev` branch) and an app's release version.~ 

### 7. Merge the pull request

If your task is finished, versioned and the reviewer approved the PR, you can merge the new branch to the `dev` branch. It is recommended to do this on GitHub and not locally (although it is possible).

Merging on GitHub has the advantage that it is a guided, transparent and comprehensive process and the `dev` branch on the server will always be the most actual.

Merging locally will result in a local `dev` branch which is newer than on the server. This interferes with the "one source of truth"-idea since the actual source of truth is not accessible to everybody. So you should rather do it on GitHub and everything will be fine.

**Important:** Remember to pull your `dev` branch after the merge to be up to date (see step 1). New branches should always be based on the most recent `dev` branch.

The merged branch will be deleted on the server - but not locally, so be careful not to work in your old branch (you may delete it also locally using `git branch -d <branch-name>`). If you need to make changes, it is recommended to create a new branch (i.e. repeat the process starting with step 1).

### 8. Push to staging

Once a new patch is merged to the dev branch, it will be automatically deployed on the staging system by the GitHub Actions and it will be visible to the public (or rather to those who know where to look).


