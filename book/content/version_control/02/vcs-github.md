## Using GitHub for effective collaboration

As research becomes increasingly collaborative and multiple people work on the same project, it becomes difficult to keep track of changes made by others if not done systematically.
Moreover, it is time-consuming to manually incorporate the work of different participants in a project, even when all of their changes are compatible.
Hosting the project on an online distributed version control system is beneficial to make collaborations open and effective.

**GitHub is online web interface**, it’s designed to share your work, and allow others to create an independent copy of your work to test, modify, remix and reuse it without impacting the original repository.
GitHub has many useful features that allows us to visually track changes made on a file, acknowledge contributors for their contributions and keep projects up to date.

There are many features of  version control system that can be accessed via GitHub web interface, for example, creating new files, updating them, reviewing others work and tracking different versions.

Some GitHub features can be accessed through 'Git',(discussed later in this chapter), but, many project management and communication related features can be accessed only via its web interface.
For example, opening or raising an issue related to the project, involve collaborators in discussing those issue via comments, request help and review each other's changes online.
GitHub can help maintain transparency and effective communication among the various stakeholders by making the entire history of the project traceable online, which adds to the reusability aspects of research.

### Getting started with GitHub

First, let's create an account (if your don't have one already) by signing up on [GitHub](https://GitHub.com/).

| ![a screengrab of the GitHub home page for creating an account](../../figures/github-account.png)         |
| ------------------------------------------------------------------------------------ |
| A screenshot of the GitHub home page, that shows how you can create or sign into your account  |

To test its features properly, let's create a new repository for your project by clicking the plus sign on the dropdown menu in the upper right hand of the screen.
Enter a name for your project repository, check box for "Initialize this repository with a README" and click "Create Repository".

In this chapter we will create a test repo called "friendly-github-lesson", as shown in th image below.

| ![screengrab showing how to create a new repo](../../figures/github-repo.png) |
| ------------------------------------------------------------------------------------ |
| A screenshot from the GitHub profile, showing how a new repository can be created for a project called "friendly-github-lesson" |

Congratulations! You just created your GitHub repository.
You will find your repository with a README.md file, which is currently empty as we haven't yet added any information there.
A README file in a landing page for the repo which should give information about your project, list names and contact details for your team, point to the way for new collaborators to get involved, invite others with specific skills.
We will discuss in detail how to write a good README file later, but for now, let's start by adding a couple of sentences about your project.
Open the file by clicking on the file name, click on the edit (pen symbol) button to start writing and scroll down to save your file, which is called "commit" in Git and GitHub (see the image below).

| ![screengrab showing how to edit a file on GitHub](../../figures/github-readme.png) |
| ------------------------------------------------------------------------------------ |
| An illustration showing how to edit files on GitHub and "commit" changes |

Every time you save your file you "commit" the proposed changes and create a new version.
A "commit message" allows you to add a comprehensive description on what is being updates.
You can learn more about commit and commit message in the [version control chapter](/version_control/01/vcs_workflow).

To create a new file, you can go to your repository and click on 


### Styling with markdown

The '.md' stands for Markdown. 

<!---Add MarkDown tutorial here--->

### Create a local copy of an online repository

In the [version control chapter](/version_control/01/vcs_workflow) we learned how to use Git as a version control system.
There are some GitHub features that can be accessed via command-line Git tool.
For example, one can create an independent local copy of the project using the following Git command: 

```
git clone <insert GitHub link of the repository here>
```

Collaborators can update their local version of an online repository or *pull* other's work into their own copy using the command: 
```
git pull
```
Similarly, they can edit files locally and stage their updates (`git add .`), commit changes to a new version (`git commit`) and *push* changes to the remote online repository using the Git command:
```
git push
```

### Link a local project on your computer to an online repository

To link a project on your computer to a new GitHub repository (preferably with the same name) you need to follow the standard workflow for creating a Git repository (described in the [version control chapter](/version_control/01/vcs_workflow)) by using the following set of commands in the terminal one by one:

```
cd <your project folder>
git init
git add .
git commit
```
Assuming that you have a GitHub repository that you want want to commect with this project, run the following command

```
git remote add origin <GitHub repository link for your project>
```

Then, *push* all the files on your computer to the online version so they match via:

```
git push -u origin master
```

You can the go on and make more commits on your computer.
When you want to push them to your online version similarly you do:

```
git push origin branch_you_want_to_push_to
```

You can also make changes directly on the GitHub by editing the online repository, and *pull* those changes locally by using the Git commans `git pull`

Others can then clone the repository to their computer by using:

```
git clone https://GitHub.com/your_username/repository_name.Git
```

They can make and commit changes to the code without impacting the original, and push their changes to *their* online GitHub account using:

```
git push -u origin master
```

The exact same procedure applies to you if you want to clone someone else's repository.

#### Pull requests

When everyone's has a copy of the code that they're on, they can *push* their changes to the online repository.
However, if you can not the owner of that repository, you will be able share your work with the help of *pull requests*.

A pull request allows a contributor to request the owner *pull* your changes into their version of the project.
Say person A has made changes they want to share with person B.
On GitHub Person A needs to go to person B's copy of the project and click the "New pull request" button.
From there they can indicate which of their branches they would like person B to pull changes from, and which branch they want the changes pulled to.
If person B accepts then person A's changes will be merged into their repository by GitHub.
They can discuss the request in comments, and make further commits to the request before it is accepted if necessary.

When person B is setting up the pull request GitHub will automatically check whether there would be any merge conflicts if they accept, and highlight them if there are.
These can then be resolved in further commits before the request is accepted, keeping the merge clean and painless.

Once the request is accepted GitHub will merge person A's changes into person B's online copy of the repository.
Person B can the *pull* those changes down to the copy on their computer using:

```
git pull origin master
```

It is also possible to make pull requests via the command line.
A guide on how to do so is available [here](https://Git-scm.com/docs/Git-request-pull).

### Good practice

In your GitHub repository you should **include a license** to allow others to re-use your work legally.
GitHub makes this very easy, simply click the "Create new file" button, name it "License.md" and a drop down menu will appear offering you a selection to choose from. The legalese can seem intimidating however [this](https://choosealicense.com/) website offers a very simple mechanism to help you pick the best license for your project.

You should also **include a readme file** where you include useful information about what the project is, how to use it and how to contribute to it.
Switching between projects in your work is common, let alone that you might need to poke at your own previous projects from time to time.
This information will also assist you collaborators, and your future employer might want to check your existing GitHub projects.

There are plenty of readme templates available online, pick one you like, but here is a list of the main things a readme should include:

- The project name and what it is: This will greatly help the random prospective contributor to get an idea of the project.
Include a few key points that describe the main features of the project and what are the main features you are implementing.
This helps to quickly compare other projects with yours and to give an idea that why the project exists in the first place.
- Instructions on how to install the project: The installer might be a collaborator, someone that comes across and is interested in the project, or even you if you get a new machine and need to re-install your project.
Nevertheless, it's a total waste of both of your resources to start figuring out how to just get started with the project.
This should also include any prerequisites that will be needed to run the project.
The best thing you can do is to just write up the installation instructions when you first do them yourself, and you will quickly save hours of work in the future.
- Instructions for how to run the project and any associated tests: If you have been working on your project it may seem obvious how to run it, but this will likely not be the case for someone coming across it for the first time.
- Links to related material.
- List of authors/contributors to the project, possibly with contact information.
- Acknowledgements.

It can be a good idea to **include documents outlining a code of conduct, agreed ways of working, and contributing guidelines**, though depending on the level of detail you want to provide the latter two can also work as sections within the readme.
These documents make explicit expectations for those working on/contributing to the project, making life easier for everyone.
Similarly depending on the scope of your project you may wish to **provide templates for how contributors should make pull requests or raise issues**.

You can also **make use of one of GitHub's major features- issues**.
Anyone can raise an issue with the project and discuss it.
By making issues for any significant changes a record can be kept of the history of the project.
GitHub has a myriad of other features such a milestones and project boards which may also be of use.

In pull requests you should **clearly explain what the changes you've made are and why you made them**.
If your changes address and issue that has been raised reference it directly.
If your request fixes and issue and you include "will fix #the_issue_number >" in the pull request, if the pull request is merged it will automatically close the referenced issue, keeping the issue queue nice and clean!
This also works for using commit messages to close issues too.

## Summary of key Git commands specific to GitHub

| Command                       | Use                                                                      |
| ----------------------------- | ------------------------------------------------------------------------ |
| git clone URL                 | Makes a clone of the repository at the specified URL                     |
| git remote add origin URL     | Links local repository and repository at the specified URL               |
| git push origin branch_name   | Push local changes to the specified branch of the online repository      |
| git pull origin branch_name   | Pull changes to online repository into local repository                  |