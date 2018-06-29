# My Sublime Text Config
This repo is to sync my Sublime Text 3.x config between my home desktop, my work desktop, and my laptop(s).

## Installation

1. Make sure [Package Control](https://packagecontrol.io/installation) is installed, then close Sublime Text.
2. Open your CLI and navigate to `cd %APPDATA%/Sublime Text 3/Packages/User`
3. `git init`
4. `git remote add origin https://github.com/joelcollyer/sublime-text-config.git`
5. `git fetch origin`
6. `git pull origin master`


## Retaining Local Config

If you have packages and preferences you want to retain, I found the best way is to do the following:

1. Make a backup of the contents in your User folder (but not the folder itself or you'll overwrite/delete the .git directory).
2. Initialize the git repo (as described above).
3. Reset your local files to those from the `master` branch:
    ```
    git reset --hard origin/master
    ```
4. Create a new branch for the machine you're on (i.e. `laptop` or `home-desktop`).
5. Restore your original config files.
6. Initiate a merge, but don't fast forward to your local config:
```
git merge --no-ff --no-commit YourNewBranchName
```
7. Cherry pick which parts of the merged files you want to keep, being careful not to create invalid json settings (missing brackets or commas), and delete the files that are not longer necessary.
8. Once you're happy with the merged data, commit your changes!
