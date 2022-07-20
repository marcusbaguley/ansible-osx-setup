# MacOS Setup with Ansible

This repository contains an Ansible configuration for setting up a Mac from scratch. It's primary purpose is setting up a new Mac from scratch, but I endeavor to also use it for adding new software as I go so that it remains up to date. At the moment it's being used for setting up Intel based Macs running MacOS Big Sur.

## Getting Started

There's a simple shell script in `bin/bootstrap` which will perform the initial steps of:

1. Installing Xcode
2. Installing Ansible
3. Fetching required Ansible roles and collections

Had to add to path and before bootstrap

Set up PATH: `export PATH=$PATH:/Users/marcusbaguley/Library/Python/3.8/bin`
For Docker - run Docker for Mac to complete installation and setup command line tools.
Installation of ruby with asdf - current open ssl issue: https://github.com/openssl/openssl/issues/18720#issuecomment-1185940347

And then runs the main playbook `ansible_osx.yml`.

For future updates, `bin/apply` can be used to run just the Ansible playbook without the setup commands.

## What's installed

The easiest way to understand what's installed is to read the contents of `ansible_osx.yml`, this configuration is fairly specific to the range of development I do personally, but may serve as a useful starting point for others. The core components are:

- ZSH + Oh My Zsh as the primary shell
- Homebrew for package management
- ASDF for version management (along with plugins and default versions for ruby, python, javascript, elixir and erlang)
- Virtualbox, Vagrant and Docker
- VSCode + default plugins and configuration
- A selection of Android SDK's
- Lots of other tools and utilities

## Customising

Everything can be customised by editing `ansible_osx.yml`.
