# TSLint Task
Lint your source files with TSLint.

## API

### tslint([options])

#### Available options:

##### **src**
(String|Array) Glob or array of globs ([What's a glob?](https://github.com/isaacs/node-glob#glob-primer)) matching TypeScript files. Default: `'app/**/*.ts'`.

##### **tslintOptions**
(Object) All [tslint options](https://github.com/panuhorsmalahti/gulp-tslint#all-default-tslint-options). Default:

```
{
    configuration: 'tslint.json',
    rulesDirectory: null,
    tslint: null
}
```

##### **reporter**
(String) A string with the name of the reporter for outputting errors. Default: `"verbose"`. Options: `"json", "prose", "verbose", "full", "msbuild"`. See the [gulp-tslint docs](https://github.com/panuhorsmalahti/gulp-tslint) for descriptions.

##### **reporterOptions**
(Object) All [reporter options](https://github.com/panuhorsmalahti/gulp-tslint#all-default-report-options). Default:

```
{
    emitError: true,
    reportLimit: 0,
    summarizeFailureOutput: false
}
```

## Usage

To use this task, install the npm package:

```
npm install --save-dev ionic-gulp-tslint
```

_Note: this package is already added by default to Ionic 2 starters._

Add the following to the `gulpfile.js` in order to run `gulp lint` from a terminal and use the rules found in the `tslint.json` file.

```javascript
var tslint = require('ionic-gulp-tslint');

// default options
gulp.task('lint', tslint);
```

## Advanced Usage

Many of the options can be overridden from the defaults. The following task passes custom options.

```javascript
var tslint = require('ionic-gulp-tslint');

// override options
gulp.task('lint', function () {
  return tslint({
    src: 'app/**/*.ts',
    tslintOptions: {
      configuration: 'source/tslint.json'
    },
    reporter: "prose",
    reportOptions: {
      emitError: true
    }
  });
});
```
