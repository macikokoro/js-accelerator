# generator-jq

## Getting Started

## Yeoman Generators
-----------------------------------
mkdir generator-nameofgenerator

- folder name has to start with generator

npm init //to create package.json

```
{
  "name": "generator-jq",
  "version": "0.1.0",
  "description": "",
  "keywords": [
    "yeoman-generator"
  ],
  "dependencies": {
    "yeoman-generator": "^0.16.0"
  }
}
```

- name property must be prefixed by generator-
- keyword property must cotain yeoman-generator to be indexed by the community generator page.

npm install --save yeoman-generator

#### Create Folder structure
------------------------------

├───package.json
├───app/
│   └───index.js
└───router/
    └───index.js

Extend a base generator

In app/index.js

```
'use strict';
var util = require('util');
var path = require('path');
var yeoman = require('yeoman-generator');
var chalk = require('chalk');

var OnepageGenerator = yeoman.generators.Base.extend({

});

module.exports = OnepageGenerator;

```
This code creates a generator object and exports it out


To receive input form a user edit index.js

```
var OnepageGenerator = yeoman.generators.Base.extend({
    promptUser: function() {
        var done = this.async();

        // have Yeoman greet the user
        console.log(this.yeoman);

        var prompts = [{
            name: 'appName',
            message: 'What is your app\'s name ?'
        },{
            type: 'confirm',
            name: 'addDemoSection',
            message: 'Would you like to generate a demo section ?',
            default: true
        }];

        this.prompt(prompts, function (props) {
            this.appName = props.appName;
            this.addDemoSection = props.addDemoSection;

            done();
        }.bind(this));
    }
});
```

### Scaffolding an application
-------------------------------------
mkdir templates

touch templates/_index.html

- starting a filename with underscore is good practice to differentiate the name from the final ouput name.

Create the footer

touch templates/_footer.html

Create the menu

touch templates/_menu.html

Create the section

touch templates/_section.html

Create the css files

mkdir css

touch css/_main.css

touch css/_section.css

Create _gruntfile.js and _package.json

touch templates/_gruntfile.js

touch templates/_package.json

##### Original tutorial:

http://code.tutsplus.com/tutorials/build-your-own-yeoman-generator--cms-20040



```bash
npm install -g yo
```
To install generator-jq from npm, run:

```bash
npm install -g generator-jq
```

Initiate the generator:

```bash
yo jq
```
