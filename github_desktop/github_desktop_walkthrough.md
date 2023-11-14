# GitHub Desktop 

This walkthrough demonstrates the standard Git workflow, using the GitHub desktop application. The application can be installed from <https://desktop.github.com/>.

Users can log into the desktop app using their GitHub credentials.

## Settings

Keeping defaul settings is recommended. As needed, review and update

- **Integrations:** The default external editor and shell can be updated under this tab.
- **Git:** User name, email, and default branch name for new repositories can be set here. Setting the default branch name to *main* is recommended.

## Creating Repositories

There are three ways to add a repository.

1. Clone an existing repository from GitHub.
1. Initialize a new repository on your local machine. Publishing the new repository will also add the repository to GitHub.
1. Add an existing repository on your local machine. This will add the repository to GitHub.

We are going to demonstrate the first two methods.

### Clone an existing repository

1. Create a new repository on GitHub. The settings can be whatever you prefer - try different settings!
1. Once the repository has been created on GitHub, return to the desktop application and select *Add -> Clone repository*.
1. Use the wizard to filter or search for the repository on GitHub. 
1. Once a repository has been selected for cloning, check the local path and change as needed to clone the repository to an accessible location on your workstation.
1. When ready, select *Clone*.
1. Note that the desktop application will update to reference the cloned repository as the current repository.

### Create a new repository

1. In the desktop application, select *Add -> Create new repository*.
1. Fill out the requested fields. In particular, check the local path and update as needed.
1. When ready, select the button *Create repository*.
1. The repository is not created on GitHub until you sync it the first time. Do this by clicking the button to *Publish repository*. You will be asked to confirm some settings for the remote repository on GitHub. When ready, click the button to *Publish repository*.
1. Go to GitHub and confirm that your repository has been published.


## The Git workflow

### App layout

First, we will step through the tabs and features of the application.

Tabs:

- Current repository: Shows the status and history of commits to the current repository.
- Current branch: Manage branches, merges, pull and push requests. This introduction does not cover branches in Git.
- Sync: Less a tab and more of a button to sync the local with the remote repository by either fetching/pulling changes from the remote repository to local, or pushing changes from the local repository to the remote.

Functions:

- Open the repository in the default editor.
- View the files in your operating system's file management application.
- View the repository on GitHub.

Settings:

Under *Repository -> Repository settings*, add an expression to the .gitignore file for the repository. This file will be created when something is added to the list.

### Key concepts

Imagine taking a group photo. The process can generally be broken down into three steps:

- Rounding up people to include in the photo. Staging the photo.
- Taking the photo or snapshot.
- Sharing or otherwise publishing/circulating the snapshot.

This is analagous to the Git workflow, in which we

- **Add** documents to be included in the next snapshot.
- **Commit** a snapshot of the current state of a repository.
- **Push** one or more commits to a remote repository (typically on GitHub).

The following image shows the workflow:

<https://raw.githubusercontent.com/unmrds/cc-version-control/7defd94a0c48f65045b40cada4021de02bb3e4e0//images/basic_cycle.png>

Let's step through this process in the desktop application.

### Add

Pick one of the repositories you just created. Navigate to it using a file manager, or by clicking the button in the app to *Show in Explorer* (Windows).

1. Set up the workspace - note that you can add files and directories. Empty directories won't be tracked for changes. That is, Git only tracks changes to documents - empty directories cannot be staged for commits (snapshots).
1. Add at least one file to the repository. **Text formats are recommended**. Add some text to the file.
1. Go to the desktop application. Note that the view of the current repository ha changed. 
	- Under the *Changes* tab, new documents are indicated with a green plus symbol.
	- Clicking on a document shows changes to the document since the previous commit.

This step demonstrates an important difference between using Git on the command line and using the desktop application. Using the command line, we have to explicitly *add* documents to the next commit (snapshot) using the ```git add``` command. In the desktop application, all new documents are automatically added. In order to exclude a document from the next commit, we have to de-select the check box next to the file name.


 








