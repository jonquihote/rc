## Requirements

Set zsh as your login shell:

    chsh -s $(which zsh)

## Install

Clone onto your laptop:

    git clone git@github.com:jonquihote/rc.git ~/.rc

(Or, [fork and keep your fork updated](http://robots.thoughtbot.com/keeping-a-github-fork-updated)).

Install [rcm](https://github.com/thoughtbot/rcm):

    brew install rcm

Install the dotfiles:

    env RCRC=$HOME/.rc/rcrc rcup

After the initial installation, you can run `rcup` without the one-time variable
`RCRC` being set (`rcup` will symlink the repo's `rcrc` to `~/.rcrc` for future
runs of `rcup`). [See example](https://github.com/thoughtbot/dotfiles/blob/master/rcrc).

This command will create symlinks for config files in your home directory.
Setting the `RCRC` environment variable tells `rcup` to use standard
configuration options:

-   Exclude the `README.md`, and `LICENSE` files, which are part of
    the `rc` repository but do not need to be symlinked in.
-   Give precedence to personal overrides which by default are placed in
    `~/.rc-local`
-   Please configure the `rcrc` file if you'd like to make personal
    overrides in a different directory

## Update

From time to time you should pull down any updates to these dotfiles, and run

    rcup

to link any new files and install new vim plugins. **Note** You _must_ run
`rcup` after pulling to ensure that all files in plugins are properly installed,
but you can safely run `rcup` multiple times so update early and update often!

## Make your own customizations

Create a directory for your personal customizations:

    mkdir ~/.rc-local

Put your customizations in `~/.rc-local` appended with `.local`:

-   `~/.rc-local/gitconfig.local`
-   `~/.rc-local/zshrc.local`

Your `~/.rc-local/gitconfig.local` might look like this:

    [user]
      name = Joni Chandra
      email = jonquihote@gmail.com
