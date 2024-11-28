# [README.md](./0001.%20eslint%20是什么？/README.md)<!-- !======> SEPERATOR <====== -->
# [0001. eslint 是什么？](https://github.com/Tdahuyou/eslint/tree/main/0001.%20eslint%20%E6%98%AF%E4%BB%80%E4%B9%88%EF%BC%9F)

<!-- region:toc -->
- [1. 🔗 links](#1--links)
- [2. 📒 eslint 简介](#2--eslint-简介)
- [3. 📒 eslint 的一些主要功能和用途](#3--eslint-的一些主要功能和用途)
- [4. 💻 demo - 基础示例 - 尝试添加规则：程序中的引号必须使用单引号](#4--demo---基础示例---尝试添加规则程序中的引号必须使用单引号)
<!-- endregion:toc -->

## 1. 🔗 links

- https://eslint.org/ - eslint 官网
- https://github.com/eslint/eslint - eslint GitHub

## 2. 📒 eslint 简介

- ESLint 是一个 **开源** 的 JavaScript 代码检查工具，它可以帮助开发者发现代码中的问题，并 **强制执行一致的编码风格**。ESLint 可以识别并报告关于你代码的问题，无论是语法错误还是不符合特定编码规范的情况。
- ESLint 是一个用于识别和报告在 ECMAScript/JavaScript 代码中发现的模式匹配问题的工具，它的主要目标是帮助开发者确保代码的一致性，并且减少错误的发生。它是一个完全 **可插拔** 的工具，这意味着每条规则都是一个独立的插件，用户可以根据自己的需求在运行时添加更多的规则。
- ESLint 不仅可以作为单独的命令行工具使用，还可以集成到大多数现代的集成开发环境（IDE）中，如 Visual Studio Code、WebStorm 等，从而实现实时的代码质量反馈。通过配置 ESLint 插件，比如 VS Code 的 ESLint 插件，可以在编辑器内直接提示代码格式错误，并且可以通过执行 `eslint . --fix` 命令来检查并自动修复一些常见的代码风格问题。
- ESLint 提供了高度自定义的能力，允许用户根据项目的需求配置不同的规则。这些规则可以是内置的，也可以是通过社区插件提供的，甚至用户自己编写。这样的灵活性使得 ESLint 可以适应从个人项目到大型企业应用的各种规模的 JavaScript 项目。
- 除了帮助保持一致的编码风格，ESLint 还能够检测潜在的错误，例如未使用的变量、不安全的操作等。这有助于提高代码的质量，减少 bug，并促进团队成员之间的协作。此外，由于其开源特性，ESLint 拥有一个活跃的社区，持续更新和改进规则集，确保它可以跟上 JavaScript 和相关技术的发展步伐。
- ESLint 是一个强大的代码检查工具，对于任何想要提升代码质量和维护性的 JavaScript 开发者来说都是不可或缺的工具。通过合理地配置和使用 ESLint，可以显著提高开发效率和最终产品的稳定性。

## 3. 📒 eslint 的一些主要功能和用途

1. **可配置性**：ESLint 提供了非常灵活的配置选项，允许用户自定义规则。你可以选择遵循流行的风格指南（如 Airbnb、Google 或者 StandardJS）或者创建自己的规则集。
2. **插件系统**：ESLint 支持插件，这意味着社区可以扩展它的功能。例如，有插件支持 React、Vue.js 和 TypeScript 等框架和技术。
3. **自动修复**：对于某些类型的错误或不一致，ESLint 能够自动修复这些问题，这可以节省大量的时间。
4. **提高代码质量**：通过强制实施良好的编程实践，ESLint 有助于减少 bug 并保持代码库的一致性和可读性。
5. **集成开发环境 (IDE) 支持**：大多数现代 IDE 和编辑器都支持 ESLint，可以在编写代码时实时显示警告和错误信息。
6. **团队协作**：在一个团队中使用 ESLint 可以确保所有成员遵循相同的编码标准，从而降低代码审查过程中的摩擦。

要开始使用 ESLint，你需要首先安装它。可以通过 npm（Node 包管理器）来安装 ESLint。安装完成后，你可以初始化一个配置文件，然后在你的项目中运行 ESLint 来检查代码。

安装 ESLint 的基本命令如下：

```bash
npm install eslint --save-dev
```

然后初始化配置文件：

```bash
npx eslint --init
```

`eslint --init` 命令会引导你完成一系列的选择题，帮助你设置最适合项目的 ESLint 配置。根据你的选择，它可能会生成一个 `.eslintrc` 文件，该文件包含了所有的规则设定。之后，你可以在你的构建流程中加入 `eslint` 命令来定期检查代码。


## 4. 💻 demo - 基础示例 - 尝试添加规则：程序中的引号必须使用单引号

```js
// demo/eslint.config.cjs
module.exports = {
    rules: {
        quotes: ['error', 'single'],
        // 引号必须使用单引号，否则会报错。
    }
}
```

```js
// demo/1.js
const str = "Hello World"
// 报错：
// Strings must use singlequote.eslintquotes
```

- ![](md-imgs/2024-09-29-10-29-42.png)
- 可以通过 eslint 命令来快速修复一个模块中不符合规范的代码，能够减少手动修改代码的工作量。不过这个功能仅限于那些可以自动化修复的错误，比如这个示例中的引号错误使用而引起的错误。对于那些无法自动一键修复的错误，依旧是需要根据 IDE 的提示，手动去修改的。
- ![](md-imgs/2024-09-29-10-32-20.png)
- 命令 `eslint --fix` 可用来一键修复模块中的一些能够被自动修复的错误。
- eslint 规则未生效的原因可能是因为 eslint 配置文件没有被正确加载，或者是 eslint 服务出现问题。测试时如果出现这样的异常现象“已明确代码没问题，但是 VSCode 并没有提供错误提示”，可以通过重启 VSCode 来尝试解决。



# [README.md](./0002.%20eslint%20的配置文件的命名/README.md)<!-- !======> SEPERATOR <====== -->
# [0002. eslint 的配置文件的命名](https://github.com/Tdahuyou/eslint/tree/main/0002.%20eslint%20%E7%9A%84%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E7%9A%84%E5%91%BD%E5%90%8D)

<!-- region:toc -->
- [1. 🔗 官方文档 > Configuration File](#1--官方文档->-configuration-file)
- [2. 📒 eslint 的配置文件名称的更多写法](#2--eslint-的配置文件名称的更多写法)
<!-- endregion:toc -->

## 1. 🔗 官方文档 > Configuration File

- https://eslint.org/docs/latest/use/configure/configuration-files#configuration-file

> 下面是来自官方文档的描述。

The ESLint configuration file may be named any of the following:

- eslint.config.js
- eslint.config.mjs
- eslint.config.cjs
- eslint.config.ts (requires additional setup)
- eslint.config.mts (requires additional setup)
- eslint.config.cts (requires additional setup)

It should be placed in the root directory of your project and export an array of configuration objects. Here’s an example:

```js
// eslint.config.js
export default [
    {
        rules: {
            semi: "error",
            "prefer-const": "error"
        }
    }
];
```

> 注意：官方文档罗列的这些名称，并非全部，eslint 的配置文件命名还有很多种写法。

## 2. 📒 eslint 的配置文件名称的更多写法

- eslint 的配置文件命名有多种写法，比如 eslint.config |.js|.mjs|.cjs|.ts|.mts|.cts 或者 .eslintrc |.js|.json|.yml|.cjs|.mjs 或者 package.json 等等。需要知道 eslint 配置文件的命名是非常灵活的，这决定了 eslint 配置信息应该书写在什么位置，我们需要知道在哪查看 eslint 的配置信息。
- eslint 的配置文件可以有多种命名方式，而不仅仅是官方列出的那些。实际上，ESLint 支持多种配置文件格式和命名约定。

1. **`.eslintrc.js`** - JavaScript 格式的配置文件。
2. **`.eslintrc.json`** - JSON 格式的配置文件。
3. **`.eslintrc.yaml`** - YAML 格式的配置文件。
4. **`.eslintrc.yml`** - YAML 格式的配置文件（与 `.yaml` 同义）。
5. **`.eslintrc.cjs`** - CommonJS 格式的配置文件。
6. **`.eslintrc.mjs`** - ECMAScript 模块格式的配置文件。
7. **`package.json`** - 在项目的 `package.json` 文件中添加 `"eslintConfig"` 字段。

此外，从 ESLint v8 开始，还支持以下新的配置文件名：

- **`eslint.config.js`** - JavaScript 格式的配置文件。
- **`eslint.config.cjs`** - CommonJS 格式的配置文件。
- **`eslint.config.mjs`** - ECMAScript 模块格式的配置文件。
- **`eslint.config.ts`** - TypeScript 格式的配置文件（需要额外设置）。
- **`eslint.config.mts`** - TypeScript 模块格式的配置文件（需要额外设置）。
- **`eslint.config.cts`** - TypeScript CommonJS 格式的配置文件（需要额外设置）。

这些新的命名约定是为了更好地与其他工具保持一致，并且更明确地表示它们是 ESLint 的配置文件。

**如何选择？**

- 如果你的项目已经使用了 `.eslintrc.js` 或其他传统命名，你可以继续使用它。
- 如果你在创建新项目或希望采用最新标准，可以考虑使用 `eslint.config.js` 或相应的其他扩展名。

**注意事项：**

- 如果在同一目录下存在多个配置文件，ESLint 会根据上面列出的顺序选择第一个找到的配置文件。
- 对于 TypeScript 配置文件（如 `eslint.config.ts`），你需要确保安装了 `@typescript-eslint/parser` 和相关的插件，并且在你的项目中正确配置了 TypeScript。


# [README.md](./0003.%20VSCode%20中的%20eslint%20插件/README.md)<!-- !======> SEPERATOR <====== -->
# [0003. VSCode 中的 eslint 插件](https://github.com/Tdahuyou/eslint/tree/main/0003.%20VSCode%20%E4%B8%AD%E7%9A%84%20eslint%20%E6%8F%92%E4%BB%B6)

<!-- region:toc -->
- [1. 🔗 vscode marketplace eslint](#1--vscode-marketplace-eslint)
- [2. 📒 VS Code ESLint extension 简介](#2--vs-code-eslint-extension-简介)
- [3. 📒 主要功能](#3--主要功能)
- [4. 📒 安装与设置](#4--安装与设置)
- [5. 📒 常见配置](#5--常见配置)
- [6. 📒 常见的初始配置流程](#6--常见的初始配置流程)
- [7. 📒 常见问题](#7--常见问题)
<!-- endregion:toc -->

## 1. 🔗 vscode marketplace eslint

- https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint
  - marketplace eslint
  - ![](md-imgs/2024-09-29-11-07-20.png)

## 2. 📒 VS Code ESLint extension 简介

- Visual Studio Code (VSCode) 的 ESLint 扩展是由 Dirk Baeumer 开发的，它允许你在 VSCode 中集成 ESLint 代码检查工具。这个扩展能够实时地在编辑器中显示代码风格和潜在错误的问题，帮助开发者保持一致的代码质量。
- 这个扩展极大地增强了开发者的编码体验，特别是在维护大型 JavaScript/TypeScript 项目时，它能够帮助开发者保持代码的一致性和质量。如果你正在使用 VSCode 开发 JavaScript 或 TypeScript 项目，那么安装和配置 ESLint 扩展是非常推荐的。

## 3. 📒 主要功能

- **集成 ESLint**：该扩展将 ESLint 集成到 VSCode 中，允许开发者在编辑器内直接查看代码风格问题、潜在错误以及进行自动修复。
- **自动检测**：扩展会在打开的工作区文件夹中寻找已安装的 ESLint 库。如果没有找到本地安装，则会查找全局安装的版本。
- **自定义规则**：用户可以通过配置文件来自定义 ESLint 规则，以适应特定项目的需要。
- **格式化支持**：可以使用 ESLint 作为格式化工具，并且可以与其它格式化工具（如 Prettier）结合使用。
- **保存时自动修复**：通过设置 `editor.codeActionsOnSave` 和 `source.fixAll.eslint`，可以在保存文件时自动应用所有可修复的 ESLint 错误。

## 4. 📒 安装与设置

- **安装**：可以从 VSCode 的扩展市场搜索并安装 "ESLint" 扩展。
  1. 打开 VSCode。
  2. 转到左侧活动栏中的扩展图标（四个方块组成的图标）。
  3. 在搜索框中输入 `ESLint`。
  4. 选择由 Dirk Baeumer 提供的 ESLint 扩展并点击安装。
  5. 安装完成后，重启 VSCode（如果需要的话）。
- **依赖安装**：确保项目中已经安装了 ESLint（通过 `npm install eslint --save-dev` 或者 `yarn add eslint --dev`）。
- **创建配置文件**：如果项目中还没有 `.eslintrc` 文件，可以通过命令行运行 `npx eslint --init` 来初始化一个配置文件，或者使用 VSCode 提供的命令来创建配置文件。

## 5. 📒 常见配置

- **eslint.enable**：启用或禁用 ESLint 扩展。
- **eslint.packageManager**：指定用于运行 ESLint 的包管理器。
- **eslint.nodePath**：指定 Node.js 模块的路径。
- **eslint.options**：传递给 ESLint 运行时的额外选项。
- **eslint.validate**：指定 ESLint 应该验证哪些语言。
- **eslint.format.enable**：使用 ESLint 作为格式化工具。
- **eslint.onIgnoredFiles**：控制是否在尝试检查被忽略的文件时生成警告。
- **eslint.rules.customizations**：自定义 ESLint 规则的严重性级别。
- **eslint.useESLintClass**：强制使用新的 ESLint API。
- **eslint.runtime**：指定 ESLint 使用的 Node.js 运行时环境。

## 6. 📒 常见的初始配置流程

一旦安装了 ESLint 扩展，你可能需要进行一些配置以确保其正确运行：

- **全局启用 ESLint**：打开用户设置（`Ctrl + ,`），搜索 `eslint.enable` 并确保其值为 `true`。
- **项目特定配置**：你可以在项目的 `.vscode/settings.json` 文件中添加特定于项目的 ESLint 设置。
- **运行模式**：你可以设置 ESLint 在什么情况下运行，例如在保存文件时 (`onSave`) 或者在输入时 (`onType`)。
- **自动修复**：你可以在保存文件时自动应用 ESLint 的修复建议。在用户设置或项目设置中添加：
```json
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
}
```
- **忽略某些文件或文件夹**：如果你不希望 ESLint 检查某些文件或文件夹，可以在 `.eslintignore` 文件中列出它们。

## 7. 📒 常见问题

- **没有看到任何错误提示**:
  - 确保 ESLint 已经安装在你的项目依赖中。
  - 检查是否有 `.eslintrc.*` 文件存在，并且配置正确。
  - 确保 ESLint 扩展已启用，并且配置正确。
- **性能问题**:
  - 如果遇到性能问题，可以尝试调整 ESLint 扩展的设置，比如减少同时处理的文件数量。

# [README.md](./0004.%20使用%20no-unused-vars%20配置规则：未使用的变量报错/README.md)<!-- !======> SEPERATOR <====== -->
# [0004. 使用 no-unused-vars 配置规则：未使用的变量报错](https://github.com/Tdahuyou/eslint/tree/main/0004.%20%E4%BD%BF%E7%94%A8%20no-unused-vars%20%E9%85%8D%E7%BD%AE%E8%A7%84%E5%88%99%EF%BC%9A%E6%9C%AA%E4%BD%BF%E7%94%A8%E7%9A%84%E5%8F%98%E9%87%8F%E6%8A%A5%E9%94%99)

<!-- region:toc -->
- [1. 📝 Summary](#1--summary)
- [2. 🔗 links](#2--links)
- [3. 📒 notes](#3--notes)
- [4. 💻 demo - 'no-unused-vars': 'error'](#4--demo---'no-unused-vars'-'error')
- [5. 🤖 AI - 请介绍一下 no-unused-var 配置](#5--ai---请介绍一下-no-unused-var-配置)
  - [5.1. 规则配置](#51-规则配置)
    - [5.1.1. 基本启用](#511-基本启用)
    - [5.1.2. 自定义选项](#512-自定义选项)
      - [5.1.2.1. 忽略模式](#5121-忽略模式)
      - [5.1.2.2. 忽略函数参数](#5122-忽略函数参数)
      - [5.1.2.3. 检查已解构的变量](#5123-检查已解构的变量)
      - [5.1.2.4. 忽略导出的变量](#5124-忽略导出的变量)
  - [5.2. 示例](#52-示例)
<!-- endregion:toc -->
## 1. 📝 Summary

## 2. 🔗 links

- https://eslint.org/docs/latest/rules/no-unused-vars - eslint 官方文档 no-unused-vars

## 3. 📒 notes

- `no-unused-vars` 用于检测代码中未使用的变量、函数参数或导入的模块。通常情况下，对于一个模块中未使用的变量，程序中是不会报错的。
- **未被使用的变量对程序的逻辑并不会造成影响。**如果想要确保程序中不存在未使用的变量，可以通过 `no-unused-vars` 规则来检测并报错提示，然后再将这些提示的变量处理掉。

## 4. 💻 demo - 'no-unused-vars': 'error'

```js
module.exports = {
    rules: {
        'no-unused-vars': 'error'
    }
}
```

![](md-imgs/2024-09-29-13-03-19.png)

## 5. 🤖 AI - 请介绍一下 no-unused-var 配置

`no-unused-vars` 是 ESLint 中一个非常有用的规则，用于检测代码中未使用的变量、函数参数或导入的模块。这个规则有助于保持代码的整洁，避免不必要的声明，并且可以减少潜在的错误。

### 5.1. 规则配置

在你的 ESLint 配置文件（例如 `.eslintrc.js` 或 `eslint.config.js`）中，你可以启用和自定义 `no-unused-vars` 规则。以下是一些常见的配置选项：

#### 5.1.1. 基本启用
```javascript
module.exports = {
  rules: {
    'no-unused-vars': 'error' // 或者 'warn'
  }
};
```

这里 `'error'` 表示如果违反了这条规则，ESLint 会将其标记为错误；如果是 `'warn'`，则只会生成警告。

#### 5.1.2. 自定义选项
`no-unused-vars` 规则支持多个选项来进一步定制其行为。这些选项可以通过数组形式传递给规则，其中第一个元素是错误级别（`error` 或 `warn`），第二个元素是一个对象，包含具体的配置选项。

##### 5.1.2.1. 忽略模式
如果你希望忽略某些特定的变量名或模式，可以使用 `varsIgnorePattern` 和 `argsIgnorePattern` 选项：
```javascript
module.exports = {
  rules: {
    'no-unused-vars': ['error', { varsIgnorePattern: '^_', argsIgnorePattern: '^_' }]
  }
};
```
在这个例子中，所有以 `_` 开头的变量和函数参数将被忽略，不会触发 `no-unused-vars` 错误。

##### 5.1.2.2. 忽略函数参数
有时候你可能需要保留一些函数参数，即使它们没有被使用，比如回调函数中的默认参数。你可以通过设置 `args` 选项来调整这一点：
```javascript
module.exports = {
  rules: {
    'no-unused-vars': ['error', { args: 'none' }]
  }
};
```
这会禁用对函数参数的检查。

##### 5.1.2.3. 检查已解构的变量
默认情况下，`no-unused-vars` 不会检查解构赋值中的未使用变量。如果你想启用这项检查，可以设置 `destructuredArrayIgnorePattern` 和 `ignoreRestSiblings` 选项：
```javascript
module.exports = {
  rules: {
    'no-unused-vars': ['error', { destructuredArrayIgnorePattern: '^_' }]
  }
};
```
这样，除了那些匹配模式的解构变量外，其他未使用的解构变量都会触发错误。

##### 5.1.2.4. 忽略导出的变量
有时你可能需要导出一些变量，即使它们在当前文件中没有被使用。你可以通过设置 `vars` 选项来调整这一点：
```javascript
module.exports = {
  rules: {
    'no-unused-vars': ['error', { vars: 'local' }]
  }
};
```
这会只检查局部变量，而忽略全局变量和导出的变量。

### 5.2. 示例

假设你有如下 JavaScript 代码：
```javascript
function example(a, b) {
  console.log(a);
}

const unusedVar = 42;
```

如果没有配置 `no-unused-vars` 规则，这段代码会被认为是有效的。但是，当你启用了 `no-unused-vars` 规则后，ESLint 会报告 `b` 和 `unusedVar` 未被使用。

如果你想要忽略以 `_` 开头的变量，可以配置如下：
```javascript
module.exports = {
  rules: {
    'no-unused-vars': ['error', { argsIgnorePattern: '^_', varsIgnorePattern: '^_' }]
  }
};
```

然后修改代码：
```javascript
function example(_a, _b) {
  console.log(_a);
}

const _unusedVar = 42;
```

此时，ESLint 将不会报告 `_b` 和 `_unusedVar` 未被使用。

通过这样的配置，你可以根据项目的具体需求灵活地应用 `no-unused-vars` 规则。


# [README.md](./0005.%20eslint%20配置格式/README.md)<!-- !======> SEPERATOR <====== -->
# [0005. eslint 配置格式](https://github.com/Tdahuyou/eslint/tree/main/0005.%20eslint%20%E9%85%8D%E7%BD%AE%E6%A0%BC%E5%BC%8F)

<!-- region:toc -->
- [1. 📒 eslint 的配置文件都有哪些格式？](#1--eslint-的配置文件都有哪些格式)
- [2. 💻 `.eslintrc.js` (JavaScript)](#2--eslintrcjs-(javascript))
- [3. 💻 `.eslintrc.json` (JSON)](#3--eslintrcjson-(json))
- [4. 💻 `.eslintrc.yaml` 或 `.eslintrc.yml` (YAML)](#4--eslintrcyaml-或-eslintrcyml-(yaml))
- [5. 💻 `.eslintrc.cjs` (CommonJS)](#5--eslintrccjs-(commonjs))
- [6. 💻 包管理器配置文件（如 `package.json`）](#6--包管理器配置文件如-packagejson)
<!-- endregion:toc -->

## 1. 📒 eslint 的配置文件都有哪些格式？

- ESLint 支持多种配置文件格式，每种格式都有其特点和适用场景。以下是 ESLint 支持的主要配置文件格式：
  - `.eslintrc.js` (JavaScript)
  - `.eslintrc.json` (JSON)
  - `.eslintrc.yaml` 或 `.eslintrc.yml` (YAML)
  - `.eslintrc.cjs` (CommonJS)
  - 包管理器配置文件（如 `package.json`）
- 选择哪种格式主要取决于你的个人偏好以及项目的具体需求。通常情况下，如果不需要复杂的逻辑，推荐使用 `.eslintrc.json` 或者 `.eslintrc.yaml`，因为它们清晰且易于维护。如果你需要动态生成配置，则可以选择 `.eslintrc.js` 或 `.eslintrc.cjs`。

## 2. 💻 `.eslintrc.js` (JavaScript)

 - 这是一个 JavaScript 文件，允许使用完整的 JavaScript 语法来定义配置。
 - 适合需要动态生成配置或者需要更复杂的逻辑的情况。
 - 示例：

```javascript
module.exports = {
    env: {
        browser: true,
        es2021: true,
    },
    extends: 'eslint:recommended',
    parserOptions: {
        ecmaVersion: 12,
        sourceType: 'module',
    },
    rules: {
        quotes: ['error', 'single'],
    },
};
```

## 3. 💻 `.eslintrc.json` (JSON)

- 这是最常用的配置文件格式之一，因为它简单直观且易于阅读。
- 适合静态配置，不包含任何逻辑。
- 示例：

```json
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": "eslint:recommended",
    "parserOptions": {
        "ecmaVersion": 12,
        "sourceType": "module"
    },
    "rules": {
        "quotes": ["error", "single"]
    }
}
```

## 4. 💻 `.eslintrc.yaml` 或 `.eslintrc.yml` (YAML)

- YAML 格式比 JSON 更简洁，并且支持注释。
- 适用于喜欢简洁配置文件的用户。
- 示例：

```yaml
env:
  browser: true
  es2021: true
extends: eslint:recommended
parserOptions:
  ecmaVersion: 12
  sourceType: module
rules:
  quotes: [error, single]
```

## 5. 💻 `.eslintrc.cjs` (CommonJS)

- 这是另一个 JavaScript 配置文件，但使用 CommonJS 模块系统（Node.js 的默认模块系统）。
- 与 `.eslintrc.js` 类似，但它使用 `require` 而不是 `import`。
- 示例：

```javascript
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: 'eslint:recommended',
  parserOptions: {
    ecmaVersion: 12,
    sourceType: 'module',
  },
  rules: {
    quotes: ['error', 'single'],
  },
};
```

## 6. 💻 包管理器配置文件（如 `package.json`）

- 可以在项目的 `package.json` 文件中直接添加 `"eslintConfig"` 字段来指定 ESLint 配置。
- 这样可以减少项目中的配置文件数量。
- 示例：

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "eslintConfig": {
    "env": {
      "browser": true,
      "es2021": true
    },
    "extends": "eslint:recommended",
    "parserOptions": {
      "ecmaVersion": 12,
      "sourceType": "module"
    },
    "rules": {
      "quotes": ["error", "single"]
    }
  }
}
```


# [README.md](./0006.%20忽略文件%20.eslintignore/README.md)<!-- !======> SEPERATOR <====== -->
# [0006. 忽略文件 .eslintignore](https://github.com/Tdahuyou/eslint/tree/main/0006.%20%E5%BF%BD%E7%95%A5%E6%96%87%E4%BB%B6%20.eslintignore)

<!-- region:toc -->
- [1. 📒 忽略文件 `.eslintignore` 简介](#1--忽略文件-eslintignore-简介)
<!-- endregion:toc -->

## 1. 📒 忽略文件 `.eslintignore` 简介

- `.eslintignore` vs. `gitignore`
  - `.eslintignore` 跟 git 的忽略配置文件 `.gitignore` 非常类似
  -  `.gitignore` 用于指定应该被 git 忽略的文件或目录。
  - `.eslintignore` 用于指定应该被 ESLint 忽略的文件或目录。
- 示例：

```
node_modules/
dist/
build/
```
