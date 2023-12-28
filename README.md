# Automatic Git Status Update Script

## Overview

This repository contains a convenient script designed to automate Git status updates whenever you navigate to a different directory using the `cd` command. Stay informed about the latest changes in your project and never forget to pull new updates again!

## How it Works

The script comprises two essential functions:

1. **`git_status()`**: Checks if the current directory is a Git repository and displays the Git status if applicable. This function ensures you receive timely updates on your project.

2. **`cd()`**: Overrides the built-in `cd` command. After changing the directory, it automatically calls `git_status()`, providing an immediate Git status update with each directory change.

## Installation

Follow these steps to set up the automatic Git status update script:

1. **Copy the Script**: Copy the script provided above.

2. **Paste into Shell Profile**:
   - Open your shell profile file (e.g., `.bashrc` for Bash or `.zshrc` for Zsh).
   - Paste the script at the end of the file.

3. **Save and Reload**:
   - Save the changes to your shell profile file.
   - Reload the shell or restart your terminal to apply the changes.

4. **Enjoy Automatic Git Status Updates**:
   - From now on, every time you use the `cd` command to navigate to a different directory, the script will automatically check and display the Git status.

## Script

```bash
git_status() {
    if [ -d .git ] || git rev-parse --git-dir > /dev/null 2>&1; then
        git status
    fi
}

cd() {
    builtin cd "$@" && git_status
}
```

Now, every time you change directories, you'll receive automatic Git status updates, helping you stay informed and ensuring that you never miss the latest changes in your project. 🚀