# @hz-9/redlock-dist

Forked from [redlock](https://www.npmjs.com/package/redlock) with modifications to the package.json.

## Installation

``` bash
npm install --global @hz-9/docker-build
```

## Usage

After configuring your tsconfig.json file, add the following to your codebase:

``` ts
import Redlock from '@hz9/redlock'

const redlock = new Redlock([...redisClients], { /* options */ })

```

For more detailed instructions, please refer to the [official redlock library documentation](https://www.npmjs.com/package/redlock).

## Why?

The package is a modified version of the build output of redlock. It is not a direct copy of the source code.

当我们的 `tsconfig.json` 中设置为以下属性时，`typescript` 将会读取 `package.json` 的 `exports` 属性。

`redlock@5.0.0-beta.2` 并未设置 `"exports['.'].types": "./dist/index.d.ts"` 信息，所以无法正常获取类型文件。

而且 `redlock@5.0.0-beta.2` 中 `package.json` 的 `"type": "module"` 默认使用 `ESM` 格式，所以创建了 `@hz-9/redlock`。

## Different with `redlock`

- What modifications were made to the `package.json` of `@hz-9/redlock` compared to `redlock` ?

  1. Removed the `"type": "module"` property.
  2. Removed the `"scripts"` property.
  3. Added the `"exports['.'].types": "./dist/index.d.ts"` property.

- What tsconfig.json configurations are supported by @hz-9/redlock?

You can see [tsconfig.json](https://github.com/hz-9/collection-space/blob/master/test-space/hz-9/redlock-dist/ts-node18-cjs/t-1.tsconfig.json) 。
