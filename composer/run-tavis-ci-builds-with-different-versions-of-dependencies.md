# Run Travis CI builds with different versions of dependencies

By default, Composer installs the latest possible versions of dependencies which are allowed by the constraints in `composer.json`. It means that for the dependency constraint `^3.0 || ^4.0`, the build would always use the latest version of the v4 release. As the 3.0 is never tested, the library may not be compatible with it and that would make your users sad.

Luckily, Composer provides a switch to install the lowest possible versions of dependencies `--prefer-lowest` (should be used with `--prefer-stable` to prevent installation of non-stable versions).

Updated `.travis.yml` configuration may look like this:

```yaml
language: php

php:
  - 7.1
  - 7.2

env:
  matrix:
    - PREFER_LOWEST="--prefer-lowest --prefer-stable"
    - PREFER_LOWEST=""

before_script:
  - composer update $PREFER_LOWEST

script:
  - composer ci
```

Even though this solution would catch most of the incompatibilities, remember that there are many combinations of dependencies between lowest and latest versions. And they may be incompatible together.

[Reference](https://blog.martinhujer.cz/17-tips-for-using-composer-efficiently/)