# RStudio Version Control

RStudio is one of several development environments that support Git based version control. The workflow is similar to that demonstrated in the GitHub desktop application.

## Create a repository

This is the process for creating a new RStudio project with version control enabled.

1. Launch RStudio and select the button to create a new project.
1. Select *New Directory -> New Project*.
1. Provide a directory name, and as needed browse to the directory where the repository will be located.
1. Select the option to *Create a git repository*.
1. Select the button to *Create Project*.
1. Click the *Git* button in the toolbar to explore the repository. Select *Commit* to view changes.
1. Several features are similar to the GitHub desktop app:
	- *Changes* and *History* tabs. Note that we have to select a branch to view history.
	- A *diff* window showing changes to files since the previous commit. (Probably currently blank.)
	- A space for a commit message.
1. In the *Files* pane of RStudio, create a new folder called *data*.
1. Edit the .gitignore file to ignore files in the data directory.
1. Open the Git window in RStudio. Select the file *.gitignore* to view staged changes. 
1. Add a commit message and select the *Commit* button.

## Connect to GitHub

We have set up version control for our new project, but we need to add GitHub as the remote. If we check the *Project Setup* in the Git tool in RStudio, we see that there is no *Origin*. "Origin" is a commonly used term for the remote repository.

We can use the GitHub desktop application to make this connection. In the desktop app:

1. From the *Current repository* tab, select *Add -> Add existing repository*.
1. In the window that opens up, select *Choose...* and navigate to the RStudio project directory we just created. Remember that it has already been initialized as a Git repository.
1. Once selected, click *Add repository*.
1. Once the repository opens in the desktop app, note that we can view the changes and history here, too.
1. Click the tab to *Publish repository*. Add a description and update other settings as appropriate.
1. When ready, click the *Publish repository* button again.
1. View the repository on GitHub to confirm that everything worked. Check the *.gitignore* file in GitHub to verify that the *data* directory is listed.

## Git workflow

From here on, the workflow is the same. You can use either the GitHub desktop app or RStudio's Git feature to add, commit, push, and pull. 

1. In GitHub, you may be encouraged to create a README file. Click the button to *Add a README*.
1. Edit the README and commit changes.
1. In RStudio, click the *Git* button and select *Commit*.
1. From the top right corner of the window, select *Pull*.
1. Barring conflicts, the README.md file should now appear in your local project directory.

## Practice

1. Add a *scripts* directory to the project. 
1. Create a new file, *my_script.R*, and save it to the *scripts* directory.
1. Write some R code in the script.
1. Note that the Git button in RSutdio now includes options to see the *diff* and *log* results for the script, as well as an option to *revert*.
1. Use either the GitHub desktop app or the Git tool in RStudio to add, commit, and push changes to the remote on GitHub.

Wash, rinse, repeat!