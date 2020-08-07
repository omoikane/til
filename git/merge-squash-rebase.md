# What is the difference between merge, squash and rebase in GIT

Let's start by the following example:

![](https://i.stack.imgur.com/1bRnI.png)

Now we have 3 options to merge changes of **feature branch** into **master branch**:

1. **Merge commits**<br>
   Will keep all commits history of the **feature branch** and move them into the **master branch**.<br>
   Will add extra dummy commit.
2. **Rebase and merge**<br>
   Will append all commits history of the **feature branch** in the front of the **master branch**<br>
   Will NOT add extra dummy commit.
3. **Squash and merge**<br>
   Will group all **feature branch** commits into one commit then append it in the front of the **master branch**<br>
   Will add extra dummy commit.

You can find below how the master branch will look after each one of them.

![](https://i.stack.imgur.com/hUtiB.png)

In all cases:<br>
We can safely DELETE the **feature branch**.

## References

- [Reply](https://stackoverflow.com/a/58608571) to [In git, what is the difference between merge --squash and rebase?](https://stackoverflow.com/q/2427238)
