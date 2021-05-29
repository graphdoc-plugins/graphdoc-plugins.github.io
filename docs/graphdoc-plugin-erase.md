<p align="center">
  <br/>
  <a href="https://graphdoc-plugins.github.io"><img src="erase/graphdoc-plugin-erase.png" alt=" "/></a>
</p>

<h1 align="center">GraphQL documentation erasing unwanted types using graphdoc</h1>

[![graphdoc-plugin-erase](https://badgen.net/badge/homepage/graphdoc-plugin-erase/blue)](https://graphdoc-plugins.github.io)
[![graphdoc-plugin-erase](https://badgen.net/badge/npm%20pack/graphdoc-plugin-erase/blue)](https://www.npmjs.com/package/graphdoc-plugin-erase)
[![ ](https://badgen.net/npm/v/graphdoc-plugin-erase)](https://www.npmjs.com/package/graphdoc-plugin-erase)
[![License](https://img.shields.io/github/license/mashape/apistatus.svg)](LICENSE.txt)
[![ ](https://badgen.net/badge/test/passing/green)](https://gmullerb.gitlab.io/graphdoc-plugin-erase/tests/tests_report.html)
[![ ](https://gitlab.com/gmullerb/graphdoc-plugin-erase/badges/master/coverage.svg)](https://gmullerb.gitlab.io/graphdoc-plugin-erase/coverage/index.html)
[![Github repo](https://badgen.net/badge/icon/github?icon=github&label)](https://github.com/gmullerb/graphdoc-plugin-erase)
[![Gitlab repo](https://badgen.net/badge/icon/gitlab?icon=gitlab&label)](https://gitlab.com/gmullerb/graphdoc-plugin-erase)

__________________

## Quick Start

1 . Add dependencies:

`package.json`:

```json
  "devDependencies": {
    "@2fd/graphdoc": "2.4.0",
    "graphdoc-plugin-erase": "1.0.1",
```

2 . If default options are not suitable, then Configure `graphdoc-plugin-erase`:

`package.json`:

```json
{
  "graphdoc-plugin-erase": {
    "eraseByNameRegex": "\\w*No",
    "eraseByKindRegex": "(?:UNION|SCALAR)"
  }
}
```

3 Use `graphdoc-plugin-erase`:

`package.json`:

```json
  "scripts": {
    "doc": "graphdoc -p graphdoc/../../graphdoc-plugin-erase -p graphdoc/plugins/default -s ./schema.graphql -o ./build/documentation"
  }
```

or if using `graphdoc-plugin-flexible` instead of graphdoc default plugins

```json
  "scripts": {
    "doc": "graphdoc -p graphdoc/../../graphdoc-plugin-erase -p graphdoc/../../graphdoc-plugin-flexible -s ./schema.graphql -o ./build/documentation"
  }
```

> `graphdoc/../../` this is required to get external plugins working in `graphdoc`.

__________________

## Goals

`graphdoc-plugin-erase` provides a way to use [`graphdoc`](https://www.npmjs.com/package/@2fd/graphdoc) and remove some types that are not required in the documentation, e.g. `__Directive`, `__EnumValue`, `__DirectiveLocation`, etc.

## Options

`package.json`:

(*default values*)

```json
{
  "graphdoc-plugin-erase": {
    "eraseByNameRegex": "^__",
    "eraseByKindRegex": "^$"
  }
}
```

* `eraseByNameRegex`: Regular Expression to be used to remove type based on `name`.
* `eraseByKindRegex`: Regular Expression to be used to remove type based on `kind`.

> `graphdoc-plugin-erase` plugin should be add before the plugins we want to have filtered types.

__________________

## Prerequisites

* [`"@2fd/graphdoc": "2.4.0"`](https://www.npmjs.com/package/@2fd/graphdoc/v/2.4.0).

> graphdoc can work with older versions of GraphQL (description syntax: #), and new versions (description syntax: """), [How to configure graphdoc](https://graphdoc-plugins.github.io/docs/how-to-configure-graphdoc.html).

__________________

## Main documentation

[Back to homepage](../README.md)
