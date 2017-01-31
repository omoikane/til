# Run git commands from another directory

If you want to execute `git log` in folder `/path`, type:

```
git -C /path log
```

Just like `make -C <directory>`, `git -C <directory> ...` tells Git to go there before doing anything else.
