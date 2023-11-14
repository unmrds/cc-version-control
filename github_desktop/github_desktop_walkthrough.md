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

- **Add** (stage) documents to be included in the next snapshot.
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

### Commit

1. Make some more edits to a file.
1. Look at the ```diff``` output in the *Changes* tab. Note that additions and deletions are color coded.
1. In the bottom left of the window, add a comment to describe the changes. This should be short, but note there is a space for a longer, more descriptive message.
1. Click the button *Commit to main*.
1. Before we push to the remote (GitHub), review the *History* tab. Note that all commits are listed in the history.

Take some time to edit files and make a couple more commits.

### Push & Fetch/Pull

If we compare our local repository with the remote on GitHub, we can see that there are local changes which need to be synced with the remote. That is, we have made changes to files in our local repository that have not been shared with GitHub. 

We use the *git push* and *git fetch* commands to synchronize the local and remote repositories. Pushing is the process of sending local changes to the remote. Fetching (and then pulling) is the process of retrieving changes from the remote repository to our local environment.

1. Click the down arrow next to the tab that should say *Push origin*. Click the button to *Fetch origin*. This is not required, but can be useful for avoiding conflicts.
1. Once the fetch command has run, click the tab to *Push origin*.
1. View the repository on GitHub to confirm that our changes were pushed to the remote.

### Workflow summary

The four commands demonstrated above make up the basic Git-based workflow:

1. When starting work in a repository, use *fetch* and *pull* to update your local repository with unsynced changes that may exist on the remote repository.
1. As you work, *add* files to stage them for the next *commit*.
1. *Commit* one or more changes as snapshots of the local repository. It is recommended to use frequent small commits, rather than infrequent, large commits.
1. Periodically *push* snapshots to the remote repository in order to sync the remote with your local copy.

## History

A powerful feature of Git is that every copy or clone of a repository is a complete copy. In general, all changes committed to your local repository will be available to your collaborators within their own copies of the repository.

1. In GitHub, click *n commits* (where *n* is the number of commits in your repository) to see the history.
1. Note the list of commits is usually the same as viewing the *History* tab in the desktop application.
1. Commits include the commit message, and the name of the person who made the commit. 
1. Click on the commit message to see the contents of the commit. 
1. We can also browse the entire repository at the point at which a commit was made.

This information is generally the same as using the *git log* command in the command line. Every clone of the repository will include this entire history.

### Discard

As we start to manage versions of files, one case where we may want to go back to a previous point in the repository's history is when we have uncommitted changes that we decide not to keep.

If we want to go back to the previously committed version of a file, in the desktop app we simply discard the changes.

1. Make some changes to a file in your repository. Note that GitHub Desktop is automatically adding/staging files for next next commit. Here, we just want to avoid making a commit.
1. View the changes in the *Changes* tab. 
1. Right-click the file which has the changes to be discarded. Select *Discard changes*. Open the file to confirm that the discarded changes are gone. Note - if the file was open when you discarded the changes, try closing it and then opening it again.

### Revert

In other cases, we may want to return a repository to a previous state. Reverting allows us to effectively undo all the changes since the commit we are reverting to.

Note that commits have to be reverted in reverse order. So if you want to revert to the state of your repository three commits ago, you have to individually revert the previous commit, the next previous commit, and then the next previous commit before that.

1. Make edits, add and commit changes to your repository.
1. From the *History* tab, select the previous commit. Right click the commit and select *Revert changes in commit*. Inspect files to confirm that the commit was reverted.

How would you return to the state of the repository before reverting? Revert the reverts! (This also has to be done in order!)

### Checkout

In the command line, *git checkout* can be used to check out previous versions of individual files. This can be useful, but does not appear to be supported by the desktop app at this time. Instead, this feature is used to check out the state of the entire repository at a previous commit for the purposes of comparison. 

Checking out the repository this way results in a state known as "detached head," in which changes to the repository will not be saved.

