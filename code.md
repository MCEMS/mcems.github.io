---
layout: markdown
---

Style
=====

Use the [GitHub JavaScript Styleguide](https://github.com/styleguide/javascript) for your CoffeeScript. Also, use CoffeeScript for more readable code.

Testing
=======

Unit tests. Write them. Make sure your code is covered. Follow TDD. For Javascript/Coffeescript, I like Mocha/Should, but feel free to use something else.

Continuous Integration
======================

All projects should have a Travis CI build set up to run unit tests and linting (if applicable) when a PR is made. If a project is Heroku-based, enable review apps so you will get a copy of the app with your changes linked to automatically on the PR.

Continuous Deployment
=====================

All merges on `master` should be deployed automatically (in the case of static GH pages sites, this will be the `gh-pages` branch). For Heroku, use the GitHub hooks to accomplish this.

