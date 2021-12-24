# Dotfiles for Nrsimha

For management of dotfiles I am using system used in this post: https://www.atlassian.com/git/tutorials/dotfiles

## Requirements

- Git
- Curl
- zsh (with Oh my zsh)

## Install

### Oh my zsh

First install Oh My Zsh:
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

Install zsh-syntax-highlighting plugin:

    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

and zsh-autosuggestions plugin:

    git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

### Install nvm

    source /usr/share/nvm/init-nvm.sh

### Install virtualenvwrapper

    sudo pacman -Syu python-virtualenvwrapper

    export WORKON_HOME=~/.virtualenvs
    source /usr/bin/virtualenvwrapper.sh

### install dotfiles

Install config tracking in your $HOME by running:

    curl -Lks https://raw.githubusercontent.com/nrsimha/cfg/main/.bin/install.sh | /bin/bash

Add alias for git command:

    alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'

## Others

### Virtualenv

Virtualenv is used for Python projects. Django uses variable which are set in postactivate file. In .virtualenvs/example/postactivate there
is example file which can be used for all new projects.

In project's settings file we can access those variable like this:

    GOOGLE_ANALYTICS = os.environ.get('GOOGLE_ANALYTICS', None)
