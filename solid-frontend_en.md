# s.o.l.i.d.-Frontend

This tutorial details the necessary steps to run the s.o.l.i.d.-frontend locally for development.

There are a few programs and tools to install - it is recommended to read through this tutorial once before starting the step-by-step installation process.

1. Git: https://git-scm.com/downloads | https://gitforwindows.org/
2. Node.js: https://nodejs.org/de/download/
3. Yarn (classic): https://classic.yarnpkg.com/en/docs/install
4. VSCode: https://code.visualstudio.com/Download (Vorschlag)

Additionally, a [GitHub](https://github.com)-account is required in order to upload your code to the project server. 

## Git - software versioning

*Git* is one of the most renowned versioning tools. Used correctly, it ensures that past versions (of files) can always be restored and progress can be processed separately in different development branches and by different people. In addition, it is always transparent which change was made when and by whom.

Versioning really works at _directory_ and _file_ level of the operating system. This means that if you switch from one version to the next or to another development branch, the file structure effectively changes. If a file is deleted in a branch, it reappears in the directory as soon as you switch to another branch in which the file still exists.

Changes to the file structure (e.g. changes to files) must be actively versioned in a so-called `commit`. By *committing*, a change is transferred to Git and saved with a version number in the *git history*.
Git also establishes the connection with the development platform *GitHub*, where our (opensource) code is stored and in which all versions are recorded. There is also a [guide](solid-git-workflow.md) on how to work correctly with Git in our projects.

Git is a command line tool in itself, but there are also user interfaces and the usual Git functions are well integrated into most development environments (including VSCode).

Git must be installed on the respective operating system. For Windows-Users we recommend *Git for Windows*: https://gitforwindows.org/

## Node.js - Javascript Runtime Environment
Node.js must be installed so that Javascript can be executed and processed on the computer: https://nodejs.org/de/download/

## Yarn - Package Manager

Modern software is heavily based on many individual software packages that perform various subtasks and special functions, so that only the programming code that is specific to the software in question really needs to be rewritten.

All *packages* used in s.o.l.i.d. are open source and are managed by a *package manager*. We use the package manager *yarn*.

The package manager installs and updates all dependencies and programme libraries required by our framework.

Yarn must be downloaded and installed for the respective operating system: https://classic.yarnpkg.com/en/docs/install

## Visual Studio Code - Work environment

In theory, only text files need to be changed for programming - but a development environment (*IDE - Integrated development environment*) supports programming with numerous search and validation functions and makes the work much easier, not least due to the good integration with Git.

In our project, we use the *VSCode* development environment almost exclusively, as it is free and a powerful tool. Other development environments can of course be used according to personal preference.

A development environment (*IDE - Integrated development environment*) supports programming with numerous search and validation functions: https://code.visualstudio.com/Download

## GitHub-Account

GitHub is an online platform for software development in teams and is closely interlinked with the Git versioning tool. The software representation of a project is called a _repository_.

A repository (also known as a ‘repo’ for short) contains all files belonging to the project as well as the complete development history. 

Various functions are also provided by the online platform, such as issue management for upcoming tasks and various project planning tools as well as workflows for testing and preparing code changes.

http://github.com &rarr; Sign up

https://docs.github.com/en/get-started/quickstart/set-up-git

see in particular steps 2 and 3 here. Authentication via SSH is recommended - this means that it is not necessary to enter a password every time you interact with GitHub, but a key pair must be generated; this is also explained in the following article: https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh

## Getting started

A folder into which the repository is to be cloned must be created on the local hard drive. Note: The packages require a relatively large amount of space.

In principle, the following steps can be carried out from the command line (*Git Bash* or the Windows command prompt / CMD). However, it is advisable to start the terminal from VSCode:

3. Start VSCode, open the created (empty) folder and call a terminal. The s.o.l.i.d. frontend repository is cloned into the current folder using the command `git clone https://github.com/zentrumnawi/solid-frontend `.
4. The required packages are installed with the command `yarn`; this takes a while.
5. After the installation is complete, the frontend can be started locally: `npx run <app-name>:serve`. Once the start process is complete, a URL (`http://localhost:4200`) is displayed, which opens a browser window in which the app is displayed and can be viewed. The data is loaded from the server interfaces of the _staging_ system.
6 **Important: Before the code is changed, a new branch must be created in the repository!** This ensures that all changes are separate from the working status quo. There is a separate [instruction](solid-git-workflow.md) for the use of Git in the s.o.l.i.d. project.

In principle, you can now ‘develop’. After each saved change in the code, the app is reloaded
