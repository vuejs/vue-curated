# vue-curated

This repository is the primary data source for the curated app. It has a [client](https://github.com/vuejs/vue-curated-client) and a [server](https://github.com/vuejs/vue-curated-server).

The list of curated packages are written in the [PACKAGES.md](./PACKAGES.md) markdown file. This file contains the data in a special format design to be still easily readable without parser.

## How to add a category

Each category is represented by a level-1 title and contains the packages until the next title. The goal is to have few high-quality choices so that developpers can quickly find the best package for their need.

Example:

```markdown
# Category label
```

## How to add a package

A package is a bullet-point line followed by some fields formatted in a particualiar way. It will be [parsed by the vue-curated app](https://github.com/vuejs/vue-curated-server/blob/master/src/utils/parse.js#L17).

The row just starts with a link to the package repository, whose label is used as the package name in the app.

Each field is separated by a comma `,` and the value is put after colons `:`.

Example:

```markdown
- [name](link), field1:value, field2:value, field3:value
```

Some fields can contain a list of values which are separated by a pipe `|` (without spaces).

Example:

```markdown
array_field:value1|value2|value3
```

### Supported fields

The package fields currently supported are: [Source](https://github.com/vuejs/vue-curated-server/blob/master/src/providers/github.js#L28)

- `vue` (array): list of supported Vue major versions. Recommended values: `1.0`, `2.0`. Example: `vue:1.0|2.0`
- `links` (array): list of useful links. Example: `links:[doc](https://doc.com/)|[demo](https://demo.com/)`.
- `status`: developpement status. Values: `dev` or `stable`. Example: `status:stable`.
- `badge`: special badge. Recommended values: `official`. Example: `badge:official`.


## Example

```markdown
# Core

- [vue](https://github.com/vuejs/vue), vue:1.0|2.0, links:[website](https://vuejs.org/)|[guide](https://vuejs.org/v2/guide/)|[api](https://vuejs.org/v2/api/)|[examples](https://vuejs.org/v2/examples/), badge:official, status:stable
```
