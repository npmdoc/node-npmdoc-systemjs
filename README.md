# api documentation for  [systemjs (v0.20.12)](https://github.com/systemjs/systemjs#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-systemjs.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-systemjs) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-systemjs.svg)](https://travis-ci.org/npmdoc/node-npmdoc-systemjs)
#### Dynamic ES module loader

[![NPM](https://nodei.co/npm/systemjs.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/systemjs)

- [https://npmdoc.github.io/node-npmdoc-systemjs/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-systemjs/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-systemjs/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-systemjs/build/apidoc.html)

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
        "es-module-loader": "^2.1.5",
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
        "shasum": "135cc471280448453347829ebb9639a09a67f101",
        "tarball": "https://registry.npmjs.org/systemjs/-/systemjs-0.20.12.tgz"
    },
    "files": [
        "dist"
    ],
    "gitHead": "c484f143c552a5c5aba875b2089c21a733d50ca6",
    "homepage": "https://github.com/systemjs/systemjs#readme",
    "license": "MIT",
    "main": "dist/system.src.js",
    "maintainers": [
        {
            "name": "guybedford"
        }
    ],
    "name": "systemjs",
    "optionalDependencies": {},
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
    "version": "0.20.12"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
