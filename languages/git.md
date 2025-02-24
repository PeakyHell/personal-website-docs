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