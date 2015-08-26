Create Project::

  $ mkdir browserify
  $ cd browserify
  $ npm init
  $ npm install browserify --save

main.js::

    var unique = require('uniq');

    var data = [1, 2, 2, 3, 4, 5, 5, 5, 6];

    console.log(unique(data));

Install uniq::

  $ npm install uniq

Build Bundle::

  $ browserify main.js -o bundle.js

