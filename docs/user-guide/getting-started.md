---
title: 快速开始
layout: doc
edit_link: https://github.com/eslint/eslint/edit/master/docs/user-guide/getting-started.md

---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->

# 快速开始 {#getting-started-with-eslint}

ESLint 是用来识别 ECMAScript/JavaScript 并按照规则给出报告的代码检测工具，使用它在可以使代码更加统一的同时还可以规避错误。在许多方面，它与 JSLint 和 JSHint 相似，但存在差异：

* ESLint 使用 [Espree](https://github.com/eslint/espree) 解析 JavaScript。
* ESLint 采用 AST 分析代码的模式。
* ESLint 是完全插件化的，每一条规则都是一个插件，并且你可以在运行时添加更多的插件。

## 安装及使用 {#installation-and-usage}

前置依赖：[Node.js](https://nodejs.org/en/) (`^10.12.0`, or `>=12.0.0`) 内置对 SSL 的支持。（如果你使用的是 Node.js 的官方正式版，那 SSL 已被内置。）

你可以通过 npm 或 yarn 来安装 ESLint：

```
npm install eslint --save-dev

# 或者

yarn add eslint --dev
```

接着需要设置配置文件，最简单的方式就是使用 `--init` 选项来进行设置：

```
$ npx eslint --init

# 或者

$ yarn run eslint --init
```

**注意：** `--init` 会假设你已拥有 `package.json` 文件。如果没有此文件，请先执行 `npm init` 或者 `yarn init`。

接着，可以对任意文件或目录执行 ESLint：

```
$ npx eslint yourfile.js

# 或者

$ yarn run eslint yourfile.js
```

当然，你也可以在全局安装 ESLint（使用 `npm install eslint --global`），但是，不建议这样做，因为你所使用的任何插件或可共享的配置无论何种情况下都必须安装在本地。

## 配置 {#configuration}

**注意：** 如果你之前使用的版本低于 1.0.0，请查看 [迁移指南](migrating-to-1.0.0)。

运行 `eslint --init`，你的文件目录下将会生成一个 `.eslintrc.{js,yml,json}` 文件。在该文件中，你会看到许多像下面这样的配置：

```json
{
    "rules": {
        "semi": ["error", "always"],
        "quotes": ["error", "double"]
    }
}
```

`"semi"` 和 `"quotes"` 均为 ESLint 中的 [规则](/docs/rules) 名称。数组中填入的第一个值代表错误级别，可以是下列值的其中之一。

* `"off"` 或 `0` - 关闭规则
* `"warn"` 或 `1` - 将规则视为警告（不影响退出码）
* `"error"` 或 `2` - 将规则视为错误（退出码为 1）

这三个错误级别可以允许你细粒度的控制 ESLint 如何应用规则（欲了解更多关于配置选项和细节的问题，请参阅 [配置文档](configuring/)）。

`.eslintrc.{js,yml,json}` 配置文件中可以引入下面这行：

```json
{
    "extends": "eslint:recommended"
}
```

引入这行，会启用 [规则页面](/docs/rules) 上所有被标为 "(recommended)" 的规则。此外，你还可以通过在 [npmjs.com](https://www.npmjs.com/search?q=eslint-config) 上搜索 "eslint-config" 来使用他人创建的配置。只有当你的配置文件中添加了一个共享配置的扩展，或者在你的配置中明确启用了规则时，ESLint 才会校验你的代码。

---

## 后续 {#next-steps}

* 学习 ESLint 的 [高级配置](configuring/)。
* 熟悉 [命令行选项](command-line-interface)。
* 探索将 [ESLint 集成](integrations) 到其他工具中，如编辑器，构建工具等。
* 没有找到合适的规则？创建 [自定义规则](/docs/developer-guide/working-with-rules)。
* [贡献代码](/docs/developer-guide/contributing/) 使 ESLint 更加完善。
