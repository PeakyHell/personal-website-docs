# Table of Contents
1. [Introduction](#introduction)
2. [Installing Git](#installing-git)
3. [Setting up a remote repository](#setting-up-a-remote-repository)
===ENDTOC===

# Introduction

In this documentation, GitHub will be used to talk about remote Git platforms like GitHub/GitLab/... for ease.

# Installing Git

Git can easily be installed with only one command.

## For Linux

```bash
sudo apt install git-all
```

## For MacOs

```bash
brew install git
```

# Setting up a remote repository

## Create a remote repository platform account

Go to a remote repository website like [GitHub](https://github.com), [GitLab](https://gitlab.com), ... and create an account.

Once your account is created you will then need to setup an SSH key to easily interact with your remote repositories.

## Generate an SSH key

Open Terminal and generate an SSH key with your email. The -f flag allows to rename the file where the key will be stored, this is optional.

You will then be asked to enter an optional passphrase.

```bash
ssh-keygen -t ed25519 -C "your_mail@example.com" -f ~/.ssh/id_ed25519_keyname
```

## Add the key to the ssh-agent

Start the ssh-agent in the background.

```bash
eval "$(ssh-agent -s)"
```

### For MacOs only
Once the agent is started, edit the ~/.ssh/config file to automatically load keys into the ssh-agent and store passphrases in the keychain :

If the ~/.ssh/config file doesn't exist, create it with :

```bash
touch ~/.ssh/config
```

Add the host to the ~/.ssh/config file by writing this into it. Replace github.com by the remote repository host you use if needed and the IdentityFile variable by the name of your key file if you changed it.

```bash
Host github.com
    AddKeysToAgent yes
    UseKeychain yes
    IdentityFile ~/.ssh/id_ed25519
```

---

Add the private key to the ssh-agent, the --apple-use-keychain flag is for Mac users only.
Edit the file name if you changed it when you created your key.

```bash
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

## Get the public key to add it to GitHub

You will now need to add your SSH key to your GitHub account to be able to use it.
First, copy your *public* key. You will then need to add it to your account.
Once again, if you edited the name of you key file, don't forget to change it in the command.

```bash
cat ~/.ssh/id_ed25519.pub
```

## Create the repository

Once your ssh key is linked with your GitHub account you have two ways to create a repository that will be tracked on GitHub.

### GitHub -> Local

The first way is to create a repository on GitHub, get the SSH link and clone it locally.

```bash
git clone link
```

### Local -> GitHub

The second way is to create a local repository and add it on GitHub.
You will first have to create an *empty* repository on GitHub and get its link.

Create your local repo.

```bash
git init
```

Add your files to your local repo. If you don't want to add *all* the files, you can specify their names one by one instead of the dot.

```bash
git add .
```

Once added, you can then commit your files.

```bash
git commit -m "First commit"
```

You can now link your local repo to your GitHub repo with the link you previously got.

```bash
git remote add origin link
```

Now that your repositories are linked, you can push to your GitHub repo.

```bash
git push origin main
```

Or you can also set an upstream branch to be able to use git push only without needing to specify the branch every time.

```bash
git push --set-upstream origin main
```

# Basic Snapshotting

## add

## status

## diff

## commit

## notes

## restore

## reset

## rm

## mv

# Branching and Merging

## branch

## checkout

## switch

## merge

### fast-forward merge

> A fast-forward merge is when you merge a remote commit and you haven't done any local commit in the meantime so the remote commit just moves the branch pointer forward.

### --ff

By default merge will use this option

Using --ff with git merge will make a fast-forward merge.  

```
local : A --- B

remote : A --- B --- C
```

```bash
git merge --ff
```

```
local : A --- B --- C

remote : A --- B --- C
```

If you had local commits, it'll create a merge commit.

```
local : A --- B --- C

remote : A --- B --- D
```

```bash
git merge --ff
```

```
local : A --- B --- C --- E
			   \         /
				--- D ---

remote : A --- B --- C
```

### --ff-only

Using --ff-only with git merge will make a fast-forward merge.

```
local : A --- B

remote : A --- B --- C
```

```bash
git merge --ff-only
```

```
local : A --- B --- C

remote : A --- B --- C
```

If you had local commits, instead of making a merge commit, the merging will stop.

```
local : A --- B --- C

remote : A --- B --- D
```

```bash
git merge --ff-only
```

```
local : A --- B --- C --- /

remote : A --- B --- D
```

## mergetool

## log

## stash

## tag

## worktree

# Sharing and Updating Projects

## fetch

git fetch downloads commits made on the remote repository but does not incorporate them into your local repository.

## pull

git pull is equivalent to git fetch + git merge, so the command is gonna download the commits from the remote branch and then directly merge them with your local branch. 

```bash
git pull
# Equivalent to :
git fetch + git merge
```

You can also modify the behavior of git pull by using these different flags.

### --rebase

 The --rebase flag or the git.rebase config set to True will rebase instead of merge.

```bash
git pull --rebase
# or
git config set pull.rebase True
git pull
# Equivalent to :
git fetch + git rebase
```

### --ff

The --ff flag will make a fast-forward merge if possible, else it will make a merge commit.

```bash
git pull --ff
# Equivalent to :
git fetch + git merge --ff
```

### --ff-only

The --ff-only flag will make a fast-forward merge if possible, else it will stop the merge operation.

```bash
git pull --ff-only
# Equivalent to :
git fetch + git merge --ff-only
```

## push

## remote

## submodule

# Inspection and Comparison

## show

## log

## diff

## difftool

## range-diff

## shortlog

## describe

# Patching

## apply

## cherry-pick

## diff

## rebase

If you fetch new remote commits but already had local commits you can use rebase to do the following :
- stash your local commit
- incorporate the remote commit
- replay your local commit on top of the remote commit

```
local : A --- B --- C

remote : A --- B --- D
```

```bash
git fetch
```

```
local : A --- B --- C
			   \
			    --- D (remote branch)
```

```bash
git rebase
```

```
local : A --- B --- D --- C'
```

## revert

# Debugging

## bisect

## blame

## grep

# Email