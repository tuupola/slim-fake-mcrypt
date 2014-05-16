Fake mcrypt extension for Slim
==============================

Slim 2.3.0 introduced a change which [makes mcrypt extension mandatory](https://github.com/codeguy/Slim/pull/523) when using Composer. There are cases when you can not or want not to install the extension. If you still want to use composer add *tuupola/slim-fake-mcrypt* to composer.json and you are good to go.

Problem was fixed in [release 2.4.2](https://github.com/codeguy/Slim/commit/eff176255635ddc867ff447812731807a3305e96). This package exists for historical reasons only.


```json
{
  "repositories": [{
      "type": "vcs",
      "url": "https://github.com/tuupola/slim-fake-mcrypt.git"
  }],
  "require": {
    "tuupola/slim-fake-mcrypt": "dev-master",
    "slim/slim": "2.3.*"
  }
}
```

Before
======

```sh
%composer install
Loading composer repositories with package information
Installing dependencies (including require-dev)
Your requirements could not be resolved to an installable set of packages.

  Problem 1
    - slim/slim 2.3.1 requires ext-mcrypt * -> the requested PHP extension mcrypt is missing from your system.
    - slim/slim 2.3.0 requires ext-mcrypt * -> the requested PHP extension mcrypt is missing from your system.
    - Installation request for slim/slim 2.3.* -> satisfiable by slim/slim[2.3.0, 2.3.1].
%
```

After
=====

```sh
%composer install
Loading composer repositories with package information
Installing dependencies (including require-dev)

  - Installing tuupola/slim-fake-mcrypt (dev-master 8eb1cc4)
    Cloning 8eb1cc4b585e5586a5e86afeaa2ac1871ebcccf4

  - Installing slim/slim (2.3.1)
    Loading from cache

Writing lock file
Generating autoload files
%
```
