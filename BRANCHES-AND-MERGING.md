[<- Back to TOC](https://github.com/Hindol/git-tutorial/blob/master/README.md)

# Branches and Merging
Lessons learned! No copying this time. You have your very own `IsPrime()` function in place.

```c++
bool IsPrime(int n)
{
    for (int i = 2; i < n; ++i)
    {
        if (n % i == 0)
            return false;
    }
    return true;
}
```

But you know that any composite number must have [at least one factor that is less than or equal to its square root](http://stackoverflow.com/q/5811151/1019491). So let's improve on our code. We'll use a trick here. We'll leave the `master` branch untouched. `master` branch is the branch that is created by `git` automatically. To list all the branches,

    $ git branch

> `* master`

The _starred_ branch is the branch you are on. Let's create a new branch,

    $ git branch better-primality-test
    $ git branch

> `  better-primality-test`  
> `* master`

We are now going to _jump_ to the newly created branch (Don't forget the whooping and screeching, (; ).

    $ git checkout better-primality-test