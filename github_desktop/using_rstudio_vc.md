# RStudio Version Control

RStudio is one of several development environments that support Git based version control. The workflow is similar to that demonstrated in the GitHub desktop application.

## Install Git

It is possible to use the GitHub Desktop application to manage a Git workflow of an RStudio project, or even just a folder with R scripts in it. The process would be similar to that described in the GitHub Desktop walkthrough tutorial included in this repository. In such cases, creating or cloning a repository, as well as all common workflow actions including adding, committing, pushing, and fetching/pulling, would be executed through the desktop application.

The steps described below demonstrate how RStudio's Git based version control features can be used in parallel with, or as an alternative to, the desktop application. However, using these features requires that a standalone instance of Git be installed on your local machine. This free, open source application is available for all platforms from <https://git-scm.com/>.

The standalone Git application shouldn't create conflicts with the GitHub desktop application (UNM RDS has been using both for some time and have not run into any problems). However, they are two different applications and don't share configuration information. So, before you can make commits or connect to a remote repository, Git needs to know some things about you.

1.  Open a UNIX command line client (or "shell"). In Apple and Linux environments, this is the *terminal* application. In Windows, with Git installed as described above, from the Start Menu launch *Git Bash*.
2.  In the shell, type the following command and press ENTER. Be sure to replace *YOUR NAME* with your name!

```         
git config --global user.name "YOUR NAME"
```

3.  Next, type a second command and press ENTER. As above, replace *YOUR EMAIL* with your email address. This should be the email address you used to create your GitHub account.

```         
git config --global user.email "YOUR EMAIL"
```

Type `exit` or use the *X* at the top right of the shell window to close the shell. You are now ready to use the Git features in RStudio.

## Create a repository

This is the process for creating a new RStudio project with version control enabled.

1.  Launch RStudio and select the button to create a new project.
2.  Select *New Directory -\> New Project*.
3.  Provide a directory name, and as needed browse to the directory where the repository will be located.
4.  Select the option to *Create a git repository*.
5.  Select the button to *Create Project*.
6.  Click the *Git* button in the toolbar to explore the repository. Select *Commit* to view changes.
7.  Several features are similar to the GitHub desktop app:
    -   *Changes* and *History* tabs. Note that we have to select a branch to view history.
    -   A *diff* window showing changes to files since the previous commit. (Probably currently blank.)
    -   A space for a commit message.
8.  In the *Files* pane of RStudio, create a new folder called *data*.
9.  Edit the .gitignore file to ignore files in the data directory.
10. Open the Git window in RStudio. In the **History** tab, select the file *.gitignore* to view staged changes. Note that this also stages the file for the next commit.
11. Add a commit message and select the *Commit* button.
12. Under the **Changes** tab, select the *main* branch to view the commit log. The commit you just made should be listed.

At this point, we have initialized a Git repository in our project, added (staged) a file and committed the change. However, a difference between using Git in RStudio and using the GitHub Desktop application is that we have to go through a few extra steps to connect the local repository to a remote copy on GitHub.

## Connect to GitHub

We have set up version control for our new project, but we need to add GitHub as the remote. If we check the *Project Setup* in the Git tool in RStudio, we see that there is no *Origin*. "Origin" is a commonly used term for the remote repository.

We can use the GitHub desktop application to make this connection. In the desktop app:

1.  From the *Current repository* tab, select *Add -\> Add existing repository*.
2.  In the window that opens up, select *Choose...* and navigate to the RStudio project directory we just created. Remember that it has already been initialized as a Git repository.
3.  Once selected, click *Add repository*.
4.  Once the repository opens in the desktop app, note that we can view the changes and history here, too.
5.  Click the tab to *Publish repository*. Add a description and update other settings as appropriate.
6.  When ready, click the *Publish repository* button again.
7.  View the repository on GitHub to confirm that everything worked. Check the *.gitignore* file in GitHub to verify that the *data* directory is listed.

## Git workflow

From here on, the workflow is the same. You can use either the GitHub desktop app or RStudio's Git feature to add, commit, push, and pull.

1.  In GitHub, you may be encouraged to create a README file. Click the button to *Add a README*.
2.  Edit the README and commit changes.
3.  In RStudio, click the *Git* button and select *Commit*.
4.  From the top right corner of the window, select *Pull*.
5.  Barring conflicts, the README.md file should now appear in your local project directory.

## Practice

1.  Add a *scripts* directory to the project.
2.  Create a new file, *my_script.R*, and save it to the *scripts* directory.
3.  Write some R code in the script.
4.  Note that the Git button in RSutdio now includes options to see the *diff* and *log* results for the script, as well as an option to *revert*.
5.  Use either the GitHub desktop app or the Git tool in RStudio to add, commit, and push changes to the remote on GitHub.

Wash, rinse, repeat!
