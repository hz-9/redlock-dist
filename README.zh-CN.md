# @hz-9/redlock-dist

从 [redlock](https://www.npmjs.com/package/redlock) 分叉并对 `package.json` 进行了修改。

## 安装

``` bash
npm install --global @hz-9/redlock-dist
```

## 使用

在配置好你的 `tsconfig.json` 文件后，将以下内容添加到你的代码库中：

``` ts
import Redlock from '@hz-9/redlock-dist'

const redlock = new Redlock([...redisClients], { /* options */ })

```

更详细的使用说明，请参考 [official redlock library documentation](https://www.npmjs.com/package/redlock)。

## 简介

该包是 `redlock` 构建输出的修改版本。它不是源代码的直接复制。

当 `tsconfig.json` 配置了特定属性时，`typescript` 将从 `package.json` 中读取 `exports` 字段。

然而，`redlock@5.0.0-beta.2` 在其 `package.json` 没有设置 `"exports['.'].types": "./dist/index.d.ts"`，这导致 TypeScript 无法正确解析类型文件。

此外，`redlock@5.0.0-beta.2` 在其 `package.json` 中使用了 `"type": "module"`，它默认为 ESM (ES Module) 格式。因此，创建了 `@hz-9/redlock-dist`。

## 与 `redlock` 的不同之处

- 与 `redlock` 相比，`@hz-9/redlock-dist` 的 `package.json` 进行了哪些修改？

  1. 移除了 `"type": "module"` 属性。
  2. 移除了 `"scripts"` 属性。
  3. 添加了 `"exports['.'].types": "./dist/index.d.ts"` 属性。

- `@hz-9/redlock-dist` 支持哪些 `tsconfig.json` 配置？

你可以查看 [tsconfig.json](https://github.com/hz-9/collection-space/blob/master/test-space/hz-9/redlock-dist/ts-node18-cjs/t-1.tsconfig.json)。

## 发布

```sh
npm publish
```
