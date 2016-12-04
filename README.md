eslint-config-wework
================

[![Libraries.io for GitHub][librariesio-image]][librariesio-url]
[![NPM version][npm-version-image]][npm-url]
[![NPM downloads][npm-downloads-image]][npm-url]
[![MIT License][license-image]][license-url]


>Shared ESLint configuration for WeWork projects

# Introduction

ESLint config for WeWork projects. This is an extension of `eslint-config-airbnb` and also provides `react` and `imports` presets.


# Usage

### Install:

```
npm install eslint eslint-config-wework eslint-config-airbnb eslint-plugin-react eslint-plugin-import eslint-plugin-jsx-a11y --save
```

Ideally, this package would be able to use its own dependencies, but ESLint does not support that at this time. For now, consumers need to install all of the above.

Note: make sure the versions of the above packages that are installed satisfy this package's `peerDependencies`, otherwise you might see inconsistent behavior.

### Configure:

First, `touch .eslintrc` if you don't already have one.

Then update it to look like the following:

```
{
  "root": true,
  "extends": [
    "wework"
  ],
  "rules": {
    # Override preset rules here
  },
}
```

### React:
To enable React-specific rules, extend `wework/react`:

```
{
  "root": true,
  "extends": [
    "wework",
    "wework/react"
  ],
  "rules": {
    # Override preset rules here
  },
}
```

### Imports:
To enable linting of ES2015+ (ES6+) import/export syntax, and prevent issues with misspelling of file paths and import names, extend `wework/imports`:

```
{
  "root": true,
  "extends": [
    "wework",
    "wework/react",
    "wework/imports"
  ],
  "rules": {
    # Override preset rules here
  },
}
```

# Development

1. Checkout this repo
2. Make changes in a feature branch and open a PR to `master`

The purpose of this package is to define and enforce code style in JavaScript code. With that in mind please be mindful when proposing changes, explain your reasoning and consider other users.

# npm scripts

Target | Behavior
------------ | -------------
**`npm run security-scan`** | (*Run as a git pre-push hook*) Checks npm dependencies for security vulnerabilities
**`npm run release <version>`** | Generates a changelog, updates package version, tags and pushes via [`np`](https://www.npmjs.com/package/np). This should only be run on an up-to-date `master` by a maintainer of this package. <br /><br />Version can be a semver level: `patch | minor | major | prepatch | preminor | premajor | prerelease`, or a valid semver version: `1.2.3`.

**`npm run` will list all npm scripts**


[npm-url]: https://npmjs.org/package/eslint-config-wework
[npm-version-image]: http://img.shields.io/npm/v/eslint-config-wework.svg?style=flat-square
[npm-downloads-image]: http://img.shields.io/npm/dm/eslint-config-wework.svg?style=flat-square

[license-url]: LICENSE
[license-image]: http://img.shields.io/badge/license-MIT-000000.svg?style=flat-square

[librariesio-url]: https://libraries.io/npm/eslint-config-wework
[librariesio-image]: https://img.shields.io/librariesio/github/wework/eslint-config-wework.svg?maxAge=2592000
