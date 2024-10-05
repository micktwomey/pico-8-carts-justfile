# PICO-8 Carts Justfile

Keeping hold of PICO-8 source code using [just](https://just.systems/).


# Setup

1. Install [PICO-8](https://www.lexaloffle.com/pico-8.php) and make sure it runs
2. Install [just](https://just.systems/)
   1. For mac users `brew install just` will do the trick


## Setting up your repo

1. Pick a git repo you'll track your carts in
2. Create a `justfile` with the following:

```sh
import? 'pico-8-carts.just'

help:
  just --list

# Fetch pico-8-carts.just
fetch:
  curl https://raw.githubusercontent.com/micktwomey/pico-8-carts-justfile/refs/heads/main/justfile > pico-8-carts.just
```

Run `just fetch` once to fetch the code (you can git commit it later if you want).

Use `just --list` to see what commands are available.

Technique from [remote justfiles](https://just.systems/man/en/remote-justfiles.html) help page.

## Importing your carts for the first time

1. Run `just fetch` to fetch the justfile (only need to do this once or to update)
2. Run `just import`
3. Use `git add` and `git commit` as normal to commit them

Note: the `demos` folder is git ignored as this is usually installed using `install_demos` inside PICO-8

## Exporting carts to PICO-8

1. Run `just fetch` to fetch the justfile (only need to do this once or to update)
2. Run `just export`

# Workflows

## Workflow 1: Editing in Pico-8

This also covers editing carts directly in the carts folder

1. Edit and develop in Pico-8 as normal
2. Bonus: `just vscode` will open vscode with the carts folder, so you can edit in there.
   - Recommended extension: [pico8-ls](https://marketplace.visualstudio.com/items?itemName=PollywogGames.pico8-ls). You can install this using `just vscode-install-extensions`.
3. Use `just import` to bring in your carts
4. `git add` and `git commit` as normal
