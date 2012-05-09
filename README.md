# Heroku buildpack for NeoQuotes

Buildpack for [NeoQuotes](https://github.com/tomasmuller/neoquotes) application based on [JRuby](https://github.com/jruby/heroku-buildpack-jruby) and [Java](https://github.com/heroku/heroku-buildpack-java) buildpacks.

For more information about Heroku buildpacks, access: [https://devcenter.heroku.com/articles/buildpacks](https://devcenter.heroku.com/articles/buildpacks).

Detect:
-------
Check the existence of a Gemfile in the project root directory.


Compile:
--------
  1. JRuby is downloaded, extracted and configured.
  2. Default gems are installed (jruby-openssl, bundler and rake).
  3. The dependencies are installed with Bundler.
  4. Maven is downloaded, extracted and configured.
  5. Finally, a mvn clean install is executed.


Release:
--------
  * Add-on: neo4j:test and shared-database:5mb
  * jruby/bin to $PATH
  * Environment variables: RACK_ENV, RAILS_ENV and JRUBY_OPTS
