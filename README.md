[gem]: https://rubygems.org/gems/rodakase
[travis]: https://travis-ci.org/solnic/rodakase
[gemnasium]: https://gemnasium.com/solnic/rodakase
[codeclimate]: https://codeclimate.com/github/solnic/rodakase
[inchpages]: http://inch-ci.org/github/solnic/rodakase/

# About

This is the project where initial ideas behind dry-system, dry-view and dry-transaction have been tested out. Eventually, this repo was moved to dry-rb/dry-web and dry-rb/dry-web-roda was extracted from it to provide Roda support. I've re-pushed this repo for sentimental/historical reasons.

# Rodakase (discontinued) [![Join the chat at https://gitter.im/solnic/rodakase](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/solnic/rodakase?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

[![Gem Version](https://badge.fury.io/rb/rodakase.svg)][gem]
[![Build Status](https://travis-ci.org/solnic/rodakase.svg?branch=master)][travis]
[![Dependency Status](https://gemnasium.com/solnic/rodakase.svg)][gemnasium]
[![Code Climate](https://codeclimate.com/github/solnic/rodakase/badges/gpa.svg)][codeclimate]
[![Test Coverage](https://codeclimate.com/github/solnic/rodakase/badges/coverage.svg)][codeclimate]
[![Inline docs](http://inch-ci.org/github/solnic/rodakase.svg?branch=master&style=flat)][inchpages]

Rodakase is a lightweight web stack on top of Roda which gives you a foundation
for building robust web applications while decoupling your application code from
the framework.

There are a couple of core concepts in Rodakase which makes it stand out from the crowd:

* Container-based architecture where your application dependencies are accessible
  through a simple IoC container
* Promotes simple, side-effect-less, functional objects with a built-in auto-injection
  mechanism making it trivial to compose objects
* Roda routing is decoupled from core application logic and focuses purely on
  http-related concerns (status codes, session, cookies etc.)
* Rendering is decoupled too, roda routing simply gets response body from *your*
  objects
* Request processing and response construction in functional style as a series
  of simple "function" calls
* Extreme focus on proper code organization and reusability, functionality of your
  application should be easily accessible using clear APIs
* Uses ROM by default for persistence

Rodakase says **NO** to the following concepts:

* monkey-patching
* mutable global state
* hot-code reloading in dev mode leading to additional complexity, nasty gotchas
  and silly constraints with regards to code organization
* implicit dependency handling through magical const-loading mechanisms
* tight coupling between web application logic and core domain logic
* tight coupling between persistence logic and core domain logic

## Sample App

A sample rodakase-based web app is [right here](https://github.com/solnic/rodakase-blog).

## Tools

Rodakase is based on a bunch of awesome libraries:

* roda
* roda-flow
* dry-container
* dry-auto_inject
* tilt
* transflow (later replaced by dry-transaction)

## LICENSE

See `LICENSE.txt` file.

## Installation

Add this line to your application's Gemfile:

```
gem 'rodakase'
```

And then execute:

```
$ bundle
```

Or install it yourself as:

```
$ gem install rodakase
```

## Development

To run the specs make sure the dummy app uses proper db configuration `spec/dummy/config/application.yml`.
Also you need to run the migrations, do following:

```
  $ cd spec/dummy
  $ bundle install
  $ rake db:migrate
```

After that you can run the specs from rodakase root:

```
  $ bundle exec rspec
```

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/solnic/rodakase.
