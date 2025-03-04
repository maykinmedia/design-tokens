# Maykin Design Tokens

[NL Design System](https://www.nldesignsystem.nl/) design token values for "the Maykin
theme".

[![NPM package](https://img.shields.io/npm/v/@maykinmedia/design-tokens.svg)](https://www.npmjs.com/package/@maykinmedia/design-tokens)

The Maykin theme is typically used in Demo environments for various projects that support
styling with NL Design System (community) components. It serves as the source of truth
for any theme/design choices.

## How it works

Specify the design tokens in JSON files, which are picked up and merged using the
[style-dictionary](https://www.npmjs.com/package/style-dictionary) library. The resulting packages
include various build targets, such as ES6 modules, CSS variables files, SASS vars... to be consumed
in downstream projects.

The draft [Design Token Format](https://design-tokens.github.io/community-group/format/) drives the
structure of these design tokens.

## Usage

**Using tokens**

If you are only _consuming_ the design tokens, the easiest integration path is adding the NPM
package as dependency to your project:

```bash
npm install --save-dev @maykinmedia/design-tokens
```

Then, import the desired build target artifact and run your usual build chain.

## Release flow

We don't let `npm` apply the git tags when releasing a new version, instead follow this process:

```bash
npm version minor  # or major or patch, depending on the nature of the changes
git commit -am ":bookmark: Bump to version <newVersion>"
git tag "<newVersion>"
git push origin main --tags
```

If you have PGP keys set up, you can use them for the git tag operation.

The CI pipeline will then publish the new version to npmjs.
