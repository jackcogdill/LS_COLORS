### Table of contents
* [LS_COLORS](#ls_colors)
* [What does it look like?](#what-does-it-look-like)
* [Installation](#installation)
  * [Arch Linux](#arch-linux)
  * [Zsh plugin manager](#zsh-plugin-manager)
  * [Zsh syntax highlighting](#zsh-syntax-highlighting)
  * [fish shell](#fish-shell)
* [Information for Developers](#information-for-developers)
* [Legal](#legal)

# LS_COLORS
This is a collection of extension:color mappings, suitable to use as your
`LS_COLORS` environment variable. Most of them use the extended color map,
described in the ECMA-48 document; in other words, you'll need a terminal
with capabilities of displaying 256 colors.

As of this writing, around 300 different filetypes/extensions is supported.
That's indeed a lot of extensions, but there's a lot more! Your help is greatly
appreciated.

Fork this project on github, add the extensions you are missing, and send a pull
request.

Some guidelines:

For files that usually ends up next to each other, like html, css and js,
try to pick colors that fits in nicely together. Filetypes with multiple
possible extensions, like htm and html, should have the same color.

# What does it look like?
Here's a screenshot _(font and minor color shades, of course, depend on terminal and its configuration)_:

![Screenshot1](http://orig07.deviantart.net/f59a/f/2016/087/a/e/ls_colors_1_by_trapd00r-d9wrdoa.png)

And another one:

![Screenshot2](http://orig02.deviantart.net/5c73/f/2016/087/4/8/ls_colors_2_by_trapd00r-d9wrdrq.png)

  [0]: https://github.com/trapd00r/zsh-syntax-highlighting-filetypes
  [1]: https://github.com/trapd00r/File-LsColor
  [2]: https://github.com/trapd00r/File-LsColor/tree/master/bin
  [3]: https://aur.archlinux.org/packages/lscolors-git

# Installation
To install and use this file, put something like this in your shell resource
file:
```shell
eval $( dircolors -b $HOME/.dircolors )
```

A quick way to install would be the following set of commands (assuming bash):

```shell
wget https://raw.github.com/trapd00r/LS_COLORS/master/LS_COLORS -O $HOME/.dircolors
echo 'eval $(dircolors -b $HOME/.dircolors)' >> $HOME/.bashrc
. $HOME/.bashrc
```

## Arch Linux
Arch Linux users can install the [`lscolors-git`][3] package from the AUR for easy
integration with bash, csh, or zsh.

## Zsh plugin manager

When using a plugin manager, make sure that `dircolors` is only run once per
install/update.

Sample commands to use on  
install/update: `dircolors -b LS_COLORS > c.zsh`  
load: `source c.zsh`

## Zsh syntax highlighting
[zsh-syntax-highlighting-filetypes][0] highlights file on the command-line in
realtime, using these colors.

## fish shell
```fish
eval ( dircolors --c-shell $HOME/.dircolors)
```

Place it in `~/.config/fish/config.fish` or any `*.fish*` file inside `~/.config/fish/conf.d/` to be loaded.

# Information for Developers
There's a [library][1] I've written that lets you use various LS COLORS on
arbitrary files and directories. A simple implementation can be found [here][2].

Using this, you can do
```shell
find $HOME -maxdepth 1  | ls_color

mpc search artist Laleh | ls_color
```

... and so on.

# Legal 
© Copyright 2014-2018 Magnus Woldrich.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.  See the Perl Artistic License for more details.

This program is free software: you can redistribute it and/or modify it under
the terms of the Perl Artistic License as published by the Perl Foundation,
either version 1.0 of the License, or (at your option) any later version.

You should have received a copy of the Perl Artistic License along
with this program.  If not, see <http://www.perlfoundation.org/artistic_license_1_0>.
