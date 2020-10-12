---
layout: post
title: "Setting Up Shop"
---

# Setting Up Shop

Author: ...Paul

I got a new Macbook Pro over the weekend, so today's the day I start setting
it up with all the configs and whatnot I've been used to using on other
Macbooks I had at work.  You'd think I'd remember all this stuff by now, but
nope -- always tripping over something I forgot to add.

We're building out an Elixir app, so some of this stuff is obviously going to
be specific to Elixir development, but a bunch of other things might still be
useful to people as a checklist of new environment things to do...

### Xcode

Go to the App Store and download Xcode.  Might as well get the whole thing,
although you'll get the command line utilities downloaded from the other steps
later, you might as well get the whole package and then you can know when you
need to update it.

### iTerm2

Mac Terminal is okay, but [iTerm2](https://www.iterm2.com/) is where it's at.
Two options I go look for immediately is the option to use 'focus follows
mouse' (my preference) and then the option to re-use the current working
directory when launching a new window.  That's a lifesaver when you're working
down deep in a directory tree.

### Homebrew

Probably step number 1, install [Homebrew](https://brew.sh/).  Being more of a
Linux console jockey than a Mac fan, this is a must-have for me.  The first
package I install is `postgresql` as my database of choice.  Don't forget after
installing it to use the brew command to start the service (and start it on 
every bootup).

### Kiex

Working with Elixir (and coming from Ruby where `rvm` was a great way to manage Ruby installs), [Kiex](https://github.com/taylor/kiex) is the way to go.  This
will use brew to install Erlang, too, so double-win.

### Vim Stuff

I'm a vi fan, so that's where I start.  Fortunately, the Mac already has a good
vim install, so that's all done.  Next is some config.

* [vim-plug](https://github.com/junegunn/vim-plug) to easily add packages
* Then, use that to install [vim-elixir](https://github.com/elixir-editors/vim-elixir) for syntax highlighting
* Edit your `~/.vimrc`:

```
syntax on
colorscheme elflord
se ts=4

call plug#begin('~/.vim/plugged')
Plug 'elixir-editors/vim-elixir'
call plug#end()
```

Open vim and run the command `PlugInstall` to install the plugin, exit and
the next time you open the app you should be presented with pleasing colors
on your Elixir code (and HTML, and Markdown)...

### Git Stuff

OS X comes with git out of the box, so no problem there.  Of course, there's
always something to remember to do, like editing your `~/.gitconfig` file.
Update your name/email to match your desires.  I'm not a big alias fan, but
there's one I do use:

```
[alias]
  co = checkout
```

So much easier to type `co`!

Also, remember to set up your keys.  Use `ssh-keygen` to create a new `id_rsa`
pair, and then copy the `~/.ssh/id_rsa.pub` contents to your account on Github
as a new key.  TIL there's a shortcut for copying a file to the clipboard:

```
pbcopy < ~/.ssh/id_rsa.pub
```

Definitely going to remember that trick going forward.

### Other Super Useful Apps

Other stuff I've needed even in the first day:

* [GIMP](https://www.gimp.org/downloads/) for tweaking images
* [CloudApp](https://www.getcloudapp.com/) for screen shots & sharing
* [Slack](https://slack.com/) for asking questions on the elixir-lang.slack.com
