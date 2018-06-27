# Version Control with Git
The guide will provide an overview of git-based code sharing resources. The goal is to introduce first-timers with the general flow of version control and to also encourage clean coding techniques.

## What is Git?
Wikipedia definition: Git is a version control system for tracking changes in computer files and coordinating work on those files among multiple people. It is primarily used for source code management in software development, but it can be used to keep track of changes in any set of files.

![alt text](https://imgs.xkcd.com/comics/git.png)

### Getting set-up
#### Installation
To install git on your machine, please follow the steps in this [online guide](https://gist.github.com/derhuerst/1b15ff4652a867391f03).

To use git, you will need to type commands through a terminal. There are many great [GUI clients](https://git-scm.com/download/gui/windows) for version control. However, for this guide, I will focus on command lines.

If you are working on a Linux server, chances are it's already installed. Type "which git" to see if it's available.

#### Creating an account with an online repository
Online repositories make to easier to browse, share, and update code. It also serves as a backup for your important coding projects, in case something happens to your computer.

There are two major online repositories:
* [Github](https://github.com/)
* [Bitbucket](https://bitbucket.org/)

The main differences between them are that Github, while more popular, forces you to only have public repositories. For private repositories, you have to be a paid member. Bitbucket permits private repositories for free, but only allows a maximum of five users on a project.

# Configuring
Go ahead and set-up your name/email on the server, so that any changes can be linked to you:
```
git config --global user.name "Enter Your Name"
git config --global user.email your.email@email.com
```
## Creating a new git project
Okay, lets say you have already started a project, made some progress, and want to save your work.

To initialize a repository, cd to your project and type:
```
git init
```
You need to specify which files are tracked. You can use the individual filenames, or \*.f95 to track changes to all files. So decide which files to include, and use the following command to add them:

```
git add [filename]
```
Now, we need to save them to the repository, so we use the following command (-a option means 'all' files, but you can also only commit one file by specifying the filename)

```
git commit -a
```

The default text editor will appear, prompting you to add a message regarding what has been changed in the code. We'll discuss this more in the "Style Guides" section.

That's it! You can now continue to make changes to the code, and when you're ready to save the current version of the project, use the 'commit' command.

## Basic git commands
Here's a good [cheat sheet](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0ahUKEwiU-7mWjerWAhVFAcAKHZ0cAmAQFggoMAA&url=https%3A%2F%2Fgitlab.com%2Fgitlab-com%2Fmarketing%2Fraw%2Fmaster%2Fdesign%2Fprint%2Fgit-cheatsheet%2Fprint-pdf%2Fgit-cheatsheet.pdf&usg=AOvVaw1bioXgbb6L3VKqf63innoY). Below is a visual summary of what each command does (Author: [Daniel Kinzler](https://commons.wikimedia.org/w/index.php?curid=25223536).

![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d8/Git_operations.svg/760px-Git_operations.svg.png)

### Managing your projects
To create a new online repository, go to your online git repository and click on the + button and select "Create new project." Fill in the name or make a short description. While the name can be changed later, it can break the paths to your repository, so take a moment to choose carefully.

Once you're done, you can add code from the server side by going to your project directory and typing the following commands in your shell (replace username and repository_name with your repository):
```
git remote add origin
... ssh path to your online repository ...
git commit -m "Initial commit"
git push -u origin master
```
If you did this right, you should see your code in the online repo. You can navigate through previous commits, older versions of the code, and share with other group members (which we'll talk about next).

## Style guides
1. Include a README file. I recommend using markdown and here is a [good template](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2). A readme file should include the following sections, where applicable:
    * Project title
    * Getting started
      * Pre-requisites
      * Installation process
      * Required libraries
    * Usage
      * How to use or run the code
    * Author(s)
    * Resources or references
2. Follow your organization's coding standards, or develop your own.
  * e.g. NOAA/STAR [coding standards](http://projects.osd.noaa.gov/SPSRB/standards_software_coding.htm).
3. Clean and clear code >> commenting (not that you shouldn't comment)
4. Leave the code cleaner than you started
5. Include detailed description of commits

![alt text](https://imgs.xkcd.com/comics/git_commit.png)

Great commit messages follows the following rules:
1. Limit the subject line to 50 characters.
2. Capitalize the subject line and do not end the subject line with a period
3. Use the imperative mood in the subject line ("Applying this commit will ..."). Fix, add, or change are good starting words.
4. Separate subject from body with a blank line.
5. Manually wrap the body at about 72 characters.
6. Use the body to explain what and why, not how (the code is the "how").

Using formatting such as bulleted lists are okay.

This is a lot to remember every time. I'm a fan of templates. You can edit the default git message to say:

```
# Subject: "Applying this commit will ..." (<50 characters)

# Describe what the change to the code is and why the change is made
```
You can save this or another default format creating a file with the template in ~/.gitmessage and then by editing  the commit.template to point to it. Run the following command:
```
git config --global commit.template ~/.gitmessage
```

Each time you commit, the above template will pop-up. The hashtags are treated at comments and will not show up in the final version of the commit.

## Resources
Tutorials
* [Git Learning Lab](https://lab.github.com/)
* [Code Academy](https://www.codecademy.com/learn/learn-git) some lessons are behind a paywall
* [Cheat sheet](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0ahUKEwiU-7mWjerWAhVFAcAKHZ0cAmAQFggoMAA&url=https%3A%2F%2Fgitlab.com%2Fgitlab-com%2Fmarketing%2Fraw%2Fmaster%2Fdesign%2Fprint%2Fgit-cheatsheet%2Fprint-pdf%2Fgit-cheatsheet.pdf&usg=AOvVaw1bioXgbb6L3VKqf63innoY) good list of main commands

[Online repository comparison](https://www.upguard.com/articles/github-vs-bitbucket)

GUIs/other
* [Comprehensive list](https://git-scm.com/download/gui/windows) for mac, linux, and windows
* [Github desktop](https://desktop.github.com/) simple and easy
* [Tig](https://jonas.github.io/tig/) repository browser

## Author
[Rebekah Esmaili](mailto: bekah@umd.edu)
