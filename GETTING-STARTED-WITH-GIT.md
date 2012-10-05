[<- Back to TOC](https://github.com/Hindol/git-tutorial/blob/master/README.md)

# Getting Started with Git
Let us create an _empty_ `git` repository. It is analogous to buying a bookshelf but you don't have any books in it, yet.

    $ mkdir prime
    $ cd prime
    $ git init

> `Initialized empty Git repository in git-tutorial/examples/prime/.git/`

## Create Content
Let us say, you are asked to write a prime number checker in C++ by your teacher. So we are going to create a bare-bones C++ file called `prime.cpp`.

Create a file named `prime.cpp` inside your prime directory and paste the following,

    #include <iostream>

    int main()
    {
        std::cout << "Hello world!" << std::endl;
        return 0;
    }

You have read somewhere that the recommended way to work with `git` is ___commit early, commit often___. So you are thinking, "this might be a good time to take a snapshot of my file and put it in the repository." Let's do that.

    $ git add prime.cpp
    $ git commit -m 'First version'

Well, to be honest, commit messages like `First version` is okay only for... err, the first version only. Typically you'd want something descriptive (yet fits in a single line) like `Implemented IsPrime(), a primality testing function'. It is important because it tells you what changes a particular commit contains. It also shows up on GitHub,

![GitHub Commit Message](https://raw.github.com/Hindol/git-tutorial/master/images/commit-message.png "GitHub Commit Message")