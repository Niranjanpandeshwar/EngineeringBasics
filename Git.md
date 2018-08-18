[Shells](Shells.md#shells) | [Development Environments](PackageManagers.md#development-environments) |  [Git](Git.md#git) | [Virtural Environments](Environments.md#environments) | [Markdown and Editors](MarkdownEditors.md#markdown) | [Programming Languages](Programming.md#programming) | [Task Management](OnlineTools.md#online-tools) | [Specialized Tools](SpecializedTools.md#specialized-tools) 

# Git

![image](https://cloud.githubusercontent.com/assets/742934/15635543/d1044ff6-25ae-11e6-9680-077830cff8f5.png)

### Why Version Control?

> You're working on a team project and need to make edits to reports and code. You waiting for your team member to make a change and then email you back another a copy. There has to be a better way...

"Version control is the lab notebook of the digital world: it’s what professionals use to keep track of what they’ve done and to collaborate with other people. Every large software development project relies on it, and most programmers use it for their small jobs as well. And it isn’t just for software: books, papers, small data sets, and anything that changes over time or needs to be shared can and should be stored in a version control system." -- [Version Control with Git](http://swcarpentry.github.io/git-novice/)

#### Git Tutorial

Work through the following tutorial. This will walk you through the most basic git commands in a simulated web terminal.

https://try.github.io/levels/1/challenges/1

#### Git Branching Playground

We will solve the "Introduction Sequence" levels in:  
http://pcottle.github.io/learnGitBranching/   

![example](https://cloud.githubusercontent.com/assets/742934/9494425/c4dd4b66-4bd3-11e5-9aac-04bfc8fed771.png)

This will help you visualize the true structure of a git repository and understand how concepts such as branching are implemented.

## Practice: Creating a Repo

Let's try the basics. Let's create a new local git repository. You can create one inside your course folder (Project0). Inside `Project0`, use the command `git init` to create a new repository. Perform the following steps:

1. Create a new empty file (README.md). There is a useful command: `touch README.md`. Edit the file to say:
   ```
   # Project 0
   Hello!
   ```
   Tip: If you want to open a graphical window inside your current shell, you can run `start .` (Windows) or `open .` (Mac/Linux). 

2. Commit the file.

While having a local git repository is cool, we should connect it to another remote repository. Perform the following steps:

1. Create a repo on GitHub (If you are a NCSU student, use GitHub Enterprise: https://github.ncsu.edu). 

2. Follow the instructions on GitHub to add a remote url to an *existing git repository*. Basically, you need to run something like: `git remote add origin https://github.com/<user>/<repo>.git`

3. Push your changes to GitHub. Verify you can see your updated README.md!

4. On GitHub, edit the README.md, to say "Hello GitHub!". Commit the changes on GitHub. Now you have changes in your remote (origin), that are missing on your local copy.

5. Run `git pull` and verify you now have the updated changes.


## Git Configuration and Security

If you want to make sure your commits are properly linked to your GitHub account, make sure you have configured your computer to have your name and email filled out.

```
$ git config --global user.name "FirstName LastName"
$ git config --global user.email email@example.com
```

You might also consider an authenication strategy. If you're being asked to login everytime your pull/push to your remote repository, you might want to enable caching of your credentials. For example, you could use: 

```
git config credential.helper store
```

However, this may store your credentials in plain text on your computer. There are other platform-specific credential.helpers that you can use to more securely store your credentials.

An alternative approach is to use sshkeys. In this case, you have a public/private keypair, with the public key stored on GitHub. You then use a [different url pattern](https://help.github.com/articles/which-remote-url-should-i-use/) for your commands such as `git clone`. Instead of the `https://` prefix, you instead use `git@github.com:user/repo.git`.

If you are interested in exploring this option: See these guides on GitHub:
  * [Generating SSH Key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
  * [Adding SSH Key to GitHub](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)
  * [Testing SSH Connection](https://help.github.com/articles/testing-your-ssh-connection/)

