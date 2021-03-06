# Change Log

## 1.5.3

### Patch Changes

- [`7854971e`](https://github.com/frontity/frontity/commit/7854971eaefa665dc5d77b0b91129c1495b0dab4) [#354](https://github.com/frontity/frontity/pull/354) Thanks [@luisherranz](https://github.com/luisherranz)! - Recommend mars-theme to beginners, because it's simpler and has more comments.
- Updated dependencies [[`34b37ec8`](https://github.com/frontity/frontity/commit/34b37ec84bc4c387754f241ea56fd5eb8b13b14d), [`ffdebed8`](https://github.com/frontity/frontity/commit/ffdebed862541d39f06305137a5cbcdec8f4ee66), [`43cf2305`](https://github.com/frontity/frontity/commit/43cf230526ed810c3778c830e41eb26ef2c53bc3), [`ac8832b1`](https://github.com/frontity/frontity/commit/ac8832b1be702f8bf4e00a8c9bc4ec3a32a3e236)]:
  - @frontity/connect@1.0.5
  - @frontity/core@1.5.2
  - @frontity/error@0.1.0

## 1.5.2

### Patch Changes

- [`b3225692`](https://github.com/frontity/frontity/commit/b32256929351b66647f64900cc59862ee7c702a7) [#329](https://github.com/frontity/frontity/pull/329) Thanks [@luisherranz](https://github.com/luisherranz)! - Fix missing `he` dependency for the `decode` function.

* [`b3225692`](https://github.com/frontity/frontity/commit/b32256929351b66647f64900cc59862ee7c702a7) [#329](https://github.com/frontity/frontity/pull/329) Thanks [@luisherranz](https://github.com/luisherranz)! - Remove `@frontity/connect` from dependencies to avoid multiple imports and fix the problem people is having when they are updating Frontity.

- [`f7418071`](https://github.com/frontity/frontity/commit/f741807197c4cda5df2e43f5496a121428d309bf) [#319](https://github.com/frontity/frontity/pull/319) Thanks [@luisherranz](https://github.com/luisherranz)! - Correctly import type declarations from the @frontity/type-declarations package.
- Updated dependencies [[`f7418071`](https://github.com/frontity/frontity/commit/f741807197c4cda5df2e43f5496a121428d309bf), [`897780d5`](https://github.com/frontity/frontity/commit/897780d549b56cc6ddb1c06b107b570114ff5587), [`f7418071`](https://github.com/frontity/frontity/commit/f741807197c4cda5df2e43f5496a121428d309bf)]:
  - @frontity/type-declarations@1.1.0
  - @frontity/types@1.3.0

## 1.5.1

### Patch Changes

- [`80fb05f2`](https://github.com/frontity/frontity/commit/80fb05f237a3267ad27d131753ff82ced2d3d305) [#325](https://github.com/frontity/frontity/pull/325) Thanks [@luisherranz](https://github.com/luisherranz)! - The `decode` function now properly decodes numeric entities.

* [`74eb448e`](https://github.com/frontity/frontity/commit/74eb448e359e1e33b1bd1deb52932850253763f4) [#323](https://github.com/frontity/frontity/pull/323) Thanks [@luisherranz](https://github.com/luisherranz)! - Fix missing typescript dependency in the frontity package. This package is the one responsible to inject typescript in a Frontity Project and the Frontity CLI.

## 1.5.0

### Minor Changes

- [`495771f8`](https://github.com/frontity/frontity/commit/495771f83951f192f92d3162221cedc9b791e399) [#302](https://github.com/frontity/frontity/pull/302) Thanks [@michalczaplinski](https://github.com/michalczaplinski)! - Add a new `decode` function to 'frontity', which unescapes the HTML.

  This replaces the `decode` function previously in `html2react`.

  This is necessary because some of the content fro WP API can come as escaped HTML entities and we want to render it straight into react components.

- [`80c1aa3a`](https://github.com/frontity/frontity/commit/80c1aa3aee6cf04f46d6fa1a409abfcae2c511cc) [#288](https://github.com/frontity/frontity/pull/288) Thanks [@michalczaplinski](https://github.com/michalczaplinski)! - Add a new option `--theme` which allows specifying the starter theme on the command line. If the theme is not specified, the user can pick a theme from an interactive prompt.

### Patch Changes

- [`417f2b0f`](https://github.com/frontity/frontity/commit/417f2b0f0b6f5626be253eb3f1be2daf257b71ef) [#305](https://github.com/frontity/frontity/pull/305) Thanks [@michalczaplinski](https://github.com/michalczaplinski)! - Improve the performance of the `decode` function. Now it works like this:

  - It does a regexp to check if there are HTML entities.
  - It does a partial replacement of common entities using the [`simple-entity-decode`](https://github.com/humanmade/simple-entity-decode) package.
  - It does a new regexp check to see if there is any entity left.
  - Finally, it does a full replacement of all entities using:
    - [`he`](https://www.npmjs.com/package/he) in the server, which works great but it is a [big library](https://bundlephobia.com/result?p=he@1.2.0) and therefore we don't want to include it in the client.
    - `DomParser` in the client, which is [safe to use](https://stackoverflow.com/questions/1912501/unescape-html-entities-in-javascript/34064434#34064434).- Updated dependencies [[`15a8b582`](https://github.com/frontity/frontity/commit/15a8b582bc38d15f49b80dbbc86884d3ba607c4d), [`495771f8`](https://github.com/frontity/frontity/commit/495771f83951f192f92d3162221cedc9b791e399), [`696dec11`](https://github.com/frontity/frontity/commit/696dec11bb8d32f0821cca3f5ce39e27c42d60b6), [`a4e9e579`](https://github.com/frontity/frontity/commit/a4e9e579a6306c87cb91f33e635201387bd405ea), [`ed257939`](https://github.com/frontity/frontity/commit/ed257939010b5a1ed79562439fed426843649af5)]:
  - @frontity/core@1.5.0
  - @frontity/connect@1.0.4
  - @frontity/types@1.2.0

## 1.4.4

### Patch Changes

- [`2517cfd`](https://github.com/frontity/frontity/commit/2517cfd64620b61ac0bd1f1f245a4b65de8d2cbe) [#243](https://github.com/frontity/frontity/pull/243) Thanks [@luisherranz](https://github.com/luisherranz)! - Remove the typescript option from `frontity create-package` because it is not implemented yet. Once it is implemented, we can add it back.

## [1.4.3](https://github.com/frontity/frontity/compare/frontity@1.4.2...frontity@1.4.3) (2019-12-10)

**Note:** Version bump only for package frontity

## [1.4.2](https://github.com/frontity/frontity/compare/frontity@1.4.1...frontity@1.4.2) (2019-11-04)

### Bug Fixes

- **core:** add labels and source maps ([#227](https://github.com/frontity/frontity/issues/227)) ([d5af653](https://github.com/frontity/frontity/commit/d5af653))

## [1.4.1](https://github.com/frontity/frontity/compare/frontity@1.4.0...frontity@1.4.1) (2019-10-10)

**Note:** Version bump only for package frontity

# [1.4.0](https://github.com/frontity/frontity/compare/frontity@1.3.1...frontity@1.4.0) (2019-10-02)

### Bug Fixes

- **typescript:** update to latest version ([a89b11c](https://github.com/frontity/frontity/commit/a89b11c))

### Features

- **cli:** add --dont-open-browser option to dev ([6ae037c](https://github.com/frontity/frontity/commit/6ae037c))
- **frontity:** add create-package command ([#218](https://github.com/frontity/frontity/issues/218)) ([eac88fd](https://github.com/frontity/frontity/commit/eac88fd))

## [1.3.1](https://github.com/frontity/frontity/compare/frontity@1.3.0...frontity@1.3.1) (2019-09-10)

### Bug Fixes

- **core:** remove componentWillMount warning with react-helmet-async ([0ea885b](https://github.com/frontity/frontity/commit/0ea885b))
- **webpack:** add support for images in Windows ([#196](https://github.com/frontity/frontity/issues/196)) ([00aa4e1](https://github.com/frontity/frontity/commit/00aa4e1))

# [1.3.0](https://github.com/frontity/frontity/compare/frontity@1.2.2...frontity@1.3.0) (2019-08-12)

### Features

- **frontity:** expose fetch and URL from frontity package ([#168](https://github.com/frontity/frontity/issues/168)) ([235c465](https://github.com/frontity/frontity/commit/235c465))

## [1.2.2](https://github.com/frontity/frontity/compare/frontity@1.2.1...frontity@1.2.2) (2019-07-12)

**Note:** Version bump only for package frontity

## [1.2.1](https://github.com/frontity/frontity/compare/frontity@1.2.0...frontity@1.2.1) (2019-07-04)

### Bug Fixes

- **cli:** didyomean dependency is in the wrong package.json ([d0e06b1](https://github.com/frontity/frontity/commit/d0e06b1))

# [1.2.0](https://github.com/frontity/frontity/compare/frontity@1.1.0...frontity@1.2.0) (2019-07-04)

### Bug Fixes

- **cli:** add description to target option ([#154](https://github.com/frontity/frontity/issues/154)) ([f8fa4cd](https://github.com/frontity/frontity/commit/f8fa4cd))

### Features

- **cli:** suggest matching commands if the user mistypes ([#155](https://github.com/frontity/frontity/issues/155)) ([7f3c24b](https://github.com/frontity/frontity/commit/7f3c24b))

# [1.1.0](https://github.com/frontity/frontity/compare/frontity@1.0.6...frontity@1.1.0) (2019-07-01)

### Bug Fixes

- **cli:** fixes misleading usage message ([#149](https://github.com/frontity/frontity/issues/149)) ([386c0cc](https://github.com/frontity/frontity/commit/386c0cc)), closes [#148](https://github.com/frontity/frontity/issues/148)
- **frontity-cli:** show npx version in the environment info ([#152](https://github.com/frontity/frontity/issues/152)) ([4a7e269](https://github.com/frontity/frontity/commit/4a7e269))

### Features

- **cli:** shows up help if no arguments were provided ([#150](https://github.com/frontity/frontity/issues/150)) ([6a6eabb](https://github.com/frontity/frontity/commit/6a6eabb)), closes [#146](https://github.com/frontity/frontity/issues/146)
- **cli:** warn the user on providing unknown commands ([#151](https://github.com/frontity/frontity/issues/151)) ([8d0d753](https://github.com/frontity/frontity/commit/8d0d753)), closes [#147](https://github.com/frontity/frontity/issues/147)
- **frontity-cli:** add command to get environment information ([#143](https://github.com/frontity/frontity/issues/143)) ([1795f1d](https://github.com/frontity/frontity/commit/1795f1d))

## [1.0.6](https://github.com/frontity/frontity/compare/frontity@1.0.5...frontity@1.0.6) (2019-06-20)

### Bug Fixes

- **create:** finally fixing the create command from berlin ([f9e650d](https://github.com/frontity/frontity/commit/f9e650d))

## [1.0.5](https://github.com/frontity/frontity/compare/frontity@1.0.4...frontity@1.0.5) (2019-06-20)

### Bug Fixes

- **frontity:** add positive tests, fix special chars ([13f9412](https://github.com/frontity/frontity/commit/13f9412))

## [1.0.4](https://github.com/frontity/frontity/compare/frontity@1.0.3...frontity@1.0.4) (2019-06-20)

### Bug Fixes

- **frontity:** fix package name validation ([fb26305](https://github.com/frontity/frontity/commit/fb26305))

## [1.0.3](https://github.com/frontity/frontity/compare/frontity@1.0.2...frontity@1.0.3) (2019-06-19)

### Bug Fixes

- **frontity-cli:** add html2react to create command ([c3a491d](https://github.com/frontity/frontity/commit/c3a491d))

## [1.0.2](https://github.com/frontity/frontity/compare/frontity@1.0.1...frontity@1.0.2) (2019-06-19)

**Note:** Version bump only for package frontity

## [1.0.1](https://github.com/frontity/frontity/compare/frontity@1.0.0...frontity@1.0.1) (2019-06-05)

### Bug Fixes

- **frontity:** update react helmet ([2e6bb9d](https://github.com/frontity/frontity/commit/2e6bb9d))

# [1.0.0](https://github.com/frontity/frontity/compare/frontity@0.2.17...frontity@1.0.0) (2019-06-05)

### Features

- **frontity:** push to 1.0.0 ([97d6a0b](https://github.com/frontity/frontity/commit/97d6a0b))

### BREAKING CHANGES

- **frontity:** push frontity package to 1.0.0

## [0.2.17](https://github.com/frontity/frontity/compare/frontity@0.2.16...frontity@0.2.17) (2019-06-05)

### Bug Fixes

- **all:** update typscript and fix some keywords ([1fe5fec](https://github.com/frontity/frontity/commit/1fe5fec))
- **wp-source:** change apiUrl for api ([26947e7](https://github.com/frontity/frontity/commit/26947e7))

## [0.2.16](https://github.com/frontity/frontity/compare/frontity@0.2.15...frontity@0.2.16) (2019-06-05)

### Bug Fixes

- **connect:** include scheduler to fix batching in async events ([b4aa340](https://github.com/frontity/frontity/commit/b4aa340))

## [0.2.15](https://github.com/frontity/frontity/compare/frontity@0.2.14...frontity@0.2.15) (2019-05-29)

**Note:** Version bump only for package frontity

## [0.2.14](https://github.com/frontity/frontity/compare/frontity@0.2.13...frontity@0.2.14) (2019-05-28)

### Bug Fixes

- **frontity:** add compiler options for ts-node in the register function ([#96](https://github.com/frontity/frontity/issues/96)) ([9960e7e](https://github.com/frontity/frontity/commit/9960e7e))

## [0.2.13](https://github.com/frontity/frontity/compare/frontity@0.2.12...frontity@0.2.13) (2019-05-27)

**Note:** Version bump only for package frontity

## [0.2.12](https://github.com/frontity/frontity/compare/frontity@0.2.11...frontity@0.2.12) (2019-05-27)

### Bug Fixes

- **frontity:** add missing settings and other stuff ([#91](https://github.com/frontity/frontity/issues/91)) ([159e5f7](https://github.com/frontity/frontity/commit/159e5f7))

## [0.2.11](https://github.com/frontity/frontity/compare/frontity@0.2.10...frontity@0.2.11) (2019-05-17)

**Note:** Version bump only for package frontity

## [0.2.10](https://github.com/frontity/frontity/compare/frontity@0.2.9...frontity@0.2.10) (2019-05-17)

**Note:** Version bump only for package frontity

## [0.2.9](https://github.com/frontity/frontity/compare/frontity@0.2.8...frontity@0.2.9) (2019-05-16)

**Note:** Version bump only for package frontity

## [0.2.8](https://github.com/frontity/frontity/compare/frontity@0.2.7...frontity@0.2.8) (2019-05-16)

### Bug Fixes

- **webpack:** fix bug with publicPath and dynamic imports ([#63](https://github.com/frontity/frontity/issues/63)) ([c6e99f5](https://github.com/frontity/frontity/commit/c6e99f5))

## [0.2.7](https://github.com/frontity/frontity/compare/frontity@0.2.6...frontity@0.2.7) (2019-05-16)

### Bug Fixes

- **core-scripts:** fixes texts and core dependencies ([faf8761](https://github.com/frontity/frontity/commit/faf8761))

## [0.2.6](https://github.com/frontity/frontity/compare/frontity@0.2.5...frontity@0.2.6) (2019-05-16)

### Bug Fixes

- **commands:** fix path to read package.json ([b8b5d1d](https://github.com/frontity/frontity/commit/b8b5d1d))

## [0.2.5](https://github.com/frontity/frontity/compare/frontity@0.2.4...frontity@0.2.5) (2019-05-16)

### Bug Fixes

- **cli:** fix inquirer dependency ([90a9198](https://github.com/frontity/frontity/commit/90a9198))

## [0.2.4](https://github.com/frontity/frontity/compare/frontity@0.2.3...frontity@0.2.4) (2019-05-16)

**Note:** Version bump only for package frontity

## [0.2.3](https://github.com/frontity/frontity/compare/frontity@0.2.2...frontity@0.2.3) (2019-05-15)

**Note:** Version bump only for package frontity

## [0.2.2](https://github.com/frontity/frontity/compare/frontity@0.2.1...frontity@0.2.2) (2019-05-15)

**Note:** Version bump only for package frontity

## [0.2.1](https://github.com/frontity/frontity/compare/frontity@0.2.0...frontity@0.2.1) (2019-05-15)

**Note:** Version bump only for package frontity

# [0.2.0](https://github.com/frontity/frontity/compare/frontity@0.1.4...frontity@0.2.0) (2019-05-15)

### Features

- **frontity:** use the frontity package as interface for the core packages ([#48](https://github.com/frontity/frontity/issues/48)) ([429e795](https://github.com/frontity/frontity/commit/429e795))

## [0.1.4](https://github.com/frontity/frontity/compare/frontity@0.1.3...frontity@0.1.4) (2019-03-27)

**Note:** Version bump only for package frontity

## [0.1.3](https://github.com/frontity/frontity/compare/frontity@0.1.2...frontity@0.1.3) (2019-02-27)

**Note:** Version bump only for package frontity

## [0.1.2](https://github.com/frontity/frontity/compare/frontity@0.1.1...frontity@0.1.2) (2019-02-27)

### Bug Fixes

- **frontity:** add exclamation mark ([c2bb4f4](https://github.com/frontity/frontity/commit/c2bb4f4))

## 0.1.1 (2019-02-27)

**Note:** Version bump only for package frontity
