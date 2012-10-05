# Installation
Installing `git` is as simple as running,

    $ sudo apt-get install git-core git-doc git-gui

I frequently use `gitg` in this tutorial. To install `gitg`,

    $ sudo apt-get install gitg

## Getting `apt-get` to Work Behind Proxy
Set up `$http_proxy` and `$https_proxy` environment variables either in `~/.bashrc` or `~/.profile` by adding the following lines,

    $ cat - >> ~/.profile
    export http_proxy="http://proxyUser:proxyPassword@proxy:proxyPort/"
    export https_proxy="http://proxyUser:proxyPassword@proxy:proxyPort/"

Terminate your input with `CTRL+D`.

To make sure proxy works in `sudo` environment too, just type,

    $ sudo visudo

Add a line to it so that it matches the following,

    ...
    Defaults        env_reset
    Defaults        env_keep+="http_proxy https_proxy ftp_proxy no_proxy"
    ...

Reboot your system.