## Grunt
================================
JavaScript Task Runner

Build Tool

Automation tool

### Typical Grunt Tasks
- Concatenation
- Minification
- Pre-processing Sass and Coffeescript
- Image Optimization
- Running Tests
- Seeding the database
- Starting a development Server

### It has two parts
--------------------------

#### Global
- npm -g intall grunt-cli
- npm install grunt --save-dev

#### It requires a package.json

```
{
  "name": "example-project",
  "version": "0.0.1",
  "devDependencies": {
    "grunt": "~0.4.4"
  }
}
```
#### It also requires Gruntfile.js

This is the outline of plugins and rules to execute on the code.

Plugins are the existing packages with all the details about a task.

```
module.exports = function(grunt) {
  grunt.initConfig({
        //specify configuration for different tasks
          //see documentation for expected values
  });

  //task plugins to be loaded
  grunt.loadNpmTasks(‘package-name’);

  //indicate lists of tasks that can be run from
  //command line

  grunt.registerTask(‘default’,'task-name');
};
```

```
module.exports = function(grunt) {
  grunt.initConfig({
    simplemocha: {
      options: { timeout: 3000 },
      all: { src: ['test/**/*.js'] }
    }
  });

  grunt.loadNpmTasks('grunt-simple-mocha');

  grunt.registerTask('default','simplemocha');
};
```

#### JSHint

- JavaScript Code Linter
- Highlight potentially bad practices
- Keeps code consistent style
- Helps teams work together

#### To use JSHint with grunt

npm install grunt-contrib-jshint --save-dev

#### JSHint Gruntfile.js

```
module.exports = function(grunt) {

  grunt.loadNpmTasks('grunt-contrib-jshint');

  grunt.initConfig({
    jshint: {
      all: ['Gruntfile.js', 'server.js']
    }

  });

  grunt.registerTask('default','jshint');
};
```
#### Install simple mocha

npm install grunt-simple-mocha

mkdir test

start linting with *grunt*

Output
```
Running "jshint:all" (jshint) task
>> 2 files lint free.

```
