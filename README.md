node-gitlab
===========

[![Build Status](https://travis-ci.org/moul/node-gitlab.png?branch=master)](https://travis-ci.org/moul/node-gitlab)
[![Dependency Status](https://david-dm.org/moul/node-gitlab.png?theme=shields.io)](https://david-dm.org/moul/node-gitlab)
[![authors](https://sourcegraph.com/api/repos/github.com/moul/node-gitlab/badges/authors.png)](https://sourcegraph.com/github.com/moul/node-gitlab)
[![library users](https://sourcegraph.com/api/repos/github.com/moul/node-gitlab/badges/library-users.png)](https://sourcegraph.com/github.com/moul/node-gitlab)
[![Total views](https://sourcegraph.com/api/repos/github.com/moul/node-gitlab/counters/views.png)](https://sourcegraph.com/github.com/moul/node-gitlab)
[![Views in the last 24 hours](https://sourcegraph.com/api/repos/github.com/moul/node-gitlab/counters/views-24h.png)](https://sourcegraph.com/github.com/moul/node-gitlab)
[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/moul/node-gitlab/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

[![NPM Badge](https://nodei.co/npm/gitlab.png?downloads=true&stars=true)](https://npmjs.org/package/gitlab)

[GitLab](https://github.com/gitlabhq/gitlabhq) API Nodejs library.


Install
=======

```bash
npm install gitlab
```

Develop
=======

```bash
cake watch
```

Edit the [CoffeeScript](http://coffeescript.org/) files in `src`.

Example Usage
=============

Coffee-Script
-------------
```coffee
# Connection
gitlab = new require('gitlab')
  url:   'http://example.com'
  token: 'abcdefghij123456'
  
# Listing users
gitlab.users.all (users) ->
  console.log "##{user.id}: #{user.email}, #{user.name}, #{user.created_at}" for user in users

# Listing projects
gitlab.projects.all (projects) ->
  for project in projects
    console.log "##{project.id}: #{project.name}, path: #{project.path}, default_branch: #{project.default_branch}, private: #{project.private}, owner: #{project.owner.name} (#{project.owner.email}), date: #{project.created_at}"
```

Javascript
----------
```javascript
// Connection
var gitlab = new require('gitlab')({
  url:   'http://example.com',
  token: 'abcdefghij123456'
});
  
// Listing users
gitlab.users.all(function(users) {
  for (var i = 0; i < users.length; i++) {
    console.log("#" + user.id + ": " + user.email + ", " + user.name + ", " + user.created_at));
  }
});

// Listing projects
gitlab.projects.all(function(projects) {
  for (var i = 0; i < projects.length; i++) {
    console.log("#" + project.id + ": " + project.name + ", path: " + project.path + ", default_branch: " + project.default_branch + ", private: " + project["private"] + ", owner: " + project.owner.name + " (" + project.owner.email + "), date: " + project.created_at);
  }
});
```

See [Examples directory](https://github.com/moul/node-gitlab/tree/master/examples) for more examples

Contributors
------------

- [Dave Irvine](https://github.com/dave-irvine)
- [Glavin Wiechert](https://github.com/Glavin001)
- [Florian Quiblier](https://github.com/fofoy)
- [Anthony Heber](https://github.com/aheber)

License
-------

MIT
