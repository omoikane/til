# Handle the commit author

The commit author consists of two parameters: a user name and an email address.

## Global

The first thing you should do when you install Git is to set your user name and email address. Usually you need to do this only the first time.

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Per repository

If you need to set a special author for a repository, you can specify it as in global configuration above, but without the `--global` parameter.

```
cd /path/to/repository
git config user.name "John Doe"
git config user.email johndoe@example.com
```

## Per commit

If you need to set a special author for a single commit, you can specify it directly in the commit command:

```
git commit --author="John Doe <johndoe@example.com>" -m "The commit message"
```
