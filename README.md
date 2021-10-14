# Dotfiles for [@Nrsimha](https://vedabase.io/en/)

For management of dotfiles I am using same system used in this post: https://www.atlassian.com/git/tutorials/dotfiles

## Requirements

- Git

## Install

Clone this repository in ~/cfg directory.

Add following line in .zshrc file:

`alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'`

