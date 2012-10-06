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

We are now going to _jump_ to the newly created branch (don't forget the whooping and screeching, (; ).

> You can anytime go back to the `master` branch by typing `$ git checkout master` and continue where you left off. ___Commiting to one branch does not change the contents of another branch___.

    $ git checkout better-primality-test

> `Switched to branch 'better-primality-test'`

Modify `prime.cpp` to look like this,

```c++
#include <cmath>
#include <iostream>

bool IsPrime(int n)
{
    int sqrtN = static_cast<int>(
                    std::ceil( std::sqrt(n) )
                );
    for (int i = 2; i <= sqrtN; ++i)
    {
        if (n % i == 0)
            return false;
    }
    return true;
}

int main()
{
    std::cout << "Hello world!" << std::endl;
    return 0;
}
```

Commit our changes as usual,

    $ git commit prime.cpp -m 'Implemented a better primality test'

> `[better-primality-test 272871e] Implemented a better primality test`  
> ` 1 file changed, 5 insertions(+), 1 deletion(-)`

Now, since you are _happy_ with the changes you have made, let's ___merge better-primality-test___ into master.

    $ git checkout master
    $ git merge better-primality-test

> `Updating 9faebab..272871e`  
> `Fast-forward`  
> ` prime.cpp |    6 +++++-`  
> ` 1 file changed, 5 insertions(+), 1 deletion(-)`

Since the branch `better-primality-test` has served its purpose,

    $ git branch -d better-primality-test

> `Deleted branch better-primality-test (was 272871e).`

> During merging, you may occassionaly end up with a _merge conflict_. Fear not, merge conflicts are discussed in the next chapter.

That's it! You are now a master of branching and merging.