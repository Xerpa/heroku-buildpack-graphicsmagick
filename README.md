heroku-buildpack-graphicsmagick
===============================

Allows using the graphicsmagick library

USAGE
-----

Just add this buildpack before the one that configures your
application. This buildpack will install files under
`/app/vendor/graphicsmagick` prefix. The `GraphicsMagick-config` and
`gm` binaries will be in the `bin` directory under that prefix.

```bash
$ heroku buildpacks:add https://github.com/xerpa/heroku-buildpack-graphicsmagick.git
```

CONFIG
------

* debug prints a lot of information during the build [default: false];

* gm_url the url to a tar.bz2 file with the source code
         [default: ftp://ftp.graphicsmagick.org/pub/GraphicsMagick/1.3/GraphicsMagick-1.3.19.tar.bz2]

CAVEATS
-------

The first time will take a long time to compile. Further builds should
be a lot faster since it will use the cache. The cached version takes
into account the `STACK` version, so you don't have to worry about
that.

LICENSE
-------

* BSD-3
