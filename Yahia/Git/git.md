# What is Git?
This is git as defined on the [official git website](https://git-scm.com/)
> Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

# Make sure git is installed correctly
If you have github desktop installed, you might not have git installed as a separate package so it is important to make sure git is correctly installed. This can be done using the following command
```
git --version
```
If the command outputs a version, then you're all set. but if you get nothing or an error then you have to install git properly. On windows make sure that "git bash" is checked in the installer.

# Layout of Git Repositories
![](git_areas.avif)

# Setup Git
To make commits, git needs to know who you are in order to associate each commit with its author. To identify yourself _locally_ use the `git config` command.
```
git config user.name "Your Name"
git config user.email mail@example.com
```
This will identify you in this repository only, if you want this name and email to be your identification on all local repositories, you should use the `--global` flag as such
```
git config --global user.name "Your Name"
git config --global user.email mail@example.com
```

## Setup ssh keys
If you intend to use remote repositories it is generally recommended to authenticate using ssh. So here we setup ssh and generate ssh keys needed for authentication.

The commands used in this section will work fine for most unix-like operating systems but for windows you must enter these commands in git bash instead of your usual terminal.

1. See if you already have any ssh keys
```
ls -la 
```
If you see any files that have the same name but one of them ends in ".pub" then you already have ssh keys that are generated, you can use them for git, but it is generally bad practice to reuse ssh keys.

2. To generate new ssh keys use the command
```
ssh-keygen -C "YourEmail@example.com"
```

3. To make sure that the SSH agent is running, restart it.
```
eval "$(ssh-agent -s)"
```

4. Add your _private_ SSH key to the ssh-agent.
```
ssh-add ~/.ssh/your_private_key
```

5. Add your _public_ ssh key to your remote git provider (Github for example). This step depends on your provider but you can generally find an option for "ssh keys" in your profile's settings.

# Start Working With Git
Here we discuss the various git commands.

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

## Setting up a Remote Repository
To upload your work to a remote repository (like github for example) you must first tell git where to push your work to.
```
git remote add remote_Name remote_URL
```
Notice that this means that you can assign more than one remote repository to the same local repository. Conventionally, the remote name is set to `origin` but this is not obligatory.

When pushing your work for the first time you should set the remote repository as "upstream"
```
git push -u origin branch_name
```
The `branch_name` is usually main if you are working with github.

## Cloning a Repository
This one is fairly simple
```
git clone remote_URL
```
This command will clone the remote repository into the current directory, creating a new subdirectory whose name is the name of the repository you are cloning.

## Browsing the History
To see all previous commits and their data use
```
git log
```























# References
1. [Git Notes For Professionals](https://books.goalkicker.com/GitBook/)

1. [Git and GitHub for Beginners - Crash Course](https://youtu.be/RGOj5yH7evk)

1. [Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
