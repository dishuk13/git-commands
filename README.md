# git-commands

git-commands are a set of helper utilities over the basic git commands which help automate frequent git actions.

There are two commands, `git switch-branch <branch>` and `git sync`.

## Getting Started

These have just been tested for macOS but it should be possible to make them work for Linux as well with minimal changes.

### Prerequisites

You require `git` of course. You also require `grep` and `cut` but they should already be installed if you're using Linux or macOS.

### Installing

Clone the repo and add the `commands` folder to the system path.

On macOS, you can do so by adding this to your `~/.zprofile`.

```
export PATH="$PATH:/path/to/commands/folder"
```

Now you're good to go. Simply go to any git repo and you should be able to execute the commands `git switch-branch` and `git sync`.

## Usage

1. git switch-branch \<branch>

This is the same as `git switch` with the addition of saving your uncommited changes into a stash and popping them automatically when you switch back.

2. git sync

This pulls origin, rebases current branch on top of "main" branch and then pushes current branch to origin. If there are any conflicts, you need to resolve them and run this command again to finish the process.

Also, you would need to change "main" to something else in `git-sync` if your trunk branch is something other than "main", say develop or master.

## Sublime Merge integration

There is a config for Sublime Merge in the repo called `Default.sublime-commands`. Instruction on how to use that can be found [here](https://www.sublimemerge.com/docs/custom_commands). 

Again, you would need to update the config if the trunk branch is not "main".



