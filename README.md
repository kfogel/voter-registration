#Voter Registration [![Build Status](https://secure.travis-ci.org/democrats/voter-registration.png?branch=master)][travis]
[travis]: http://travis-ci.org/democrats/voter-registration

[![Code Climate](https://codeclimate.com/badge.png)](https://codeclimate.com/github/democrats/voter-registration)

##About

We need more Americans to have a say in their government, not just the special interests. That's why we should be taking down roadblocks to voting.  We believe in an America where everybody can make their voices heard.

That is why the Democratic National Committee created this open source application to provide more opportunities to register to vote in November!  States have varying laws for voter registration, so this application is a one stop shop that contains all the voter registration information and voting checklists that you will need to vote. **This information should not be altered.**

You can help all eligible voters register to vote by using this software.

# What is it?

A Ruby on Rails Application that generates a [National Voter Registration Form](http://www.eac.gov/voter_resources/register_to_vote.aspx) PDF from a webform.
Includes the guidelines for the National Voter Registration form in all states.

## Demo
You can see a running version of the application at [http://voter-registration.herokuapp.com/](http://voter-registration.herokuapp.com/)

## Requirements
1.  Make sure the machine that you're using has Ruby 1.9.3 installed.
    We use [rbenv](https://github.com/sstephenson/rbenv/) for Ruby version management
2.  You'll need the RubyGem "bundler" installed.

## Installation

    git clone git@github.com:ofa/voter-registration.git
    cd voter-registration
    bundle install
    rake db:migrate
    rake db:seed #This will load all the State information

## Usage
    rails server

Open up your browser and go to http://localhost:3000

## Deploying to [Heroku](http://www.heroku.com)
You can setup a Heroku account for free [https://devcenter.heroku.com/articles/quickstart](https://devcenter.heroku.com/articles/quickstart)

    heroku create
    heroku addons:add sendgrid:starter #Free addon used for devise emails
    rake secret # to generate a secret token
    heroku config:set SECRET_TOKEN={{your secret token}}
    git push heroku master
    heroku run rake db:migrate
    heroku run rake db:seed

## Running Tests

We use RSpec for tests: `bundle exec rake spec`

## Admin the pages
We use [rails_admin](https://www.github.com/sferik/rails_admin) to manage the State Guidelines
Go to "/admin" to login and manage the Guidelines

The default email: admin@example.com
The default password: p@ssw0rd

## Supported Ruby Versions
This application aims to support and is tested against the following Ruby
implementations:

* Ruby 1.9.3

## Contributing
Check out [contributing](https://github.com/democrats/voter-registration/blob/master/CONTRIBUTING.mkd) for ways that you can contribute

## Documentation

Documentation is available in the **/doc** directory in the root of the project.

## License

Voter Registration is open source software; please see LICENSE.md for licensing information.
