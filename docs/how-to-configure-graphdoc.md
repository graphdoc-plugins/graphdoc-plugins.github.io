# How to configure graphdoc

## Old GraphQL

For old GraphQL nothing special have to be done, but the following configuration can be also applied.

## New GraphQL

To avoid getting the following error:

```sh
 ✗ Syntax Error GraphQL (1:1) Unexpected String

1: """
   ^
2: ...

```

It is necessary to override `graphql` version dependency for `graphdoc` package.

## yarn

* Use `yarn` `resolutions`:

```json
  "resolutions": {
    "@2fd/graphdoc/**/graphql": "15.5.0"
  }
```

then `package.json` will result in something like:

```json
  "devDependencies": {
    "@2fd/graphdoc": "2.4.0",
    "graphdoc-plugin-erase" :"1.0.1",
    "graphdoc-plugin-flexible": "1.0.2",
    "graphdoc-plugin-operations": "2.0.0",
    "graphdoc-plugin-schema": "2.0.0",
    "yarn": "^1.22.10"
  },
  "resolutions": {
    "@2fd/graphdoc/**/graphql": "15.5.0"
  },
```

### Online Examples

* Pokemon GraphQL schema: [Project](https://github.com/gmullerb/base-graphdoc-yarn) and [Online generated documentation](https://gmullerb.gitlab.io/base-graphdoc-yarn).

## npm

`npm` has not an easy solution yet defined at the core, so use [`npm-force-resolutions`](https://www.npmjs.com/package/npm-force-resolutions):

* `npm-force-resolutions` provides a similar `resolutions` config field:

```json
  "resolutions": {
    "graphql": "15.5.0"
  }
```

then `package.json` will result in something like:

```json
  "devDependencies": {
    "@2fd/graphdoc": "2.4.0",
    "graphdoc-plugin-erase" :"1.0.1",
    "graphdoc-plugin-flexible": "1.0.2",
    "graphdoc-plugin-operations": "2.0.0",
    "graphdoc-plugin-schema": "2.0.0",
    "yarn": "^1.22.10"
  },
  "resolutions": {
    "@2fd/graphdoc/**/graphql": "15.5.0"
  },,
  "scripts": {
    "preinstall": "npx npm-force-resolutions",
    "doc": "graphdoc -p graphdoc/../../graphdoc-plugin-erase -p graphdoc/../../graphdoc-plugin-operations -p graphdoc/../../graphdoc-plugin-schema -p graphdoc/../../graphdoc-plugin-flexible -s ./src/schema.graphql -t ./template -o ./docs -f -v"
  }
```

> note the `preinstall` script.

### Online Examples

* Github GraphQL schema: [Project](https://github.com/gmullerb/base-graphdoc-npm) and [Online generated documentation](https://gmullerb.gitlab.io/base-graphdoc-npm).

__________________

## Main documentation

[Back to homepage](../README.md)
