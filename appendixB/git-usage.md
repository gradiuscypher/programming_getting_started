# Git - Setup and Usage
A simple collection of git commands.

## Create your Git Repo on Github/Gitlab/etc
Since this step is tool-specific, I'll leave this as an exercise to the reader. Most web-based tools are simple enough to use. When creating a new repository, I suggest at least creating it with a README and a LICENSE file. This way, you don't forget to do it later and you can easily clone the repository afterwards.

Also, don't forget to setup SSH keys on your web-based git service, so that you can easily clone repositories in the future.

## Cloning the repository to your local machine
To clone a repository to work on it locally:

```
git clone REPOSITORY_URL
```

For example, to clone this repository via git (rather than HTTPS), you would issue this command:
```
git clone git@github.com:gradiuscypher/programming_getting_started.git
```

Note: you can only SSH clone repositories that you have permissions for. When you're met with an error message saying that you're unable to clone the repository, it's either because you don't have permissions, or you've not configured your SSH keys properly.

## Checking the status of your Git repo
On your local machine, once you've added/modified/removed files, you can check the status of the repository with the command:
```
git status
```

This will present to you which files have been modified in any way. From there, you can determine which files you'd like to add to later commit. You can use standard file operations like wildcards.

## Adding files to stage a commit
Before you can commit changes to a file, you have to stage them with this command:
```
git add [FILE OR DIRECTORY]
```

For example, if I modified this README, and I wanted to stage it for commit:
```
git add README.md
```

## Removing files from a repository
To fully remove a file from a repository, you have to use this command:
```
git rm [FILENAME]
```

This will remove the file from being tracked by the Git repository. If you didn't already `rm` the file, this command will prompt you, asking whether you want to cache the file (keep it locally on your machine without deleting it, but still remove it from the git repo).

## Staging a commit
Once you've got a set of changes together, you can now stage a commit to be pushed to your remote Git service (Github, Gitlab, etc):
```
git commit -m [DESCRIPTIVE, YET SHORT SUMMARY OF CHANGES]
```

## Pushing to Remote
Once you've created a new commit, you can push it to the remote server with this command:
```
git push
```

## Creating a new Branch
Branching is a useful feature of Git if you'd like to make some changes to your code without potentially breaking your code and having to manually revert things. For example, you might want to play around with a different library, but you don't want to harm your working `master` branch. You could create a new branch with this command, where you can play with all of your changes:

```
git branch [NEW BRANCH NAME]
git checkout [NEW BRANCH NAME]
```

Important note: Please don't forget to checkout the branch after creating it.
