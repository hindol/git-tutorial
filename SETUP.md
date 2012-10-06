[<- Back to TOC](https://github.com/Hindol/git-tutorial/blob/master/README.md)

# Setup
Every time you save something to a `git` repository, it prepares a list of changes from the previous version and _signs it off with your signature_. In this case your signature is just your name and your (unique) email id. So let us tell `Git` that information.

    $ git config --global user.name "First Last"
    $ git config --global user.email "your.email@provider.whatever"

Also tell `Git` about our proxy servers _just in case_, although it should detect your `$http_proxy` and `$https_proxy` environment variables.

    $ git config --global http.proxy "http://proxyUser:proxyPassword@proxy:proxyPort/"
    $ git config --global https.proxy "http://proxyUser:proxyPassword@proxy:proxyPort/"

## Setting Up Visual Merge / Diff Tools
Meld is a very nice (and free) visual diff / merge tool. A diff tool is a utility that opens two files side-by-side and shows the differences between them. To setup Meld,

    $ sudo apt-get install meld

Now let us _integrate_ it with `Git`.

    $ git config --global diff.tool meld
    $ git config --global merge.tool meld