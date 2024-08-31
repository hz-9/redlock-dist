# @hz-9/redlock-dist

Forked from [redlock](https://www.npmjs.com/package/redlock) with modifications to the `package.json`.

## Installation

``` bash
npm install --global @hz-9/redlock-dist
```

## Usage

After configuring your `tsconfig.json` file, add the following to your codebase:

``` ts
import Redlock from '@hz9/redlock'

const redlock = new Redlock([...redisClients], { /* options */ })

```

For more detailed instructions, please refer to the [official redlock library documentation](https://www.npmjs.com/package/redlock).

## Introduction

The package is a modified version of the build output of `redlock`. It is not a direct copy of the source code.

When the `tsconfig.json` is configured with certain properties, `typescript` will read the `exports` field from the `package.json`.

However, `redlock@5.0.0-beta.2` did not set `"exports['.'].types": "./dist/index.d.ts"` in its `package.json`, which prevented TypeScript from properly resolving the type files.

Also, `redlock@5.0.0-beta.2` uses `"type": "module"` in its `package.json`, which defaults to the ESM (ES Module) format. Therefore, `@hz-9/redlock-dist` was created.

## Different with `redlock`

- What modifications were made to the `package.json` of `@hz-9/redlock-dist` compared to `redlock` ?

  1. Removed the `"type": "module"` property.
  2. Removed the `"scripts"` property.
  3. Added the `"exports['.'].types": "./dist/index.d.ts"` property.

- What `tsconfig.json` configurations are supported by `@hz-9/redlock-dist`?

You can see [tsconfig.json](https://github.com/hz-9/collection-space/blob/master/test-space/hz-9/redlock-dist/ts-node18-cjs/t-1.tsconfig.json) 。

## Publish

```sh
npm publish
```