1. Make some changes to a file in your repository. Add and commit.
1. Under *History*, select a previous commit. Right click and select *Checkout commit*.
1. A warning message will appear. Click the button to *Checkout* the commit.
1. Make changes, add, commit. Note that we cannot push our changes to the remote.
1. From the branch tab, select *main*. Inspect the files you edited while the repo was in a detached head state. Where are the changes?

### Wait! Which version was THE version?

Git's features for managing history and the state of a repository are very powerful, but can result in unexpected consequences. It's worth remembering that you can almost always recover some previous version of a file. That said, we recommend having policies and workflows in place to prevent confusion.


## Conflicts

When syncing repositories via push or pull, or when merging branches, Git compares different versions of files and merges them into a single current version. There are many potential conflicts which Git manages effectively. Sometimes, Git is unable to determine how two versions of a file can be reconciled. This results in a conflict, which we have to resovle manually.

Conflicts can happen when we collaborate with others, but also when we are working by ourselves.

1. Go to the remote repository in GitHub. 
1. Select a file that you have been editing locally. Use GitHub's web editor to make some changes to the file. Commit the changes.
1. Note that our local repository is now one commit behind the remote.
1. In the desktop app, click the *Fetch origin* tab. This essentially does a status check to compare the local with the remote, but it doesn't automatically pull changes from the remote. To finish the process, click the button to *Pull origin*.

No conflicts there! That is the recommended workflow. Sometimes we forget to fetch/pull before we begin working in our local repository. Let's do this again.

1. Go to the remote repository in GitHub.
1. Select a file that you have been editing locally. Use GitHub's web editor to make some changes to the file. Commit the changes.
1. Without doing a fetch/pull, make some edits to the same file in your local repository.
1. In the desktop app, add and commit the local changes.
1. Click the button to *Push origin*. You should receive an error, *Newer commits on remote*. The error message is actually pretty helpful here. It advises us to fetch these new commits and reconcile them. Let's do that!
1. Click the *Fetch* button.
1. Recalling that *Fetch* is essentially a status check, click the *Pull origin* button to pull the conflicting changes from the remote repository.
1. A box pops up telling us to *Resolve conflicts before Merge*, and offering some options for doing this. Click the *X* at the top right of the box to close it. We will resolve the conflict manually.
1. Open the file with the conflict. Note that it is annotated - our local changes are preceeded by ```<<<<<<< HEAD```. After our local changes there is a series of equal signs to denote a separate between our local changes and the conflicting changes from the remote. These previous changes are followed by several right angle brackets and the commit hash. (Note that the HEAD is always the most recent commit, regardless of where the snapshot was taken - locally or on the remote, or some other copy of the repository. So the commit represented by HEAD is not necessarily always going to be the most recent local commit.)
1. Edit the file to resolve the conflict. One of you must do this.
1. In the desktop app, add, commit, and push the resolved file.
1. View the repository and the reconciled file in GitHub. Note that there wasn't a second conflict when we pushed to the remote - Git knows a conflict has been resolved on the file, and completes the merge accordingly.

Now - do it again for the practice. Force and resolve a conflict.

## Ignoring files

There are typically datasets, file types, and directories that we don't need Git to track, but which we may need to keep in our repository. Think of large data files (or any data file, for that matter), results, figures, etc. We can manage these using the *.gitignore* file. This is a hidden file that allows us to use string pattern matching on file names to tell Git not to track changes to individual files, groups of files, files of specific types, files in specific directories, etc.

1. From the *Repository* menu, select *Repository settings*.
1. Select *Ignored files*.
1. In the box provided, add some file names, directory names, or patterns to ignore. (Try *.csv, .ipynb_checkpoint/, .idea/)
1. Save when done. The .gitignore file has been added - commit and push.
1. Create and edit some files with the ignored endings - note that changes do not appear in the *Changes* tab. 

For more info on pattern matching, etc., see the documentation at <https://git-scm.com/docs/gitignore>.











