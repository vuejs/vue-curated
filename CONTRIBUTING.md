# Contributing Guidelines

The main objective of this repository is to setup a **curated** list of packages that might be helpful for developers.
As such, each package in this list should be high quality and meet a number of requirements.

**You can also contribute to the [client app](https://github.com/vuejs/vue-curated-client) and the [graphql server](https://github.com/vuejs/vue-curated-server)!**

## Minimal Requirements

### Find and explain a common use case

The package should solve a reasonably common use case that Vue devlopers might encounter when creating an app.
If it is too 'niche', it will won't make into the list.

- In the PR, explain what is the use case solved by your package.

### Provide a Demo

You need to provide a demo showcasing the package so it can easily be tested by potential users.

- Add a link to a demo project repository that shows the package in action.
- It should be a focused demo on this specific package (don't use one demo for multiple packages).
- If possible, you should also add a link to a live demo that can be played in the browser.
- Get a core Vue member/contributor to test the demo project and verify it is a good solution for the use case. Don't hesitate to ask for advices!

### Document the package

Documenation is essential for the user to understand what your package does and how to use it.

- The repository should have either a documentation on the `README.md` file or a dedicated website (in this case, provide the link to it).
- It should be at least available in English.
- It should have a **complete** API reference (if it makes sens to have one).

### Distribution

Most of the users will want to use your package directly, without having to setup specific build tools.

- Make sure you compile the package to a UMD distribution file so that it can at least be imported in a webpack project.
*In rollup, use the `umd` format.*
*Put the path to this file in the `main` field in `package.json`.*

- You can also compile to an ES module that can be consumed by webpack 2+ to take advantage of tree shaking.
*In rollup, use the `es` format.*
*Put the path to this file in the `module` field in `package.json`.*

- You can also optionally provide compiled files to be used directly in the browser via a script tag.
*In rollup, use the `iife` format.*
*Put the path to this file in the `unpkg` field in `package.json`.*

### Tests

Having tests help make your code more stable and give users more confidence when using it.

- Write at least unit tests
- It should have a reasonable coverage

### Visual Quality

Having good visuals give the viewer good impression of both your package and the Vue ecosystem.

- If you package is visual (for example a component), it should be reasonably polished and have a nice visual quality.
- Put a screenshot in the `README.md` file so user will see how it look like at a glance.

### Activity

Keeping the repository maintained is also essential for the sustainability of the package and for the user confidence.

- Have active maintainers on the repository

## Adding a new package

If you are sure the minimal requirements are met, open a PR by [editing the PACKAGES.md file](https://github.com/vuejs/vue-curated/edit/master/PACKAGES.md) and read the following guide.

### How to add a category

Each category is represented by a level-1 title and contains the packages until the next title.

Example:

```markdown
# Category label
```

### How to add a package

A package is a bullet-point line followed by some fields formatted in a particular way. It will be [parsed by the vue-curated app](https://github.com/vuejs/vue-curated-server/blob/master/src/utils/parse.js#L17).

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

#### Supported fields

The package fields currently supported are: [Source](https://github.com/vuejs/vue-curated-server/blob/master/src/providers/github.js#L28)

- `vue` (array): list of supported Vue major versions. Recommended values: `1.0`, `2.0`. Example: `vue:1.0|2.0`
- `links` (array): list of useful links. Example: `links:[doc](https://doc.com/)|[demo](https://demo.com/)`.
- `status`: development status. Values: `dev` or `stable`. Example: `status:stable`.
- `badge`: special badge. Recommended values: `official`. Example: `badge:official`.


### Example

```markdown
# Core

- [vue](https://github.com/vuejs/vue), vue:1.0|2.0, links:[website](https://vuejs.org/)|[guide](https://vuejs.org/v2/guide/)|[api](https://vuejs.org/v2/api/)|[examples](https://vuejs.org/v2/examples/), badge:official, status:stable
```

