# [0003. VSCode 中的 eslint 插件](https://github.com/Tdahuyou/eslint/tree/main/0003.%20VSCode%20%E4%B8%AD%E7%9A%84%20eslint%20%E6%8F%92%E4%BB%B6)

<!-- region:toc -->
- [1. 📝 Summary](#1--summary)
- [2. 🔗 links](#2--links)
- [3. 🤖 AI - 请介绍一下 VS Code ESLint extension](#3--ai---请介绍一下-vs-code-eslint-extension)
  - [3.1. 主要特性](#31-主要特性)
  - [3.2. 安装步骤](#32-安装步骤)
  - [3.3. 配置](#33-配置)
  - [3.4. 常见问题](#34-常见问题)
- [4. 🤖 AI - 阅读 https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint](#4--ai---阅读-https://marketplacevisualstudiocom/items?itemname=dbaeumervscode-eslint)
  - [4.1. 主要功能](#41-主要功能)
  - [4.2. 安装与设置](#42-安装与设置)
  - [4.3. 设置选项](#43-设置选项)
  - [4.4. 版本更新](#44-版本更新)
  - [4.5. 安全性和隐私](#45-安全性和隐私)
<!-- endregion:toc -->
## 1. 📝 Summary

## 2. 🔗 links

- https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint - marketplace eslint

![](md-imgs/2024-09-29-11-07-20.png)

## 3. 🤖 AI - 请介绍一下 VS Code ESLint extension

Visual Studio Code (VSCode) 的 ESLint 扩展是由 Dirk Baeumer 开发的，它允许你在 VSCode 中集成 ESLint 代码检查工具。这个扩展能够实时地在编辑器中显示代码风格和潜在错误的问题，帮助开发者保持一致的代码质量。以下是关于这个扩展的一些重要信息：

### 3.1. 主要特性

1. **实时 linting**:
   - 当你编辑 JavaScript 或 TypeScript 文件时，ESLint 扩展会实时检查代码，并在编辑器中显示警告和错误。
2. **自动修复问题**:
   - 对于一些可以自动修复的问题，你可以使用快捷键（通常是 `Ctrl + .`）或者通过命令面板来应用这些修复。
3. **配置文件支持**:
   - 支持多种 ESLint 配置文件格式，如 `.eslintrc.js`, `.eslintrc.json`, `.eslintrc.yaml` 等。
   - 也支持从 `package.json` 中读取 `"eslintConfig"` 字段。
4. **规则自定义**:
   - 你可以通过项目中的 ESLint 配置文件来自定义 lint 规则。
5. **与 Prettier 等其他工具的集成**:
   - 可以与其他格式化工具（如 Prettier）结合使用，确保代码不仅符合风格指南，而且格式统一。
6. **快速修复建议**:
   - 提供快速修复建议，可以直接在编辑器中选择并应用。
7. **工作区设置**:
   - 允许为不同的工作区或文件夹设置不同的 ESLint 配置。
8. **多语言支持**:
   - 支持 JavaScript 和 TypeScript 以及 JSX/TSX 语法。

### 3.2. 安装步骤

1. 打开 VSCode。
2. 转到左侧活动栏中的扩展图标（四个方块组成的图标）。
3. 在搜索框中输入 `ESLint`。
4. 选择由 Dirk Baeumer 提供的 ESLint 扩展并点击安装。
5. 安装完成后，重启 VSCode（如果需要的话）。

### 3.3. 配置

一旦安装了 ESLint 扩展，你可能需要进行一些配置以确保其正确运行：

- **全局启用 ESLint**:
  - 打开用户设置（`Ctrl + ,`），搜索 `eslint.enable` 并确保其值为 `true`。
- **项目特定配置**:
  - 你可以在项目的 `.vscode/settings.json` 文件中添加特定于项目的 ESLint 设置。
- **运行模式**:
  - 你可以设置 ESLint 在什么情况下运行，例如在保存文件时 (`onSave`) 或者在输入时 (`onType`)。
- **自动修复**:
  - 你可以在保存文件时自动应用 ESLint 的修复建议。在用户设置或项目设置中添加：
    ```json
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
    }
- **忽略某些文件或文件夹**:
  - 如果你不希望 ESLint 检查某些文件或文件夹，可以在 `.eslintignore` 文件中列出它们。
### 3.4. 常见问题

- **没有看到任何错误提示**:
  - 确保 ESLint 已经安装在你的项目依赖中。
  - 检查是否有 `.eslintrc.*` 文件存在，并且配置正确。
  - 确保 ESLint 扩展已启用，并且配置正确。
- **性能问题**:
  - 如果遇到性能问题，可以尝试调整 ESLint 扩展的设置，比如减少同时处理的文件数量。

通过上述介绍，你应该对如何在 VSCode 中使用 ESLint 扩展有了一个基本的了解。如果你有更具体的需求或遇到问题，可以查阅官方文档或社区资源获取更多信息。

## 4. 🤖 AI - 阅读 https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint

根据 Visual Studio Code Marketplace 上关于 ESLint 扩展的页面，以下是一些关键点和特性介绍：

### 4.1. 主要功能
- **集成 ESLint**：该扩展将 ESLint 集成到 VSCode 中，允许开发者在编辑器内直接查看代码风格问题、潜在错误以及进行自动修复。
- **自动检测**：扩展会在打开的工作区文件夹中寻找已安装的 ESLint 库。如果没有找到本地安装，则会查找全局安装的版本。
- **自定义规则**：用户可以通过配置文件来自定义 ESLint 规则，以适应特定项目的需要。
- **格式化支持**：可以使用 ESLint 作为格式化工具，并且可以与其它格式化工具（如 Prettier）结合使用。
- **保存时自动修复**：通过设置 `editor.codeActionsOnSave` 和 `source.fixAll.eslint`，可以在保存文件时自动应用所有可修复的 ESLint 错误。

### 4.2. 安装与设置
- **安装**：可以从 VSCode 的扩展市场搜索并安装 "ESLint" 扩展。
- **依赖安装**：确保项目中已经安装了 ESLint（通过 `npm install eslint --save-dev` 或者 `yarn add eslint --dev`）。
- **创建配置文件**：如果项目中还没有 `.eslintrc` 文件，可以通过命令行运行 `npx eslint --init` 来初始化一个配置文件，或者使用 VSCode 提供的命令来创建配置文件。

### 4.3. 设置选项
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

### 4.4. 版本更新
- 最新版本的 ESLint 扩展增加了对单个笔记本文档单元格的支持（如果语言被 ESLint 支持）。
- 添加了对 ESLint V8.0 Beta 的支持，并且保持向后兼容。
- 适配了 VS Code 的工作区信任模型，并移除了自定义对话框。
- 增加了自定义 ESLint 规则严重性的支持。
- 改进了 TypeScript 检测，当 ESLint 正确配置时不再需要额外的 VS Code 设置。
- 支持 glob 工作目录模式，方便处理复杂的文件夹结构。
- 引入了 formatter 支持，使 ESLint 可以作为格式化工具使用。
- 改进了保存时自动修复的功能，现在是 VS Code 的代码操作保存基础设施的一部分。
- 修复了一些 bug 并提高了整体性能。

### 4.5. 安全性和隐私
- 扩展遵循 VS Code 的安全模型，包括确认执行 ESLint 库时的信任流程。
- 用户可以选择批准或拒绝 ESLint 库的执行，这些决定可以通过状态栏图标、快速修复建议或命令面板中的命令进行管理。

这个扩展极大地增强了开发者的编码体验，特别是在维护大型 JavaScript/TypeScript 项目时，它能够帮助开发者保持代码的一致性和质量。如果你正在使用 VSCode 开发 JavaScript 或 TypeScript 项目，那么安装和配置 ESLint 扩展是非常推荐的。