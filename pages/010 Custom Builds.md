## Custom builds

Custom builds make it easy to create lightweight versions of lodash containing only the features you need. To top it off, we handle all function dependency & alias mapping for you. Review the [build differences](https://github.com/lodash/lodash/wiki/build-differences) & pick the one that’s right for you.

Using Grunt? We also provide a [Grunt plugin](https://npmjs.org/package/grunt-lodash) to build lodash as part of your Gruntfile.

The `lodash` command-line utility is available when [lodash-cli](https://npmjs.org/package/lodash-cli) is installed as a global package:

```
$ {sudo -H} npm i -g npm
$ {sudo -H} npm i -g lodash-cli
$ lodash -h
```

**Note:** Uninstall older versions _before_ installing `lodash-cli`.

*   Compat builds, with support for old & new environments, are created using the `compat` modifier. _(default)_

```
lodash compat
```

*   Modern builds, tailored for newer environments with [ES5](https://es5.github.io/)/[ES6](ttps://people.mozilla.org/~jorendorff/es6-draft.html) support, are created using the `modern` modifier.

```
lodash modern
```

*   Strict builds, with [ES strict mode](https://es5.github.io/#C) enabled, are created using the `strict` modifier.

```
lodash strict
```

*   Modularized builds, splitting lodash into modules, are created using the `modularize` modifier.

```
lodash modularize
```

Build commands:

*   Use the `category` command to pass comma separated categories of functions to include in the build. Valid categories are _“array”_, _“chain”_, _“collection”_, _“date”_, _“function”_, _“lang”_, _“object”_, _“number”_, _“string”_, & _“utility”_.

```
lodash category=collection,function
```

*   Use the `exports` command to pass comma separated names of ways to export the `lodash` function. Valid exports are _“amd”_, _“commonjs”_, _“es”_, _“global”_, _“iojs”_, _“node”_, _“npm”_, _“none”_, & _“umd”_.

```
lodash exports=amd,commonjs,iojs
```

*   Use the `iife` command to specify code to replace the [IIFE](http://benalman.com/news/2010/11/immediately-invoked-function-expression/) that wraps lodash.

```
lodash iife="!function(window,undefined){%output%}(this)"
```

*   Use the `include` command to pass comma separated names of functions to include in the build.

```
lodash include=each,filter,map
```

*   Use the `minus` command to pass comma separated function/category names to remove from the build.

```
lodash modern minus=result,shuffle
```

*   Use the `plus` command to pass comma separated function/category names to add to the build.

```
lodash category=array plus=random,template
```

*   Use the `template` command to pass the file path pattern used to match template files to precompile. **Note:** Precompiled templates are assigned to the `_.templates` object.

```
lodash template="./*.jst"
```

*   Use the `settings` command to pass template settings used when precompiling templates.

```
lodash settings="{interpolate:/\{\{([\s\S]+?)\}\}/g}"
```

*   Use the `moduleId` command to specify the AMD module ID for lodash or the module ID used to include lodash in compiled templates. Use “none” as the module ID to create compiled templates without a dependency on lodash.

```
lodash moduleId=underscore
```

**Notes:**

*   All commands except `compat` & `modern` may be combined
*   The `exports` values _“es”_ & _“npm”_ may only be used in conjunction with the `modularize` command
*   The `modularize` command uses the first `exports` values as its module format, ignoring subsequent values.
*   Unless specified by `-o` or `--output` all files created are saved to the current working directory
*   Node.js 0.10.8-0.10.11 [have](https://github.com/joyent/node/issues/5622) [bugs](https://github.com/joyent/node/issues/5688) preventing minified builds

The following options are also supported:

```
-c, --stdout .......... Write output to standard output
-d, --development ..... Write only the non-minified development output
-h, --help ............ Display help information
-m, --source-map ...... Generate a source map using an optional source map URL
-o, --output .......... Write output to a given path/filename
-p, --production ...... Write only the minified production output
-s, --silent .......... Skip status updates normally logged to the console
-V, --version ......... Output current version of lodash
```
