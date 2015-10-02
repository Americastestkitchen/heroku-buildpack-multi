# ATK's heroku-buildpack-multi

This repo (originally forked from [heroku/heroku-buildpack-multi](https://github.com/heroku/heroku-buildpack-multi)), is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) that triggers one or more other buildpacks in a single deploy process.

It was created to migrate [The Feed](https://github.com/Americastestkitchen/feed) from the Heroku stack of Cedar-10 to Cedar-14, where there are 2 buildbacks in the .buildpacks file that we need to run:
    https://github.com/Americastestkitchen/heroku-buildpack-apt
    https://github.com/Americastestkitchen/heroku-wordpress-php

---
## Original instructions

The following is from the original repo instructions [heroku/heroku-buildpack-multi](https://github.com/heroku/heroku-buildpack-multi).

This multi buildpack helps support:

1. Running multiple language buildpacks such as JS for assets and Ruby for your application
2. Running a daemon process such as [pgbouncer](https://github.com/heroku/heroku-buildpack-pgbouncer) with your application
3. Pulling in system dependencies.

## Usage

To use this buildpack you'll first need to set it as your custom buildpack:

    $ heroku buildpacks:set https://github.com/heroku/heroku-buildpack-multi.git

From here you will need to create a `.buildpacks` file which contains (in order) the buildpacks you wish to run when you deploy:

    $ cat .buildpacks
    https://github.com/heroku/heroku-buildpack-nodejs.git#0198c71daa8
    https://github.com/heroku/heroku-buildpack-ruby.git#v86

## License

MIT

## FAQ

