# What is Git?
This is git as defined on the [official git website](https://git-scm.com/)
> Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

# Make sure git is installed correctly
If you have github desktop installed, you might not have git installed as a separate package so it is important to make sure git is correctly installed. This a can be done using the following command
```
git --version
```
If the command outputs a version, then you're all set. but if you get nothing or an error then you have to install git properly.

# Layout of Git Repositories
![](git_areas.avif)

# Setup Git

# Start Working With Git

## Initialize a Git Repository
At first you have a folder or "Directory" that you want to turn into a local git repository. To do so you use
```
git init
```
This initializes a git repo, in other words it tells git to start paying attention to the changes that happens inside this directory.

## Adding Files
Normally you don't want git to track all the files in your working directory, because some files might contain sensitive information such as passwords and other files might not be relevant to your projects. To see the status of your repo you can use the command
```
git status
```
This command shows you which files are tracked, which are not, which are tracked but modified since your last commit, and so on.

To track a file means to add it to the staging area, and this is done using
```
git add myFile.txt
```
Alternatively, you can add all files to the staging area by simply doing `git add .`

## Committing Changes
A commit takes a snapshot of everything in the staging area, so any changes made after the `git add` command will not be part of this commit

```
git commit -m "put commit message here" -m "put commit description here"
```





# References
1. [Git Notes For Professionals](https://books.goalkicker.com/GitBook/)

1. [Git and GitHub for Beginners - Crash Course](https://youtu.be/RGOj5yH7evk)
