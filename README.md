# npmtest-mongo-express

#### basic test coverage for  mongo-express (v0.39.2)  [![npm package](https://img.shields.io/npm/v/npmtest-mongo-express.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-mongo-express) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-mongo-express.svg)](https://travis-ci.org/npmtest/node-npmtest-mongo-express)

#### Web-based admin interface for MongoDB

[![NPM](https://nodei.co/npm/mongo-express.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/mongo-express)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-mongo-express/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-mongo-express/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-mongo-express/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-mongo-express/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-mongo-express/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-mongo-express/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-mongo-express/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-mongo-express/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-mongo-express/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-mongo-express/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-mongo-express/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-mongo-express/build/test-report.html](https://npmtest.github.io/node-npmtest-mongo-express/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-mongo-express/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-mongo-express/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-mongo-express/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-mongo-express/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-mongo-express/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-mongo-express/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-mongo-express/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-mongo-express/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "version": "0.39.2",
    "author": "https://github.com/mongo-express",
    "name": "mongo-express",
    "description": "Web-based admin interface for MongoDB",
    "keywords": [
        "admin",
        "administration",
        "collection",
        "database",
        "GUI",
        "interface",
        "manage",
        "manage-mongo",
        "mongo",
        "mongodb",
        "phpmyadmin",
        "UI",
        "web-based"
    ],
    "bin": {
        "mongo-express": "./app.js"
    },
    "repository": {
        "type": "git",
        "url": "git://github.com/mongo-express/mongo-express.git"
    },
    "dependencies": {
        "async": "2.0.1",
        "basic-auth-connect": "^1.0.0",
        "body-parser": "1.15.2",
        "busboy": "^0.2.13",
        "cli-color": "^1.1.0",
        "commander": "^2.9.0",
        "cookie-parser": "1.4.3",
        "cross-env": "^3.2.4",
        "csurf": "1.9.0",
        "errorhandler": "1.4.3",
        "express": "4.14.0",
        "express-session": "1.14.1",
        "flat": "^2.0.1",
        "gridfs-stream": "^1.1.1",
        "json2csv": "^3.7.1",
        "lodash": "~4.17.4",
        "method-override": "2.3.6",
        "mongodb": "2.2.24",
        "morgan": "1.7.0",
        "serve-favicon": "2.3.0",
        "swig-templates": "2.0.2",
        "update-notifier": "1.0.2"
    },
    "devDependencies": {
        "assets-webpack-plugin": "^3.5.1",
        "babel-core": "^6.24.1",
        "babel-loader": "^6.3.2",
        "babel-preset-es2015": "^6.24.1",
        "bootstrap": "^3.3.7",
        "chai": "3.5.0",
        "clean-webpack-plugin": "^0.1.15",
        "codemirror": "^5.23.0",
        "concurrently": "^3.3.0",
        "copy-webpack-plugin": "^4.0.1",
        "eslint": "~3.9.1",
        "eslint-config-airbnb-base": "^8.0.0",
        "eslint-plugin-import": "^1.16.0",
        "eslint-plugin-lodash": "^2.3.5",
        "jquery": "^3.1.1",
        "mocha": "3.0.2",
        "nodemon": "^1.11.0",
        "pre-commit": "1.1.3",
        "renderjson": "dozoisch/renderjson#cd0ef870c1298d53f09555da54e4bf57a0d21414",
        "supertest": "^3.0.0",
        "webpack": "^2.4.1"
    },
    "engines": {
        "node": ">=4.0.0",
        "npm": ">=3.0.0"
    },
    "license": "MIT",
    "scripts": {
        "lint": "eslint .",
        "start": "cross-env NODE_ENV=production node app",
        "start-dev": "concurrently --kill-others \"nodemon app\" \"npm run build-dev\"",
        "build-dev": "webpack --watch",
        "build": "cross-env NODE_ENV=production webpack",
        "test": "npm run mocha && npm run lint",
        "mocha": "cross-env NODE_ENV=test mocha",
        "test-watch": "cross-env NODE_ENV=test mocha --watch --reporter spec",
        "prepublish": "npm run build"
    },
    "pre-commit": [
        "test"
    ],
    "main": "./middleware"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
