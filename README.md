# A little baby dotfiles repo

Managed with [rcm][]

## First, install zsh and Homebrew

We'll use the [oh-my-zsh][] project for zsh and install Homebrew as well:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Dotfiles Installation:

Now clone this repo into `~/.dotfiles`, and install [rcm][]::

```
git clone https://github.com/tinystride/dotfiles .dotfiles
brew tap thoughtbot/formulae
brew install rcm
```

Install the .rcrc file so rcm has configuration to run:

```
rcup rcrc
```

Now do a dry run to see which files will be symlinked:

```
lsrc
```

If you're satisfied with the dry run, install the dotfiles on your system:

```
rcup
```

## Install brew casks

```
brew bundle install
```

## Install Vim plugins, nvm, and rvm

- Follow instructions to install [Vundle][]
- Follow instructions to install [nvm][]

## Set up key mapping:

Install these applications before proceeding:

- [Karabiner-Elements][] *custom key mapping*
- [Hammerspoon][]

### Configure key mapping settings:

- Karabiner-Elements > Simple Modifications > caps_lock to key f18
- Hammerspoon > Reload Config to load the config that was auto-installed
during dotfiles installation

Key mapping setup should be complete!

### Personalize teriminals 

- Install /assets/Meslo LG M Regular for Powerline.ttf
- Install /assets/Solarized Dark - Patched.itermcolors

Instructions for iTerm at <https://gist.github.com/kevin-smets/8568070> 
Instructions for VSCode at <https://gist.github.com/480/3b41f449686a089f34edb45d00672f28>

### Personalize Alfred

- Install my custom macOS Dark Alfred theme: <https://www.alfredapp.com/extras/theme/JOEIP0l4M9/>

## Adding new files to the project

```
mkrc ~/.filename
```

**Examples:**

```
mkrc ~/.vimrc
mkrc ~/.atom/config.cson  # Nested files also work
mkrc ~/.vim  # And entire directories work too
```

The specified file will be moved to the `~/.dotfiles` directory with the
dot prefix removed. The original file will be deleted,
then symlinked from `~/.dotfiles` back to its original location.
It will now stay in sync and be easily managed with source control.

## Features

- Editor: [vim][] and [Visual Studio Code][]
- Shell: [zsh][]
- Source Control: [git][]

[oh-my-zsh]: https://github.com/robbyrussell/oh-my-zsh
[rcm]: https://github.com/thoughtbot/rcm
[vim]: http://www.vim.org
[Visual Studio Code]: https://code.visualstudio.com/  
[zsh]: http://www.zsh.org
[git]: http://git-scm.com
[iTerm2]: https://www.iterm2.com/
[Atom]: https://atom.io/
[Vundle]: https://github.com/VundleVim/Vundle.vim
[Karabiner-Elements]: https://github.com/tekezo/Karabiner-Elements
[Hammerspoon]: http://www.hammerspoon.org/
[nvm]: https://github.com/creationix/nvm
