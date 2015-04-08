Latpot
======

Latpot is a script to set up an OS X laptop for PHP web development.

It can be run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

Requirements
------------

It supports:

* [OS X Yosemite (10.10)](https://www.apple.com/osx/)

Older versions may work but aren't regularly tested. Bug reports for older
versions are welcome.

Install
-------

Download, review, then execute the script:

```sh
curl --remote-name https://raw.githubusercontent.com/40digits/latpot/master/mac
less mac
sh mac 2>&1 | tee ~/latpot.log
```

Debugging
---------

Your last Latpot run will be saved to `~/latpot.log`. Read through it to see if
you can debug the issue yourself. If not, copy the lines where the script
failed into a [new GitHub
Issue](https://github.com/40digits/latpot/issues/new) for us. Or, attach the
whole log file as an attachment.

What it sets up
---------------

* [Homebrew] and [Cask] for managing operating system libraries
* [Git] for source control management
* [Cairo] for image manipulation
* [Node.js] and [NPM], for running apps and installing JavaScript packages
* [Apache] for serving web requests
* [MySQL] for all your database needs

[Homebrew]: http://brew.sh/
[Git]: http://git-scm.com/
[Cairo]: http://cairographics.org/
[Node.js]: http://nodejs.org/
[NPM]: https://www.npmjs.org/
[Apache]: http://httpd.apache.org/
[MySQL]: https://www.mysql.com/

It should take less than 15 minutes to install (depends on your machine).

Customize in `~/.latpot.local`
------------------------------

Your `~/.latpot.local` is run at the end of the Latpot script.
Put your customizations there.
For example:

We have provided a common [latpot.local] file. Just delete what you don't want to use.

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Latpot functions such as `fancy_echo`,
`brew_install_or_upgrade`, and
`brew_cask_install_or_update`
can be used in your `~/.latpot.local`.

Credit
-------

This is a fork of the original [Laptop] repo created by Thoughtbot, Inc
It is free software,
and may be redistributed under the terms specified in the [LICENSE] file.

[LICENSE]: LICENSE
[Laptop]: https://github.com/thoughtbot/laptop/blob/master/README.md
