# grunt-nglue

![nglue logo](https://raw.github.com/eladelrom/poet/ei-pages/effectiveidea/public/images/nglue-logo-small.jpg)

> Glue re-usable angular modules together to create one app

`nglue` is lightweight architectural micro-framework it stands for the internal architecture of the processor. It provides the skeleton, around the exact needs/features of your application. In other words, nglue framework provides the starting point for your application’s architecture.

See: [https://github.com/eladelrom/generator-nglue](https://github.com/eladelrom/generator-nglue)

## Getting Started
This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-nglue --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
'use strict';
module.exports = function (grunt) {
  grunt.loadNpmTasks('grunt-nglue');
};
```

The grunt plugin is intended to be used in an `nglue` project, it already includes the default task and other tasks.

### Grunt tasks:

>grunt

Once you run `grunt` the compiled js and css files will be published to `code_base/dist/`.  Assets files will be copied, less files will be compiled.
It uses the `config.js > name` and `version` to generate the names as follow;

<pre>
// global style
styles/your-project-name-global-components-0.0.0.css
styles/your-project-name-global-components-latest.css

// global components
js/your-project-name-global-components-0.0.0.min.js
js/your-project-name-global-components-latest.min.js

// global dev-dependencies components
js/your-project-name-global-components-dev-dependencies-0.0.0.min.js
js/your-project-name-global-components-dev-dependencies-latest.min.js
</pre>

To build a min module component file for an app do the following;

> grunt app --src=detail-page-app

This grunt task will fetch the `nglue.config` file from the app and will glue together all the modules bower and none bower components as well as a less files.
The `nglue.config` file of an app includes all modules you are adding together and than it go to work and pick each `nglue.confoig` from each module to create the component
library and less files.  When you created the app using `yo nglue:apps detail-page` it will create the scaffolding and template as well as basic `nglue.config` file.

Here's an example of an app `nglue.config` file;

<pre>
{
  "version": "0.0.1",
  "name": "detail-page-app",
  "dependencies": {
  },
  "nglue-dependencies": {
    "map": "map",
    "dropdown": "dropdown",
    "infinite-scroll": "infinite-scroll",
    "menu": "menu",
    "sorting": "sorting"
}
</pre>

## License
[MIT License](http://en.wikipedia.org/wiki/MIT_License)
