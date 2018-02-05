# Part 0: Introduction
Programming and automation are great tools for any IT or security engineer (or anyone wanting to finish their tasks automagically!). They allow you to build new tools or to combine already existing tools. These tools can improve and speed up already existing IT and security tasks.

The goal for this documentation is to help introduce people who are interested in learning more about programming and automation. I’m not looking to teach someone how to be a professional developer, but looking to help encourage and grow new hackers, tinkerers, and builders. I’m looking to provide the tools and direction to inspire curiosity and passion for programming. Remember there's never only one way to solve a problem. I'll work to provide you with the tools to solve the problems you'll encounter. 

Most importantly, stay focused on continued learning. Keeping your skills sharp by programming frequently and always looking for new things to automate. Don't get discouraged when something doesn't work perfectly, coming back to a project later may expose a new way to solve a problem.

This document is only the start. After reading this, we'll go step by step solving some problems and providing examples along the way. Every step will be a building block to help you start solving your own problems with code.

# Part 0: Getting Started
## How to pick a programming language - Right tool for the job
Rather than suggest a language or two without providing any reasoning, I'd like to give a few ways to determine what the right language for the job might be.

* Existing knowledge and urgency - Depending on the urgency of the task your trying to complete, sometimes it might be best to use a language you're already familiar with.
* Community Support - Some projects or communities have a tendency to lean towards a specific languages. For example, many of the infosec community projects use Python or Ruby. IT and DevOps have started to use a lot of Go. You're not required to use the same language as your peers, but it might make the process easier.
* System Support - Another important thing to consider is whether the systems you’ll be running the code on supports the language you’re using. For example, many Linux systems support both Python2.7 and Python3 but will default to a particular version. Other languages will compile to binaries that will execute on any system, regardless of current software installed.
* There are other details to take into consideration, but at this point, it's not worth adding the complexity. In the following examples, we'll discuss in detail why a language choice makes sense.

## Programming development environment configuration - Python and Go
Python and Go are the two languages I enjoy the most, so I’ll be using these in my examples moving forward. Below are links to environment setup guides for each of these languages.

* [Python Development Environment Setup - Ubuntu](python_setup_ubuntu.md)

* [Go Development Environment Setup - Ubuntu](go_setup_ubuntu.md)

## Workflow with Version Control - Git
Using version control is one of the best ways to organize and manage your code. It also allows you to collaborate with others easily and effectively.

### Example Git Workflow
* Start a new project, with a new git repo. Push the new repo to your remote repository (github, gitlab, etc).
* Make some changes to the code, create a new commit along with a detailed commit message, push the commit to your remote repository.
* Create a new branch for some experimental changes, determine whether they’re successful or not, and merge the branch or delete it.
* After a few more merges into the master repo, you realize a change has created a terrible bug, so you git reset back to a known working commit and push to your remote repository. This reverts everything back to the target commit.
* Add a few additional people to this workflow with everyone contributing and using branches properly, and you have a great team workflow!

### Collaboration
Using Git along with a remote upload site like Github, Gitlab, or an internal version control system makes it much easier to collaborate with others on your project. When working on the same project with others, Git provides the tools (pull, push, merge, pull requests, etc) to make sure that no one clobbers someone else's work (it will at least provide warnings of this happening - merge conflicts). It also provides repository branches so that features work can be done on individual branches and merged back into a master branch once they've been completed.

Even for simple scripts, using Git for collaboration is invaluable. I suggest using it for any code or documentation you care about.

### Version control and source management
Similar to the branching example given above, Git provides you with the tools to quickly iterate and test changes to your code without running the risk of “changing too much” or “having to hold ctrl-z for the next 30 minutes to revert everything”. Create an experimental branch for all your changes, if it works, merge it back into your master branch. If it doesn’t work, just delete the branch! You can also revert changes that have been pushed to your repository with more complex git commands. Every single git commit is tracked individually, so treat commits like saving your code. Every commit message should have a detailed (but brief) summary of what you’ve done. The more often you commit, the more granular your change management will be.

### Historical context
Each commit in your Git repository holds historical context. It tells you about what changes were made as well as who made them. This allows you to properly track changes to your code base.

### Backup (ish)
When you push your code to a remote repo, it serves as a remote backup. Just with any other backup solution, always have multiple backup destinations other than just your remote repo. Also consider if the remote repository you’re using is hosted by a 3rd party and what their ToCs and SLAs might be.

### Other External Resources
Linked below are some great resources for getting started with Git. Rather than duplicating information here, I’d suggest reading these write ups for a good place to get started.

* [Git - The simple guide](http://rogerdudler.github.io/git-guide/)

* [Github tutorial for beginners](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)

* [Github Hello World](https://guides.github.com/activities/hello-world/)

* [Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

## Examples of Automation and Programming
Below are some projects and ideas of automation and programming. This should help brainstorm some ideas around what you could work on next.

* Your team has a shell script that everyone is interested in the output of, so you could write a program that pushes this data to a Slack webhook.
* Your IDS stack needs to update its rules once a day from various internal and external sources, so you could write a program to collect these rules and install them on your IDS sensors.
* You’d like to have all of your Zabbix alerts go to Slack, but Zabbix doesn’t have the functionality built-in. You could write a program that runs via Zabbix’s script execution that sends those alerts to Slack.
* Your group of friends like to share Youtube videos on Discord, and you’d like to collect all those videos in one playlist. You could write a program that uses the Discord and Youtube APIs to build this playlist.
* You’d like to scrape a website’s information and store it in a database for further analysis. You could write a program that parses the website’s HTML and sends it to a database.
