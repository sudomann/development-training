# Beginner's Guide to Git and GitHub

This guide will help you use Git and GitHub for the first time. We'll work with the [development-training](https://github.com/sudomann/development-training) repository using PowerShell on Windows.

## What's a Repository?

A repository (or "repo") is like a project folder that Git keeps track of. Think of it as a special folder that remembers all changes made to its files.

## Before You Start

You need:

- [Git](https://git-scm.com/downloads) installed on your computer
- A [GitHub Personal Access Token (PAT)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) - this is like a special password for accessing GitHub securely

## Step 1: Getting the Repository on Your Computer

1. Open PowerShell and go to where you want to keep the repository:

   ```powershell
   cd "C:\Users\YourUsername\Documents"   # Replace with your preferred location
   ```

2. Copy the repository from GitHub to your computer:

   ```powershell
   git clone https://github.com/sudomann/development-training.git
   ```

3. Move into the new folder that was just created:

   ```powershell
   cd development-training
   ```

## Step 2: Setting Up Your Login Info

To avoid typing your username and password every time:

```powershell
git config --global credential.helper manager-core
```

When asked to log in:

- Username: Your GitHub username
- Password: Use your PAT (not your GitHub password)

## Understanding Some Basic Concepts

### The Main Branch

- A branch is like a version of your project
- The "main" branch (or sometimes called "master") is the default branch
- "main" is the newer default name, while "master" was the old default
- You can rename these branches - the names "main" or "master" are just common defaults

### What is "origin"?

- When you clone a repository, Git calls the GitHub version "origin"
- "origin" is just a nickname for the URL of your repository on GitHub
- When you type `git push origin main`, you're saying "send my changes to the main branch on GitHub"

### What is a Remote?

- A remote is any version of your repository that's hosted somewhere else (like on GitHub)
- "origin" is a remote - it's the GitHub version of your repository
- Think of it like this: your computer has a copy, and GitHub has a copy - the GitHub copy is called a "remote"

## Common Tasks

### 1. Making Changes (Committing)

When you change files in your repository, you need to save these changes in Git:

1. See what files you changed:

   ```powershell
   git status
   ```

2. Tell Git which files to save (the `.` means "all files"):

   ```powershell
   git add .
   ```

3. Save your changes with a message explaining what you did:

   ```powershell
   git commit -m "Describe what you changed here"
   ```

### 2. Sending Changes to GitHub (Pushing)

After committing, your changes are only on your computer. To share them:

```powershell
git push origin main
```

This sends your changes to the main branch on GitHub (remember, "origin" means GitHub).

### 3. Getting Updates from GitHub (Pulling)

To get changes others have made:

```powershell
git pull origin main
```

This gets any new changes from the main branch on GitHub and updates your computer's copy.

### 4. Working with Branches

Branches let you work on new features without changing the main code.

1. Create a new branch:

   ```powershell
   git branch my-new-feature   # Replace my-new-feature with a descriptive name
   ```

2. Switch to your new branch:

   ```powershell
   git checkout my-new-feature
   ```

3. Make changes, commit them, and send to GitHub:

   ```powershell
   git add .
   git commit -m "Describe your changes"
   git push origin my-new-feature
   ```

4. Go back to the main branch when you're done:

   ```powershell
   git checkout main
   ```

## Tips

- Always `pull` before you start working to get the latest changes
- Write clear commit messages that explain what you changed
- If you're not sure what's happening, use `git status` to check
- Make small, focused commits rather than big ones with many changes
- If you make a mistake, don't worry! Git keeps a history of everything

## Common Issues

- If `git push` fails, try `git pull` first - someone might have pushed changes while you were working
- If you see "master" instead of "main" in an old repository, don't worry - they mean the same thing
- Always make sure you're on the right branch before making changes (use `git status` to check)
