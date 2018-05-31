---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# MakerDAO Exchange Integration

[![tests][tests]][tests-url]
[![coverage][cover]][cover-url]

A toolkit for easy integration of MakerDAO smart contract functionality with 
external platforms. 

If you're a cryptocurrency exchange looking to add leveraged ETH positions through 
distributed DAI lending to your platform, you're in the right place.

This library aims to support a wide range of platform architectures; from fully 
decentralized with immediate on-chain settlement, to centralized exchange architectures 
with internal settlement services.

## Prerequisites

[![node][node]][node-url]
[![npm][npm]][npm-url]
      
- [Node.js](http://es6-features.org)

## Features

- [Webpack](https://webpack.js.org/guides) (v3.5.5)
    - [Webpack Dev Server](https://github.com/webpack/webpack-dev-server) (v2.7.1)
    - [Hot Module Replacement](https://webpack.js.org/concepts/hot-module-replacement)
    - [Clean Webpack Plugin](https://github.com/johnagan/clean-webpack-plugin) (v0.1.16)
- [ECMAScript 6](http://es6-features.org)
- [Babel](https://babeljs.io/docs/setup/#installation) (v6.26.0)
- [ESLint](https://eslint.org/docs/user-guide/getting-started) (v4.5.0)
- [Jest](https://facebook.github.io/jest/docs/en/getting-started.html) (v20.0.4)
- [Sass](http://sass-lang.com/guide)

## Start Dev Server

1. `git clone https://github.com/makerdao/makerdao-integration-poc`
2. Run `npm install`
3. Start the dev server using `npm start`
3. Open [http://localhost:9000](http://localhost:9000)


## Commands

- `npm start` - start the dev server
- `npm run build` - create build in `dist` folder
- `npm run lint` - run an ESLint check
- `npm run coverage` - run code coverage and generate report in the `coverage` folder
- `npm test` - run all tests
- `npm run test:watch` - run all tests in watch mode

## License
_makerdao-exchange-integration_ is available under MIT.

This project was built on the excellent [_webpack-es6-boilerplate_](https://github.com/jluccisano/webpack-es6-boilerplate).

[npm]: https://img.shields.io/badge/npm-5.3.0-blue.svg
[npm-url]: https://npmjs.com/

[node]: https://img.shields.io/node/v/webpack-es6-boilerplate.svg
[node-url]: https://nodejs.org

[tests]: http://img.shields.io/travis/jluccisano/webpack-es6-boilerplate.svg
[tests-url]: https://travis-ci.org/jluccisano/webpack-es6-boilerplate

[cover]: https://codecov.io/gh/jluccisano/webpack-es6-boilerplate/branch/master/graph/badge.svg
[cover-url]: https://codecov.io/gh/jluccisano/webpack-es6-boilerplate

# Use Maker.js in Your Project 

`npm install @makerdao/makerdao-exchange-integration`

Import the necessary modules in your JS code:

`import { Maker, ConfigFactory } from '@makerdao/makerdao-exchange-integration';`

Then create a connected instance of the Maker class and use it to call CDP methods:

```
async setupFunction() {
  const config = ConfigFactory.create('kovan');

  return await new Maker(config);
}

async someOtherFunction() {
  const maker = await setupFunction();
  const cdp = await maker.openCdp();

  return await cdp.lockEth();
}
```