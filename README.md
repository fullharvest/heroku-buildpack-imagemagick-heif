heroku-buildpack-imagemagick-heif
=================================

Forked from a 3rd-party Heroku buildpack to install ImageMagick 7 on FH's heroku-18 servers. Not guarenteed to work when the app is upgraded to a new Heroku stack.

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for vendoring the ImageMagick  with HEIF support binaries into your project. 

This one works with [Heroku stack](https://devcenter.heroku.com/articles/stack) `heroku-18`.

## Usage

Add this buildpack to your app:

```
https://github.com/epicatization/heroku-buildpack-imagemagick-heif
```

## Build script

[This](./build.sh) is the script used to build vips using docker.
After building a tar file, it will be copied to the `build` directory. Then you should commit this changes to git.

### Clear cache
Since the installation is cached you might want to clean it out due to config changes.

1. `heroku plugins:install heroku-repo`
2. `heroku repo:purge_cache -app HEROKU_APP_NAME`

### Credits
https://github.com/brandoncc/heroku-buildpack-vips
https://github.com/steeple-dev/heroku-buildpack-imagemagick
