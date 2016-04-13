# Edit the last commit

You can edit the last commit with the `--amend` option:

```sh
git commit --amend -m "New commit message"
```

If you've already pushed your commit up to your remote branch, then you'll need to force push the commit with:

```sh
git push <remote> <branch> --force
```

## References

- [Amending the most recent commit message](http://stackoverflow.com/a/179147)
