# api documentation for  [systemjs (v0.20.11)](https://github.com/systemjs/systemjs#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-systemjs.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-systemjs) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-systemjs.svg)](https://travis-ci.org/npmdoc/node-npmdoc-systemjs)
#### Dynamic ES module loader

[![NPM](https://nodei.co/npm/systemjs.png?downloads=true)](https://www.npmjs.com/package/systemjs)

[![apidoc](https://npmdoc.github.io/node-npmdoc-systemjs/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-systemjs_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-systemjs/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-systemjs/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-systemjs/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Guy Bedford"
    },
    "bugs": {
        "url": "https://github.com/systemjs/systemjs/issues"
    },
    "dependencies": {},
    "description": "Dynamic ES module loader",
    "devDependencies": {
        "babel-core": "^6.21.0",
        "babel-plugin-syntax-dynamic-import": "^6.18.0",
        "babel-plugin-transform-es2015-modules-systemjs": "^6.19.0",
        "bluebird": "^3.4.6",
        "es-module-loader": "^2.1.0",
        "mocha": "^3.1.2",
        "plugin-typescript": "^5.2.7",
        "rollup": "^0.41.1",
        "rollup-plugin-node-resolve": "^2.0.0",
        "rollup-plugin-replace": "^1.1.1",
        "systemjs-plugin-babel": "0.0.17",
        "systemjs-plugin-traceur": "0.0.3",
        "traceur": "0.0.111",
        "typescript": "^2.0.6",
        "uglifyjs": "^2.4.10"
    },
    "directories": {},
    "dist": {
        "shasum": "a874a47e0472471a8442bed685259b2a9a82069b",
        "tarball": "https://registry.npmjs.org/systemjs/-/systemjs-0.20.11.tgz"
    },
    "files": [
        "dist"
    ],
    "gitHead": "664115e924472a6e807297048605cdd33f83acf7",
    "homepage": "https://github.com/systemjs/systemjs#readme",
    "license": "MIT",
    "main": "dist/system.src.js",
    "maintainers": [
        {
            "name": "guybedford",
            "email": "guybedford@gmail.com"
        }
    ],
    "name": "systemjs",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/systemjs/systemjs.git"
    },
    "scripts": {
        "build": "npm run build:dev && npm run build:production",
        "build:dev": "rollup -c",
        "build:production": "rollup -c --environment production",
        "footprint": "npm run footprint:dev && npm run footprint:production",
        "footprint:dev": "uglifyjs dist/system.src.js -cm --screw-ie8 | gzip -9f | wc -c",
        "footprint:production": "uglifyjs dist/system-production.src.js -cm --screw-ie8 | gzip -9f | wc -c",
        "irhydra": "node --trace-hydrogen --trace-phase=Z --trace-deopt --code-comments --hydrogen-track-positions --redirect-code-traces --redirect-code-traces-to=code.asm --print-opt-code --trace_hydrogen_file=hydrogen.cfg irhydra/load.js",
        "min": "npm run min:dev && npm run min:production",
        "min:dev": "cd dist && uglifyjs system.src.js -cm --in-source-map system.src.js.map --source-map system.js.map --screw-ie8 --comments '/SystemJS v/' > system.js",
        "min:production": "cd dist && uglifyjs system-production.src.js -cm --in-source-map system-production.src.js.map --source-map system-production.js.map --screw-ie8 --comments '/SystemJS v/' > system-production.js",
        "prepublish": "rm -r dist && npm run build && npm run min",
        "test": "npm run test:production && npm run test:babel && npm run test:traceur && npm run test:typescript",
        "test:babel": "mocha test/test-babel.js -u tdd --reporter dot",
        "test:production": "mocha test/test-production.js -u tdd --reporter dot",
        "test:traceur": "mocha test/test-traceur.js -u tdd --reporter dot",
        "test:typescript": "mocha test/test-typescript.js -u tdd --reporter dot"
    },
    "version": "0.20.11"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module systemjs](#apidoc.module.systemjs)
1.  boolean <span class="apidocSignatureSpan">systemjs.</span>trace
1.  [function <span class="apidocSignatureSpan">systemjs.</span>_nodeRequire (path)](#apidoc.element.systemjs._nodeRequire)
1.  [function <span class="apidocSignatureSpan">systemjs.</span>amdDefine (name, deps, factory)](#apidoc.element.systemjs.amdDefine)
1.  [function <span class="apidocSignatureSpan">systemjs.</span>amdRequire (names, callback, errback, referer)](#apidoc.element.systemjs.amdRequire)
1.  object <span class="apidocSignatureSpan">systemjs.</span>_loader
1.  object <span class="apidocSignatureSpan">systemjs.</span>_nodeRequire.extensions
1.  object <span class="apidocSignatureSpan">systemjs.</span>registry
1.  string <span class="apidocSignatureSpan">systemjs.</span>scriptSrc

#### [module systemjs._nodeRequire](#apidoc.module.systemjs._nodeRequire)
1.  [function <span class="apidocSignatureSpan">systemjs.</span>_nodeRequire (path)](#apidoc.element.systemjs._nodeRequire._nodeRequire)
1.  [function <span class="apidocSignatureSpan">systemjs._nodeRequire.</span>resolve (request)](#apidoc.element.systemjs._nodeRequire.resolve)
1.  object <span class="apidocSignatureSpan">systemjs._nodeRequire.</span>cache
1.  object <span class="apidocSignatureSpan">systemjs._nodeRequire.</span>extensions
1.  object <span class="apidocSignatureSpan">systemjs._nodeRequire.</span>main

#### [module systemjs._nodeRequire.extensions](#apidoc.module.systemjs._nodeRequire.extensions)

#### [module systemjs.registry](#apidoc.module.systemjs.registry)
1.  [function <span class="apidocSignatureSpan">systemjs.registry.</span>delete (key)](#apidoc.element.systemjs.registry.delete)
1.  symbol <span class="apidocSignatureSpan">systemjs.registry.</span>_registry



# <a name="apidoc.module.systemjs"></a>[module systemjs](#apidoc.module.systemjs)

#### <a name="apidoc.element.systemjs._nodeRequire"></a>[function <span class="apidocSignatureSpan">systemjs.</span>_nodeRequire (path)](#apidoc.element.systemjs._nodeRequire)
- description and source-code
```javascript
function require(path) {
  try {
    exports.requireDepth += 1;
    return self.require(path);
  } finally {
    exports.requireDepth -= 1;
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.systemjs.amdDefine"></a>[function <span class="apidocSignatureSpan">systemjs.</span>amdDefine (name, deps, factory)](#apidoc.element.systemjs.amdDefine)
- description and source-code
```javascript
function define(name, deps, factory) {
  if (typeof name !== 'string') {
    factory = deps;
    deps = name;
    name = null;
  }

  if (!(deps instanceof Array)) {
    factory = deps;
    deps = ['require', 'exports', 'module'].splice(0, factory.length);
  }

  if (typeof factory !== 'function')
    factory = (function (factory) {
      return function() { return factory; }
    })(factory);

  if (!name) {
    if (curMetaDeps) {
      deps = deps.concat(curMetaDeps);
      curMetaDeps = undefined;
    }
  }

  // remove system dependencies
  var requireIndex, exportsIndex, moduleIndex;

  if ((requireIndex = deps.indexOf('require')) !== -1) {

    deps.splice(requireIndex, 1);

    // only trace cjs requires for non-named
    // named defines assume the trace has already been done
    if (!name)
      deps = deps.concat(amdGetCJSDeps(factory.toString(), requireIndex));
  }

  if ((exportsIndex = deps.indexOf('exports')) !== -1)
    deps.splice(exportsIndex, 1);

  if ((moduleIndex = deps.indexOf('module')) !== -1)
    deps.splice(moduleIndex, 1);

  function execute (req, exports, module) {
    var depValues = [];
    for (var i = 0; i < deps.length; i++)
      depValues.push(req(deps[i]));

    module.uri = module.id;

    module.config = noop;

    // add back in system dependencies
    if (moduleIndex !== -1)
      depValues.splice(moduleIndex, 0, module);

    if (exportsIndex !== -1)
      depValues.splice(exportsIndex, 0, exports);

    if (requireIndex !== -1) {
      var contextualRequire = function (names, callback, errback) {
        if (typeof names === 'string' && typeof callback !== 'function')
          return req(names);
        return require.call(loader, names, callback, errback, module.id);
      };
      contextualRequire.toUrl = function (name) {
        return loader.normalizeSync(name, module.id);
      };
      depValues.splice(requireIndex, 0, contextualRequire);
    }

    // set global require to AMD require
    var curRequire = envGlobal.require;
    envGlobal.require = require;

    var output = factory.apply(exportsIndex === -1 ? envGlobal : exports, depValues);

    envGlobal.require = curRequire;

    if (typeof output !== 'undefined')
      module.exports = output;
  }

  // anonymous define
  if (!name) {
    loader.registerDynamic(deps, false, curEsModule ? wrapEsModuleExecute(execute) : execute);
  }
  else {
    loader.registerDynamic(name, deps, false, execute);

    // if we don't have any other defines,
    // then let this be an anonymous define
    // this is just to support single modules of the form:
    // define('jquery')
    // still loading anonymously
    // because it is done widely enough to be useful
    // as soon as there is more than one define, this gets removed though
    if (lastNamedDefine) {
      lastNamedDefine = undefined;
      multipleNamedDefines = true;
    }
    else if (!multipleNamedDefines) {
      lastNamedDefine = [deps, execute];
    }
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.systemjs.amdRequire"></a>[function <span class="apidocSignatureSpan">systemjs.</span>amdRequire (names, callback, errback, referer)](#apidoc.element.systemjs.amdRequire)
- description and source-code
```javascript
function require(names, callback, errback, referer) {
  // in amd, first arg can be a config object... we just ignore
  if (typeof names === 'object' && !(names instanceof Array))
    return require.apply(null, Array.prototype.splice.call(arguments, 1, arguments.length - 1));

  // amd require
  if (typeof names === 'string' && typeof callback === 'function')
    names = [names];
  if (names instanceof Array) {
    var dynamicRequires = [];
    for (var i = 0; i < names.length; i++)
      dynamicRequires.push(loader.import(names[i], referer));
    Promise.all(dynamicRequires).then(function (modules) {
      for (var i = 0; i < modules.length; i++)
        modules[i] = modules[i].__useDefault ? modules[i].default : modules[i];
      if (callback)
        callback.apply(null, modules);
    }, errback);
  }

  // commonjs require
  else if (typeof names === 'string') {
    var normalized = loader.decanonicalize(names, referer);
    var module = loader.get(normalized);
    if (!module)
      throw new Error('Module not already loaded loading "' + names + '" as ' + normalized + (referer ? ' from "' + referer + '".' : '.'));
    return module.__useDefault ? module.default : module;
  }

  else
    throw new TypeError('Invalid require');
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.systemjs._nodeRequire"></a>[module systemjs._nodeRequire](#apidoc.module.systemjs._nodeRequire)

#### <a name="apidoc.element.systemjs._nodeRequire._nodeRequire"></a>[function <span class="apidocSignatureSpan">systemjs.</span>_nodeRequire (path)](#apidoc.element.systemjs._nodeRequire._nodeRequire)
- description and source-code
```javascript
function require(path) {
  try {
    exports.requireDepth += 1;
    return self.require(path);
  } finally {
    exports.requireDepth -= 1;
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.systemjs._nodeRequire.resolve"></a>[function <span class="apidocSignatureSpan">systemjs._nodeRequire.</span>resolve (request)](#apidoc.element.systemjs._nodeRequire.resolve)
- description and source-code
```javascript
function resolve(request) {
  return Module._resolveFilename(request, self);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.systemjs._nodeRequire.extensions"></a>[module systemjs._nodeRequire.extensions](#apidoc.module.systemjs._nodeRequire.extensions)



# <a name="apidoc.module.systemjs.registry"></a>[module systemjs.registry](#apidoc.module.systemjs.registry)

#### <a name="apidoc.element.systemjs.registry.delete"></a>[function <span class="apidocSignatureSpan">systemjs.registry.</span>delete (key)](#apidoc.element.systemjs.registry.delete)
- description and source-code
```javascript
delete = function (key) {
  var deleted = registryDelete.call(this, key);

  // also delete from register registry if linked
  if (records.hasOwnProperty(key) && !records[key].linkRecord)
    delete records[key];

  return deleted;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
