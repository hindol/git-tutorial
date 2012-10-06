[<- Back to TOC](https://github.com/Hindol/git-tutorial/blob/master/README.md)

# Solving Merge Conflicts
With `git` a merge conflict is not that uncommon. If two people modify the same line and we attempt to merge it, `git` depends on us to _resolve_ the conflict.

Example conflict,

    $ git merge jack\'s-version

> `Updating 3e7b380..9a0aaac`  
> `Fast-forward`  
> ` TEXT |    2 +-`  
> ` 1 file changed, 1 insertion(+), 1 deletion(-)`

    $ git merge rose\'s-version

> `Auto-merging TEXT`  
> `CONFLICT (content): Merge conflict in TEXT`  
> `Automatic merge failed; fix conflicts and then commit the result.`

At this point if you open the file TEXT, you will see something like this,

```
<<<<<<< HEAD
For my knife is bathed in the blood of the brave,
=======
For my dagger is washed in the blood of the brave,
>>>>>>> rose's-version
I come, care-worn tenant of life, from the grave,
Where Innocence sleeps beneath the peace-giving sod,
And the good cease to tremble at Tyranny's nod;
```

Clearly, `For my *knife* is bathed in the blood of the brave,` is Jack's version of the poetry and Rose wrote, `For my *dagger* is washed in the blood of the brave,`. Now, as a conflict resolver, you must decide whose version to keep. You love them both, so you decided to keep both versions. So you manually edit the file to look like,

```
For my knife / dagger is bathed in the blood of the brave,
I come, care-worn tenant of life, from the grave,
Where Innocence sleeps beneath the peace-giving sod,
And the good cease to tremble at Tyranny's nod;
```

Simply commit the changes and you are done.