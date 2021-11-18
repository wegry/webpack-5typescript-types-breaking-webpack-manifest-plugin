# webpack-5typescript-types-breaking-webpack-manifest-plugin

Running `yarn tsc ./webpack.config.ts` causes tsc to fail with 

```
yarn tsc ./webpack.config.ts
yarn run v1.22.17
$ /Users/zw/manifest-plugin-broken/node_modules/.bin/tsc ./webpack.config.ts
node_modules/webpack-manifest-plugin/dist/helpers.d.ts:1:8 - error TS1259: Module '"/Users/zw/manifest-plugin-broken/node_modules/webpack/types"' can only be default-imported using the 'esModuleInterop' flag

1 import webpack, { AssetInfo, Chunk } from 'webpack';
         ~~~~~~~

  node_modules/webpack/types.d.ts:12708:1
    12708 export = exports;
          ~~~~~~~~~~~~~~~~~
    This module is declared with using 'export =', and can only be used with a default import when using the 'esModuleInterop' flag.

node_modules/webpack-manifest-plugin/dist/helpers.d.ts:19:18 - error TS2430: Interface 'ProperChunk' incorrectly extends interface 'Chunk'.
  Types of property 'auxiliaryFiles' are incompatible.
    Type 'any[]' is missing the following properties from type 'Set<string>': add, clear, delete, has, and 2 more.

19 export interface ProperChunk extends Chunk {
                    ~~~~~~~~~~~

node_modules/webpack-manifest-plugin/dist/hooks.d.ts:1:8 - error TS1259: Module '"/Users/zw/manifest-plugin-broken/node_modules/webpack/types"' can only be default-imported using the 'esModuleInterop' flag

1 import webpack, { Compiler, Module } from 'webpack';
         ~~~~~~~

  node_modules/webpack/types.d.ts:12708:1
    12708 export = exports;
          ~~~~~~~~~~~~~~~~~
    This module is declared with using 'export =', and can only be used with a default import when using the 'esModuleInterop' flag.

webpack.config.ts:2:8 - error TS1259: Module '"/Users/zw/manifest-plugin-broken/node_modules/webpack/types"' can only be default-imported using the 'esModuleInterop' flag

2 import webpack from "webpack";
         ~~~~~~~

  node_modules/webpack/types.d.ts:12708:1
    12708 export = exports;
          ~~~~~~~~~~~~~~~~~
    This module is declared with using 'export =', and can only be used with a default import when using the 'esModuleInterop' flag.


Found 4 errors.

error Command failed with exit code 2.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
```
