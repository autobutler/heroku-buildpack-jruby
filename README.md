# Heroku buildpack for JRuby

A buildpack to fast and easy use JRuby on Heroku. Just create a Heroku app like this:

    heroku create -s cedar --buildpack https://github.com/carlhoerberg/heroku-buildpack-jruby.git 

It will download and unpack JRuby from [jruby.org](http://jruby.org/), install [Bundler](http://gembundler.com/) and run ```bundle install``` and then use your ```Procfile```.

Example ```Procfile```:

    web: bin/trinidad -t -r -p $PORT -e $RACK_ENV

Note: You do normally not want to use ```bundle exec``` with JRuby. Use the binstubs (in ```bin/```) instead, and put ```require 'bundler/setup'``` before any other ```require```.

Current JRuby version: 1.6.7

For now only support 1.9 mode, open an issue if you need 1.8 mode.

