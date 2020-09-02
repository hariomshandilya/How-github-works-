# How-github-works-
<b>Step 0: Install git and create a GitHub account </b>
- The first two things you'll want to do are install git and create a free GitHub account.

Follow the instructions here to install git (if it's not already installed). Note that for this tutorial we will be using git on the command line only. While there are some great git GUIs (graphical user interfaces), I think it's easier to learn git using git-specific commands first and then to try out a git GUI once you're more comfortable with the command. <br /> 

Once you've done that, create a GitHub account here.  (Accounts are free for public repositories, but there's a charge for private repositories.)

<b> Step 1: Create a local git repository</b>
When creating a new project on your local machine using git, you'll first create a new `repository` (or often, 'repo', for short). 

To use git we'll be using the terminal. If you don't have much experience with the terminal and basic commands, check out this tutorial (especially the 'Navigating the Filesystem' and 'Moving Around' sections).
<br />
To begin, open up a terminal and move to where you want to place the project on your local machine using the cd (change directory) command. For example, if you have a 'projects' folder on your desktop, you'd do something like:
```mnelson:Desktop mnelson$ cd ~/Desktop
mnelson:Desktop mnelson$ mkdir myproject
mnelson:Desktop mnelson$ cd myproject/ 
```
- To initialize a git repository in the root of the folder, run the git init command:
```mnelson:myproject mnelson$ git init
Initialized empty Git repository in /Users/mnelson/Desktop/myproject/.git/
```
<b>Step 2: Add a new file to the repo</b>
Go ahead and add a new file to the project, using any text editor you like or running a `touch` command.<br />
Once you've added or modified files in a folder containing a git repo, git will notice that changes have been made inside the repo. But, git won't officially keep track of the file (that is, put it in a commit - we'll talk more about commits next) unless you explicitly tell it to

```mnelson:myproject mnelson$ touch mnelson.txt
mnelson:myproject mnelson$ ls
mnelson.txt
```
After creating the new file, you can use the git status command to see which files git knows exist.
``mnelson:myproject mnelson$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	mnelson.txt

nothing added to commit but untracked files present (use "git add" to track)
``
- An interlude: The staging environment, the commit, and you
One of the most confusing parts when you're first learning git is the concept of the staging environment and how it relates to a commit.

A `commit` is a record of what files you have changed since the last time you made a commit. Essentially, you make changes to your repo (for example, adding a file or modifying one) and then tell git to put those files into a commit.Commits make up the essence of your project and allow you to go back to the state of a project at any point.

<b>Step 3: Add a file to the staging environment</b>
If you rerun the git status command, you'll see that git has added the file to the staging environment (notice the "Changes to be committed" line).  
``mnelson:myproject mnelson$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   mnelson.txt
  ``
  <b>Step 4: Create a commit</b>
  Run the command git commit -m "Your message about the commit"
  ``
  mnelson:myproject mnelson$ git commit -m "This is my first commit!"
[master (root-commit) b345d9a] This is my first commit!
 1 file changed, 1 insertion(+)
 create mode 100644 mnelson.txt 
 ``
 
