# git-cola: The highly caffeinated Git GUI

    git-cola is a powerful Git GUI with a slick and intuitive user interface.

    Copyright (C) 2007-2015, David Aguilar and contributors

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

## SCREENSHOTS

Screenshots are available on the
[git-cola screenshots page](https://git-cola.github.io/screenshots.html).

## DOWNLOAD

    apt-get install git-cola python-pyinotify

New releases are available on the
[git-cola download page](https://git-cola.github.io/downloads.html).

## FORK

    git clone git://github.com/git-cola/git-cola.git

[git-cola on github](https://github.com/git-cola/git-cola)

[git-cola google group](http://groups.google.com/group/git-cola/)


# NUTRITIONAL FACTS


## ACTIVE INGREDIENTS

* [git](http://git-scm.com/) 1.6.3 or newer.

* [Python](http://python.org/) 2.6, 2.7, and 3.2 or newer.

* [PyQt4](http://www.riverbankcomputing.co.uk/software/pyqt/download) 4.4 or newer

* [argparse](https://pypi.python.org/pypi/argparse) 1.1 or newer.
  argparse is part of the stdlib in Python 2.7; install argparse separately if
  you are running on Python 2.6.

## ADDITIVES

*git-cola* enables additional features when the following
Python modules are installed.

[pyinotify](https://github.com/seb-m/pyinotify) 0.7.1 or newer
enables inotify support on Linux.

[send2trash](https://github.com/hsoft/send2trash) enables cross-platform
"Send to Trash" functionality.

# BREWING INSTRUCTIONS

## RUN FROM SOURCE

You don't need to install *git-cola* to run it.
Running *git-cola* from its source tree is the easiest
way to try the latest version.

    git clone git://github.com/git-cola/git-cola.git
    cd git-cola
    ./bin/git-cola
    ./bin/git-dag

Having *git-cola*'s *bin/* directory in your path allows you to run
*git-cola* like a built-in Git command:

    PATH=$PWD/bin:"$PATH"
    export PATH
    git cola
    git dag

# INSTALLATION

Normally you can just do "make install" to install *git-cola*
in your `$HOME` directory (`$HOME/bin`, `$HOME/share`, etc).
If you want to do a global install you can do

    make prefix=/usr install

There are also platform-specific installation methods.
You'll probably want to use one of these anyways since they
have a nice side-effect of installing *git-cola*'s PyQt4
and argparse dependencies.

## LINUX

Linux is it! Your distro has probably already packaged git-cola.
If not, please file a bug against your distribution ;-)

### arch

    yaourt -S git-cola

### debian, ubuntu

    apt-get install git-cola

### fedora

    yum install git-cola

### gentoo

    emerge git-cola

### opensuse

Use the [one-click install link](http://software.opensuse.org/package/git-cola).

## MAC OS X

[Homebrew](http://mxcl.github.com/homebrew/) is the easiest way to install
git-cola, *Qt4* and *PyQt4*.

    brew install git-cola

Once brew has installed git-cola you can:

1. Clone git-cola

    `git clone git://github.com/git-cola/git-cola.git && cd git-cola`

2. Build the git-cola.app application bundle

    `make git-cola.app`

3. Copy it to _/Applications_

    `rm -fr /Application/git-cola.app && cp -r git-cola.app /Applications`

## WINDOWS INSTALLATION

Download the latest stable Git, Python 2.x, and Py2x-PyQt4 installers

* [msysGit](http://msysgit.github.com/)

* [Python](http://python.org/download/)

* [PyQt](http://www.riverbankcomputing.co.uk/software/pyqt/download/)

* [git-cola Installer](https://github.com/git-cola/git-cola/downloads)

Once these are installed you can run *git-cola* from the Start menu or
by double-clicking on the `git-cola.pyw` script.

If you are developing *git-cola* on Windows you can use `python.exe` to run
*git-cola* directly from source.

    python.exe ./bin/git-cola

If you want to build the `git-cola Installer` yourself run the provided script

    ./contrib/win32/create-installer.sh

You have to make sure that the file */share/InnoSetup/ISCC.exe* exists.
That is normally the case when you run the *msysGit bash* and not the
*Git for Windows bash* (look [here](http://msysgit.github.com/) for the differences).

# DOCUMENTATION

* [HTML documentation](https://git-cola.readthedocs.org/en/latest/)

* [git-cola manual](share/doc/git-cola/git-cola.rst)

* [git-dag manual](share/doc/git-cola/git-dag.rst)

* [Keyboard shortcuts](https://git-cola.github.io/share/doc/git-cola/hotkeys.html)

* [Contributing guidelines](CONTRIBUTING.md)

# GOODIES

*git-cola* ships with an interactive rebase editor called *git-xbase*.
*git-xbase* can be used to reorder and choose commits and is typically
launched through the *git-cola*'s "Rebase" menu.

*git-xbase* can also be launched independently of the main *git-cola* interface
by telling `git rebase` to use it as its editor:

    GIT_SEQUENCE_EDITOR=$PWD/share/git-cola/bin/git-xbase git rebase -i origin/master

You can also launch *git-xbase* via the *git-cola* rebase sub-command
(as well as various other sub-commands):

    ./bin/git-cola rebase origin/master

# COMMAND-LINE TOOLS

The *git-cola* command exposes various sub-commands that allow you to quickly
launch tools that are available from within the *git-cola* interface.
For example, `./bin/git-cola find` launches the file finder,
and `./bin/git-cola grep` launches the grep tool.

See `./bin/git-cola --help-commands` for the full list of commands.

    $ ./bin/git-cola --help-commands
    usage: git-cola [-h]
    
                    {cola,am,archive,branch,browse,classic,config,
                     dag,diff,fetch,find,grep,merge,pull,push,
                     rebase,remote,search,stash,tag,version}
                    ...
    
    valid commands:
      {cola,am,archive,branch,browse,classic,config,
       dag,diff,fetch,find,grep,merge,pull,push,
       rebase,remote,search,stash,tag,version}

        cola                start git-cola
        am                  apply patches using "git am"
        archive             save an archive
        branch              create a branch
        browse              browse repository
        classic             browse repository
        config              edit configuration
        dag                 start git-dag
        diff                view diffs
        fetch               fetch remotes
        find                find files
        grep                grep source
        merge               merge branches
        pull                pull remote branches
        push                push remote branches
        rebase              interactive rebase
        remote              edit remotes
        search              search commits
        stash               stash and unstash changes
        tag                 create tags
        version             print the version
