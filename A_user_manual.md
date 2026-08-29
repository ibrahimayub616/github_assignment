# Exercise A: User Manual Procedure

## Setting Up a GitHub Repository and Making a First Commit

### Introduction

This procedure explains how to create a GitHub repository from scratch, connect it to a local project, and make the first Git commit. It is written for a first-semester computing student who has basic computer knowledge but is new to Git and GitHub.

## Prerequisites

Before starting, you need:

* A computer with Windows, macOS, or Linux.
* An internet connection.
* A GitHub account.
* Git installed on your computer.
* Visual Studio Code or another code editor.
* Basic knowledge of creating folders and files.

## Step-by-Step Procedure

### Step 1: Open Visual Studio Code

**Action:** Open Visual Studio Code on your computer.

**Expected result:** Visual Studio Code opens successfully.

### Step 2: Create a project folder

**Action:** Create a new folder named `computing-assignment`.

**Expected result:** A folder named `computing-assignment` appears on your computer.

### Step 3: Open the project folder

**Action:** Open the `computing-assignment` folder in Visual Studio Code.

**Expected result:** The folder appears in the VS Code Explorer panel.

### Step 4: Create a README file

**Action:** Create a file named `README.md`.

**Expected result:** The `README.md` file appears inside the project folder.

### Step 5: Add a project title

**Action:** Add `# Computing Assignment` to the README file.

**Expected result:** The project title appears in the README file.

### Step 6: Open the terminal

**Action:** Open the VS Code terminal by selecting **Terminal → New Terminal**.

**Expected result:** A terminal appears at the bottom of the VS Code window.

### Step 7: Initialize Git

**Action:** Run `git init` in the terminal.

**Expected result:** Git creates a new local repository in the project folder.

### Step 8: Check the repository status

**Action:** Run `git status` in the terminal.

**Expected result:** Git displays the files that are not yet tracked.

### Step 9: Stage the files

**Action:** Run `git add .` in the terminal.

**Expected result:** The project files are added to the staging area.

### Step 10: Create the first commit

**Action:** Run `git commit -m "Initial commit"` in the terminal.

**Expected result:** Git creates the first commit containing the project files.

### Step 11: Open GitHub

**Action:** Open GitHub in a web browser.

**Expected result:** The GitHub website opens.

### Step 12: Create a new repository

**Action:** Select **New repository** on GitHub.

**Expected result:** The new repository creation form appears.

### Step 13: Enter the repository name

**Action:** Enter `computing-assignment` as the repository name.

**Expected result:** The repository name is displayed in the creation form.

### Step 14: Create the repository

**Action:** Select **Create repository**.

**Expected result:** GitHub creates the new remote repository.

### Step 15: Copy the repository URL

**Action:** Copy the HTTPS URL displayed by GitHub.

**Expected result:** The GitHub repository URL is copied to the clipboard.

### Step 16: Add the GitHub remote

**Action:** Run `git remote add origin YOUR-REPOSITORY-URL` in the VS Code terminal.

**Expected result:** The local repository is connected to the GitHub repository.

### Step 17: Rename the main branch

**Action:** Run `git branch -M main` in the terminal.

**Expected result:** The current branch is named `main`.

### Step 18: Upload the commit

**Action:** Run `git push -u origin main` in the terminal.

**Expected result:** The committed files are uploaded to GitHub.

### Step 19: Open the repository

**Action:** Open the repository page on GitHub.

**Expected result:** The repository displays the uploaded project files.

## Screenshot Description

A useful screenshot should show the VS Code terminal after running the command:

```text
git push -u origin main
```

The screenshot should show a successful push message and the GitHub repository name. This provides evidence that the local project was successfully uploaded to GitHub.

## Troubleshooting

### Common Error: "git is not recognized"

This error usually means that Git is not installed or Git was not added to the computer's PATH.

**Solution:** Install Git, restart Visual Studio Code, and run:

```text
git --version
```

If Git is installed correctly, the terminal should display the installed Git version.

## Conclusion

The completed procedure creates a local Git repository, makes the first commit, connects the repository to GitHub, and uploads the project. The GitHub repository can then be shared with an instructor using its repository URL.
