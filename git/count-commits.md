# Count the commits in a repository

Simply type:

```sh
git rev-list --count HEAD
```

You can specify a revision:

```sh
git rev-list --count <revision>
```

Or get the commit count across all branches:

```sh
git rev-list --all --count
```
