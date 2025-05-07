# Git & GitHub Contribution Guide

This guide will walk you through how to set up Git and GitHub to contribute to a project repository.

## Table of Contents

- [Git \& GitHub Contribution Guide](#git--github-contribution-guide)
  - [Table of Contents](#table-of-contents)
  - [iStow Playbook Contribution Guide](#istow-playbook-contribution-guide)
  - [Installing Git](#installing-git)
    - [Windows](#windows)
    - [macOS](#macos)
    - [Linux (Ubuntu/Debian)](#linux-ubuntudebian)
    - [Linux (Fedora)](#linux-fedora)
    - [Verify Installation](#verify-installation)
  - [Setting up Git](#setting-up-git)
  - [Creating a GitHub Account](#creating-a-github-account)
  - [Be a Direct Collaborator (easier step)](#be-a-direct-collaborator-easier-step)
  - [Forking the Repository](#forking-the-repository)
  - [Cloning the Fork](#cloning-the-fork)
  - [Setting up Remote](#setting-up-remote)
  - [Creating a Branch](#creating-a-branch)
  - [Making Changes](#making-changes)
  - [Committing Changes](#committing-changes)
  - [Pushing Changes](#pushing-changes)
  - [Creating a Pull Request](#creating-a-pull-request)
  - [Best Practices](#best-practices)
    - [Keeping Your Fork Updated](#keeping-your-fork-updated)
    - [Before Creating a Pull Request](#before-creating-a-pull-request)
    - [Responding to Feedback](#responding-to-feedback)
    - [Useful Git Commands](#useful-git-commands)

## iStow Playbook Contribution Guide

1. The Chapters are in the `chapters` directory
2. Please do not edit the `naskah.tex` file except necessary
3. Please only contribute the edited version of the manuscript to avoid duplicating with the Google Drive version
4. Enjoy and happy writing 😄

## Installing Git

### Windows

1. Download the installer from [Git for Windows](https://git-scm.com/download/win)
2. Run the installer with default settings (you can customize if you know what you're doing)
3. Choose the default editor (Vim, Nano, or Visual Studio Code)
4. Select "Use Git from the Windows Command Prompt" during installation

### macOS

1. Method 1: Install from [Git website](https://git-scm.com/download/mac)
2. Method 2: If you have Homebrew: `brew install git`
3. Method 3: Xcode Command Line Tools: `xcode-select --install`

### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install git
```

### Linux (Fedora)

```bash
sudo dnf install git
```

### Verify Installation

Open a terminal or command prompt and run:

```bash
git --version
```

You should see the Git version number.

## Setting up Git

Configure your identity (used in commits):

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Optional: Configure your default editor:

```bash
git config --global core.editor "code --wait"  # For VS Code
```

## Creating a GitHub Account

1. Go to [GitHub.com](https://github.com/)
2. Click "Sign up" and follow the registration process
3. Verify your email address
4. Optional: Set up two-factor authentication for security

## Be a Direct Collaborator (easier step)

1. Message Lintang Fitri with your username
2. Wait for the confirmation
3. Start cloning and push your changes

## Forking the Repository

1. Navigate to the main GitHub page of the project you want to contribute to
2. Click the "Fork" button in the top-right corner of the page
3. Select your account as the destination for the fork
4. Wait for GitHub to create a copy of the repository under your account

## Cloning the Fork

1. Go to your fork on GitHub (should be at `https://github.com/YOUR-USERNAME/REPOSITORY-NAME`)
2. Click the green "Code" button
3. Copy the URL (HTTPS or SSH if you have SSH keys set up)
4. Open a terminal and navigate to where you want to store the project
5. Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/REPOSITORY-NAME.git
```

6. Navigate into the project directory:

```bash
cd REPOSITORY-NAME
```

## Setting up Remote

Add the original repository as a remote called "upstream" to keep your fork in sync:

```bash
git remote add upstream https://github.com/ORIGINAL-OWNER/REPOSITORY-NAME.git
```

Verify your remotes:

```bash
git remote -v
```

You should see:

- `origin` (your fork)
- `upstream` (the original repository)

## Creating a Branch

Always create a new branch for your changes:

1. Make sure you're on the main branch and it's up to date:

```bash
git checkout main
git pull upstream main
```

2. Create a new branch with a descriptive name:

```bash
git checkout -b feature/your-feature-name
```

Use meaningful branch names like:

- `feature/add-login-page`
- `bugfix/header-alignment`
- `docs/update-readme`

## Making Changes

1. Open the project in your preferred code editor
2. Make your changes to the code
3. Test your changes locally

## Committing Changes

1. Check which files have been modified:

```bash
git status
```

2. Add the files you want to commit:

```bash
git add filename.ext           # Add specific file
git add directory/             # Add all files in a directory
git add .                      # Add all modified files (use carefully)
```

3. Commit your changes with a descriptive message:

```bash
git commit -m "Add feature: detailed description of changes"
```

Good commit message format:

- Start with a verb (Add, Fix, Update, Improve, Remove, etc.)
- Keep it under 50 characters if possible
- Use the extended description for details if needed:

  ```git
  git commit -m "Add user authentication feature" -m "This implements JWT-based authentication with password hashing and user session management."
  ```

## Pushing Changes

Push your branch to your fork:

```bash
git push origin feature/your-feature-name
```

If this is your first push for the branch, you might need to set the upstream branch:

```bash
git push -u origin feature/your-feature-name
```

## Creating a Pull Request

1. Go to the original repository on GitHub
2. You should see a banner suggesting to create a pull request from your recently pushed branch. If not, click on "Pull requests" tab and then "New pull request"
3. Select your fork and the branch with your changes
4. Click "Create pull request"
5. Add a descriptive title and detailed description
6. Reference any related issues by using "#" followed by the issue number
7. Submit the pull request

## Best Practices

### Keeping Your Fork Updated

Regularly sync your fork with the upstream repository:

```bash
# Fetch changes from upstream
git fetch upstream

# Check out your main branch
git checkout main

# Merge upstream changes into your main branch
git merge upstream/main

# Push the updated main to your fork
git push origin main
```

### Before Creating a Pull Request

1. Make sure your code follows the project's style guidelines
2. Write or update tests if required
3. Ensure all tests pass
4. Keep your PR focused on a single issue/feature
5. Rebase your branch if there are conflicts with the main branch:

```bash
git checkout feature/your-feature-name
git pull --rebase upstream main
git push --force origin feature/your-feature-name
```

### Responding to Feedback

1. Make the requested changes on your local branch
2. Commit and push the changes
3. The pull request will update automatically
4. Respond to comments to explain your decisions

### Useful Git Commands

- View commit history: `git log`
- Discard uncommitted changes: `git checkout -- filename` or `git restore filename`
- Temporarily store changes: `git stash` (and `git stash pop` to restore)
- See changes before committing: `git diff`
- Amend the last commit: `git commit --amend`

---

Happy contributing! Remember, it's normal to face challenges when first using Git. Don't hesitate to ask for help or look up commands when you get stuck.
