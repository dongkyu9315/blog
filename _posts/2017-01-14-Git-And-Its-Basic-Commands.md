---
title: "GIT and its Basic Commands"
layout: post
description: "Basic description of git and its basic commands"
categories: [Tech, Version Control System]
tags: [git, commands]
comments: true
---

> "Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency"
> <p style="text-align: right;">- git-scm.com</p>

#### In short, git is a free version control system. We can use it for any projects or even a small word document.

#### First, you might need to install git to use it. Open up your Terminal (or Command line prompt, if you are using Windows) and enter git. If you see something like below, git is installed. If not, you need to install git from [git-scm.com](https://www.git-scm.com "Git's Homepage").

![git successful installation]({{ site.baseurl }}/assets/img/git-and-its-basic-commands/git-successful-installation.jpeg)

<br />

#### Now, you can make a directory into a git repository by using "git init" command.

```shell
git init
```

<br />

#### To see the status of this repository, you can check it with "git status" command.

```shell
git status
```

<br />

#### After you make a new file or edit an existing file, "git status" command will show which files have been created or edited.

![git status untracted]({{ site.baseurl }}/assets/img/git-and-its-basic-commands/git-status-untracted.jpeg)

<br />

#### Then you can add a single file, multiple files, or all files by using "git add" command.

##### To add a single file, named "helloworld.txt".
```shell
git add helloworld.txt
```

##### To add multiple files, named "test1.txt" and "test2.txt".
```shell
git add test1.txt test2.txt
```

##### To add all new and edited files
```shell
git add .
```

##### Of course, you can unstage a file, named "test1.txt", by using "git rm" command.
```shell
git rm --cached test1.txt
```

<br />

#### After you add all files you want to tract, you are now ready to commit with "git commit" command. As you can see below, you type your own commit message between double quotes with "-m".

![git status tracted]({{ site.baseurl }}/assets/img/git-and-its-basic-commands/git-status-tracted.jpeg)

![git commit]({{ site.baseurl }}/assets/img/git-and-its-basic-commands/git-commit.jpeg)

<br />

#### You can see all the previous commits on the git repository by using "git log" command.

![git log]({{ site.baseurl }}/assets/img/git-and-its-basic-commands/git-log.jpeg)

<br />

#### Until now, we have been working with local git repository. In order to upload the changes, we need to push the changes by using "git push" command.

```shell
git push
```

<br />

#### If someone else changed the code upstream after you pushed, you need to pull from upstream to your local repository to get the latest version by using "git pull" command.

```shell
git pull
```

<br />

#### To summarize the workflow of git when working with a team, you do the following.

0. __git pull__ to get the latest version
0. make changes
0. __git add --filename--__ or __git add .__ to stage untracted files
0. __git commit -m "--commit message--"__ to commit changes
0. __git pull__ to see if someone else pushed after my previous pull
0. fix conflicts if any and do step 3, 4, and 5 again
0. __git push__

***

#### Reference  
- [Git's Homepage](https://www.git-scm.com "Git's Homepage")

***
