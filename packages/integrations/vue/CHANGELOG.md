# @astrojs/vue

## 2.0.0-beta.1

### Major Changes

- [#5782](https://github.com/withastro/astro/pull/5782) [`1f92d64ea`](https://github.com/withastro/astro/commit/1f92d64ea35c03fec43aff64eaf704dc5a9eb30a) Thanks [@Princesseuh](https://github.com/Princesseuh)! - Remove support for Node 14. Minimum supported Node version is now >=16.12.0

- [#5806](https://github.com/withastro/astro/pull/5806) [`7572f7402`](https://github.com/withastro/astro/commit/7572f7402238da37de748be58d678fedaf863b53) Thanks [@matthewp](https://github.com/matthewp)! - Make astro a peerDependency of integrations

  This marks `astro` as a peerDependency of several packages that are already getting `major` version bumps. This is so we can more properly track the dependency between them and what version of Astro they are being used with.

### Patch Changes

- Updated dependencies [[`01f3f463b`](https://github.com/withastro/astro/commit/01f3f463bf2918b310d130a9fabbf3ee21d14029), [`1f92d64ea`](https://github.com/withastro/astro/commit/1f92d64ea35c03fec43aff64eaf704dc5a9eb30a), [`c2180746b`](https://github.com/withastro/astro/commit/c2180746b4f6d9ef1b6f86924f21f52cc6ab4e63), [`ae8a012a7`](https://github.com/withastro/astro/commit/ae8a012a7b6884a03c50494332ee37b4505c2c3b), [`cf2de5422`](https://github.com/withastro/astro/commit/cf2de5422c26bfdea4c75f76e57b57299ded3e3a), [`ec09bb664`](https://github.com/withastro/astro/commit/ec09bb6642064dbd7d2f3369afb090363ae18de2), [`665a2c222`](https://github.com/withastro/astro/commit/665a2c2225e42881f5a9550599e8f3fc1deea0b4), [`f7aa1ec25`](https://github.com/withastro/astro/commit/f7aa1ec25d1584f7abd421903fbef66b1c050e2a), [`302e0ef8f`](https://github.com/withastro/astro/commit/302e0ef8f5d5232e3348afe680e599f3e537b5c5), [`840412128`](https://github.com/withastro/astro/commit/840412128b00a04515156e92c314a929d6b94f6d), [`1f49cddf9`](https://github.com/withastro/astro/commit/1f49cddf9e9ffc651efc171b2cbde9fbe9e8709d), [`4a1cabfe6`](https://github.com/withastro/astro/commit/4a1cabfe6b9ef8a6fbbcc0727a0dc6fa300cedaa), [`c4b0cb8bf`](https://github.com/withastro/astro/commit/c4b0cb8bf2b41887d9106440bb2e70d421a5f481), [`23dc9ea96`](https://github.com/withastro/astro/commit/23dc9ea96a10343852d965efd41fe6665294f1fb), [`63a6ceb38`](https://github.com/withastro/astro/commit/63a6ceb38d88331451dca64d0034c7c58e3d26f1), [`52209ca2a`](https://github.com/withastro/astro/commit/52209ca2ad72a30854947dcb3a90ab4db0ac0a6f), [`2303f9514`](https://github.com/withastro/astro/commit/2303f95142aa740c99213a098f82b99dd37d74a0)]:
  - astro@2.0.0-beta.2

## 2.0.0-beta.0

### Major Changes

- [#5685](https://github.com/withastro/astro/pull/5685) [`f6cf92b48`](https://github.com/withastro/astro/commit/f6cf92b48317a19a3840ad781b77d6d3cae143bb) Thanks [@bluwy](https://github.com/bluwy)! - Upgrade to Vite 4. Please see its [migration guide](https://vitejs.dev/guide/migration.html) for more information.

## 1.2.2

### Patch Changes

- [#5571](https://github.com/withastro/astro/pull/5571) [`50ecb3005`](https://github.com/withastro/astro/commit/50ecb3005dae3d288e60c7a59c114d504193553b) Thanks [@matthewp](https://github.com/matthewp)! - Add primevue as an external Vue package

## 1.2.1

### Patch Changes

- [#5126](https://github.com/withastro/astro/pull/5126) [`850cc19fd`](https://github.com/withastro/astro/commit/850cc19fda8e092c1a5fcbd7abfe7c7a0e15629c) Thanks [@natemoo-re](https://github.com/natemoo-re)! - Automatically add `vuetify` to `vite.ssr.noExternal`

## 1.2.0

### Minor Changes

- [#5075](https://github.com/withastro/astro/pull/5075) [`d25f54cb9`](https://github.com/withastro/astro/commit/d25f54cb9306eea9ed0445af8f77604dacacad43) Thanks [@natemoo-re](https://github.com/natemoo-re)! - Add support for the `appEntrypoint` option, which accepts a root-relative path to an app entrypoint. The default export of this file should be a function that accepts a Vue `App` instance prior to rendering. This opens up the ability to extend the `App` instance with [custom Vue plugins](https://vuejs.org/guide/reusability/plugins.html).

  ```js
  // astro.config.mjs
  import { defineConfig } from 'astro/config';
  import vue from '@astrojs/vue';

  export default defineConfig({
    integrations: [
      vue({
        appEntrypoint: '/src/pages/_app',
      }),
    ],
  });
  ```

  ```js
  // src/pages/_app.ts
  import type { App } from 'vue';
  import i18nPlugin from '../plugins/i18n';

  export default function setup(app: App) {
    app.use(i18nPlugin, {
      /* options */
    });
  }
  ```

## 1.1.0

### Minor Changes

- [#4897](https://github.com/withastro/astro/pull/4897) [`fd9d323a6`](https://github.com/withastro/astro/commit/fd9d323a68c0f0cbb3b019e0a05e2c33450f3d33) Thanks [@bluwy](https://github.com/bluwy)! - Support Vue JSX

### Patch Changes

- [#4842](https://github.com/withastro/astro/pull/4842) [`812658ad2`](https://github.com/withastro/astro/commit/812658ad2ab3732a99e35c4fd903e302e723db46) Thanks [@bluwy](https://github.com/bluwy)! - Add missing dependencies, support strict dependency installation (e.g. pnpm)

## 1.0.2

### Patch Changes

- [#4706](https://github.com/withastro/astro/pull/4706) [`b0ee81d0a`](https://github.com/withastro/astro/commit/b0ee81d0a70d8301530c321b670ab784c9bc00a2) Thanks [@bholmesdev](https://github.com/bholmesdev)! - Fix Vue `script setup` with other renderers applied

## 1.0.1

### Patch Changes

- [#4639](https://github.com/withastro/astro/pull/4639) [`f08ca005e`](https://github.com/withastro/astro/commit/f08ca005e28cc7d279535680d5b44495877aa7b6) Thanks [@matthewp](https://github.com/matthewp)! - Mark vueperslides as a default noExternal

## 1.0.0

### Major Changes

- [`04ad44563`](https://github.com/withastro/astro/commit/04ad445632c67bdd60c1704e1e0dcbcaa27b9308) - > Astro v1.0 is out! Read the [official announcement post](https://astro.build/blog/astro-1/).

  **No breaking changes**. This package is now officially stable and compatible with `astro@1.0.0`!

## 0.5.0

### Minor Changes

- [#3570](https://github.com/withastro/astro/pull/3570) [`04070c0c1`](https://github.com/withastro/astro/commit/04070c0c12c00a3e17842ce48e36edc3f2c890a3) Thanks [@matthewp](https://github.com/matthewp)! - Bump to Vite 3!

## 0.4.1

### Patch Changes

- [#3937](https://github.com/withastro/astro/pull/3937) [`31f9c0bf0`](https://github.com/withastro/astro/commit/31f9c0bf029ffa4b470e620f2c32e1370643e81e) Thanks [@delucis](https://github.com/delucis)! - Roll back supported Node engines

## 0.4.0

### Minor Changes

- [#3914](https://github.com/withastro/astro/pull/3914) [`b48767985`](https://github.com/withastro/astro/commit/b48767985359bd359df8071324952ea5f2bc0d86) Thanks [@ran-dall](https://github.com/ran-dall)! - Rollback supported `node@16` version. Minimum versions are now `node@14.20.0` or `node@16.14.0`.

## 0.3.1

### Patch Changes

- [#3885](https://github.com/withastro/astro/pull/3885) [`bf5d1cc1e`](https://github.com/withastro/astro/commit/bf5d1cc1e71da38a14658c615e9481f2145cc6e7) Thanks [@delucis](https://github.com/delucis)! - Integration README fixes

## 0.3.0

### Minor Changes

- [#3871](https://github.com/withastro/astro/pull/3871) [`1cc5b7890`](https://github.com/withastro/astro/commit/1cc5b78905633608e5b07ad291f916f54e67feb1) Thanks [@natemoo-re](https://github.com/natemoo-re)! - Update supported `node` versions. Minimum versions are now `node@14.20.0` or `node@16.16.0`.

## 0.2.1

### Patch Changes

- [#3854](https://github.com/withastro/astro/pull/3854) [`b012ee55`](https://github.com/withastro/astro/commit/b012ee55b107dea0730286263b27d83e530fad5d) Thanks [@bholmesdev](https://github.com/bholmesdev)! - [astro add] Support adapters and third party packages

* [#3864](https://github.com/withastro/astro/pull/3864) [`f9ed77bb`](https://github.com/withastro/astro/commit/f9ed77bb0d71d1644d524547a24963210f4ecaff) Thanks [@Princesseuh](https://github.com/Princesseuh)! - Add entrypoints for editor support for Vue and Svelte (destined to be used by our language server)

## 0.2.0

### Minor Changes

- [#3652](https://github.com/withastro/astro/pull/3652) [`7373d61c`](https://github.com/withastro/astro/commit/7373d61cdcaedd64bf5fd60521b157cfa4343558) Thanks [@natemoo-re](https://github.com/natemoo-re)! - Adds support for passing named slots from `.astro` => framework components.

  Inside your components, use the built-in `slot` API as you normally would.

## 0.1.5

### Patch Changes

- [#3455](https://github.com/withastro/astro/pull/3455) [`e9a77d86`](https://github.com/withastro/astro/commit/e9a77d861907adccfa75811f9aaa555f186d78f8) Thanks [@natemoo-re](https://github.com/natemoo-re)! - Update client hydration to check for `ssr` attribute. Requires `astro@^1.0.0-beta.36`.

## 0.1.4

### Patch Changes

- [#3333](https://github.com/withastro/astro/pull/3333) [`ce6d7982`](https://github.com/withastro/astro/commit/ce6d79828250e9a3631778a37d43068cae04bb4f) Thanks [@FredKSchott](https://github.com/FredKSchott)! - Fix a vite peer dependency bug

## 0.1.3

### Patch Changes

- [`0c6bbee4`](https://github.com/withastro/astro/commit/0c6bbee4c95b50e5bd43675296511fbb5b985014) Thanks [@FredKSchott](https://github.com/FredKSchott)! - Republishing. No changes from v0.1.2.

## 0.1.2

### Patch Changes

- [#3143](https://github.com/withastro/astro/pull/3143) [`44e294c9`](https://github.com/withastro/astro/commit/44e294c9cbaf8f6bbccce8b956c7c53d37c15c70) Thanks [@tony-sull](https://github.com/tony-sull)! - `@astrojs/vue` integration supports custom vue compiler options

## 0.1.1

### Patch Changes

- [`815d62f1`](https://github.com/withastro/astro/commit/815d62f151a36fef7d09590d4962ca71bda61b32) Thanks [@FredKSchott](https://github.com/FredKSchott)! - no changes.

## 0.1.0

### Minor Changes

- [#2979](https://github.com/withastro/astro/pull/2979) [`9d7a4b59`](https://github.com/withastro/astro/commit/9d7a4b59b53f8cb274266f5036d1cef841750252) Thanks [@FredKSchott](https://github.com/FredKSchott)! - Welcome to the Astro v1.0.0 Beta! Read the [official announcement](https://astro.build/blog/astro-1-beta-release/) for more details.

## 0.0.2

### Patch Changes

- [#2885](https://github.com/withastro/astro/pull/2885) [`6b004363`](https://github.com/withastro/astro/commit/6b004363f99f27e581d1e2d53a2ebff39d7afb8a) Thanks [@bholmesdev](https://github.com/bholmesdev)! - Add README across Astro built-in integrations

* [#2847](https://github.com/withastro/astro/pull/2847) [`3b621f7a`](https://github.com/withastro/astro/commit/3b621f7a613b45983b090794fa7c015f23ed6140) Thanks [@tony-sull](https://github.com/tony-sull)! - Adds keywords to the official integrations to support discoverability on Astro's Integrations site

## 0.0.2-next.0

### Patch Changes

- [#2847](https://github.com/withastro/astro/pull/2847) [`3b621f7a`](https://github.com/withastro/astro/commit/3b621f7a613b45983b090794fa7c015f23ed6140) Thanks [@tony-sull](https://github.com/tony-sull)! - Adds keywords to the official integrations to support discoverability on Astro's Integrations site
