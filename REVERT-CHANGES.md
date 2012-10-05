[<- Back to TOC](https://github.com/Hindol/git-tutorial/blob/master/README.md)

# Revert Changes
Hopefully you have not forgotten about your assignment from the last chapter. But who wants to do an assignment? (Not me at least.) Luckily, you have a friend who has already done it. Let's copy his assignment.

```c++
bool CopiedIsPrime(int n)
{
    for (int i = 2; i < n; ++i)
    {
        if (n % i == 0)
            return false;
    }
    return true;
}
```

Paste this function just before `int main()`. Commit your changes,

    $ git commit prime.cpp -m 'Borrowed IsPrime() from a friend (don't tell the teacher)'

> Note that `git add` is not required here since we are explicitly mentioning the name of the file we want to commit.

That's it. An assignment well done!

Well, not quite...
Unfortunately for you, your teacher is also a frequent visitor of GitHub and he sees your commit message. Now he is really angry. He screams, "Either you do it yourself or I will fail you." So you type,

    $ git reflog

> `4c29248 HEAD@{0}: commit: Borrowed IsPrime() from a friend (don't tell the teacher)`
> `974dbe5 HEAD@{1}: commit (initial): First version`

You want to go back to the commit `974dbe5`.

    $ git reset --hard HEAD@{1}

> `HEAD is now at 974dbe5 First version`

> The `--hard` part is to essentially tell `git` to ___permanently destroy___ all the changes made after commit `974dbe5`. It is also possible to do a `--soft` reset.