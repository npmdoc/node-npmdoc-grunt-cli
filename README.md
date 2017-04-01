# api documentation for  [grunt-cli (v1.2.0)](https://github.com/gruntjs/grunt-cli#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-grunt-cli.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-grunt-cli) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-grunt-cli.svg)](https://travis-ci.org/npmdoc/node-npmdoc-grunt-cli)
#### The grunt command line interface

[![NPM](https://nodei.co/npm/grunt-cli.png?downloads=true)](https://www.npmjs.com/package/grunt-cli)

[![apidoc](https://npmdoc.github.io/node-npmdoc-grunt-cli/build/screen-capture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-grunt-cli_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-grunt-cli/build..beta..travis-ci.org/apidoc.html)

![package-listing](https://npmdoc.github.io/node-npmdoc-grunt-cli/build/screen-capture.npmPackageListing.svg)



# package.json

```json

{
    "appveyor_id": "prp6g944b05jsq6d",
    "author": {
        "name": "Grunt Development Team",
        "url": "http://gruntjs.com/development-team"
    },
    "bin": {
        "grunt": "bin/grunt"
    },
    "bugs": {
        "url": "https://github.com/gruntjs/grunt-cli/issues"
    },
    "contributors": [
        {
            "name": "Tyler Kellen",
            "url": "http://goingslowly.com"
        },
        {
            "name": "Ben Alman",
            "url": "http://gruntjs.com"
        },
        {
            "name": "Scott González",
            "url": "http://nemikor.com"
        },
        {
            "name": "Forbes Lindesay",
            "url": "https://github.com/"
        }
    ],
    "dependencies": {
        "findup-sync": "~0.3.0",
        "grunt-known-options": "~1.1.0",
        "nopt": "~3.0.6",
        "resolve": "~1.1.0"
    },
    "description": "The grunt command line interface",
    "devDependencies": {
        "grunt": "~0.4.5",
        "grunt-contrib-jshint": "~1.0.0"
    },
    "directories": {},
    "dist": {
        "shasum": "562b119ebb069ddb464ace2845501be97b35b6a8",
        "tarball": "https://registry.npmjs.org/grunt-cli/-/grunt-cli-1.2.0.tgz"
    },
    "engines": {
        "node": ">=0.10.0"
    },
    "files": [
        "bin",
        "completion",
        "lib"
    ],
    "gitHead": "edd8bd29a72f2f28b63fe2629fcb7b9d9f2feb46",
    "homepage": "https://github.com/gruntjs/grunt-cli#readme",
    "license": "MIT",
    "maintainers": [
        {
            "name": "cowboy",
            "email": "cowboy@rj3.net"
        },
        {
            "name": "shama",
            "email": "kyle@dontkry.com"
        },
        {
            "name": "tkellen",
            "email": "tyler@sleekcode.net"
        },
        {
            "name": "vladikoff",
            "email": "vlad@vladikoff.com"
        }
    ],
    "name": "grunt-cli",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/gruntjs/grunt-cli.git"
    },
    "scripts": {
        "test": "node bin/grunt test"
    },
    "version": "1.2.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module grunt-cli](#apidoc.module.grunt-cli)
1.  object <span class="apidocSignatureSpan">grunt-cli.</span>completion
1.  object <span class="apidocSignatureSpan">grunt-cli.</span>info

#### [module grunt-cli.completion](#apidoc.module.grunt-cli.completion)
1.  [function <span class="apidocSignatureSpan">grunt-cli.completion.</span>print (name)](#apidoc.element.grunt-cli.completion.print)

#### [module grunt-cli.info](#apidoc.module.grunt-cli.info)
1.  [function <span class="apidocSignatureSpan">grunt-cli.info.</span>fatal (msg, code)](#apidoc.element.grunt-cli.info.fatal)
1.  [function <span class="apidocSignatureSpan">grunt-cli.info.</span>help ()](#apidoc.element.grunt-cli.info.help)
1.  [function <span class="apidocSignatureSpan">grunt-cli.info.</span>helpFooter ()](#apidoc.element.grunt-cli.info.helpFooter)
1.  [function <span class="apidocSignatureSpan">grunt-cli.info.</span>helpHeader ()](#apidoc.element.grunt-cli.info.helpHeader)
1.  [function <span class="apidocSignatureSpan">grunt-cli.info.</span>version ()](#apidoc.element.grunt-cli.info.version)



# <a name="apidoc.module.grunt-cli"></a>[module grunt-cli](#apidoc.module.grunt-cli)



# <a name="apidoc.module.grunt-cli.completion"></a>[module grunt-cli.completion](#apidoc.module.grunt-cli.completion)

#### <a name="apidoc.element.grunt-cli.completion.print"></a>[function <span class="apidocSignatureSpan">grunt-cli.completion.</span>print (name)](#apidoc.element.grunt-cli.completion.print)
- description and source-code
```javascript
print = function (name) {
  var code = 0;
  var filepath = path.join(__dirname, '../completion', name);
  var output;
  try {
    // Attempt to read shell completion file.
    output = String(fs.readFileSync(filepath));
  } catch (err) {
    code = 5;
    output = 'echo "Specified grunt shell auto-completion rules ';
    if (name && name !== 'true') {
      output += 'for \'' + name + '\' ';
    }
    output += 'not found."';
  }

  console.log(output);
  process.exit(code);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.grunt-cli.info"></a>[module grunt-cli.info](#apidoc.module.grunt-cli.info)

#### <a name="apidoc.element.grunt-cli.info.fatal"></a>[function <span class="apidocSignatureSpan">grunt-cli.info.</span>fatal (msg, code)](#apidoc.element.grunt-cli.info.fatal)
- description and source-code
```javascript
fatal = function (msg, code) {
  exports.helpHeader();
  console.log('Fatal error: ' + msg);
  console.log('');
  exports.helpFooter();
  process.exit(code);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.grunt-cli.info.help"></a>[function <span class="apidocSignatureSpan">grunt-cli.info.</span>help ()](#apidoc.element.grunt-cli.info.help)
- description and source-code
```javascript
help = function () {
  exports.helpHeader();
  exports.helpFooter();
  process.exit();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.grunt-cli.info.helpFooter"></a>[function <span class="apidocSignatureSpan">grunt-cli.info.</span>helpFooter ()](#apidoc.element.grunt-cli.info.helpFooter)
- description and source-code
```javascript
helpFooter = function () {
  [
    'If you\'re seeing this message, grunt hasn\'t been installed locally to',
    'your project. For more information about installing and configuring grunt,',
    'please see the Getting Started guide:',
    '',
    'http://gruntjs.com/getting-started',
  ].forEach(function(str) { console.log(str); });
}
```
- example usage
```shell
...
};

// Show help, then exit with a message and error code.
exports.fatal = function(msg, code) {
exports.helpHeader();
console.log('Fatal error: ' + msg);
console.log('');
exports.helpFooter();
process.exit(code);
};

// Show help and exit.
exports.help = function() {
exports.helpHeader();
exports.helpFooter();
...
```

#### <a name="apidoc.element.grunt-cli.info.helpHeader"></a>[function <span class="apidocSignatureSpan">grunt-cli.info.</span>helpHeader ()](#apidoc.element.grunt-cli.info.helpHeader)
- description and source-code
```javascript
helpHeader = function () {
  console.log('grunt-cli: ' + pkg.description + ' (v' + pkg.version + ')');
  console.log('');
}
```
- example usage
```shell
...
// Display grunt-cli version.
exports.version = function() {
  console.log('grunt-cli v' + pkg.version);
};

// Show help, then exit with a message and error code.
exports.fatal = function(msg, code) {
  exports.helpHeader();
  console.log('Fatal error: ' + msg);
  console.log('');
  exports.helpFooter();
  process.exit(code);
};

// Show help and exit.
...
```

#### <a name="apidoc.element.grunt-cli.info.version"></a>[function <span class="apidocSignatureSpan">grunt-cli.info.</span>version ()](#apidoc.element.grunt-cli.info.version)
- description and source-code
```javascript
version = function () {
  console.log('grunt-cli v' + pkg.version);
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
