# [0002. eslint 的配置文件的命名](https://github.com/Tdahuyou/eslint/tree/main/0002.%20eslint%20%E7%9A%84%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E7%9A%84%E5%91%BD%E5%90%8D)

## 🔗 links

- https://eslint.org/docs/latest/use/configure/configuration-files#configuration-file

## 📒 notes

- eslint 的配置文件命名有多种写法，比如 eslint.config |.js|.mjs|.cjs|.ts|.mts|.cts 或者 .eslintrc |.js|.json|.yml|.cjs|.mjs 或者 package.json 等等。需要知道 eslint 配置文件的命名是非常灵活的，这决定了 eslint 配置信息应该书写在什么位置，我们需要知道在哪查看 eslint 的配置信息。
- 命令 `eslint --fix` 可用来一键修复模块中的一些能够被自动修复的错误。
- eslint 规则未生效的原因可能是因为 eslint 配置文件没有被正确加载，或者是 eslint 服务出现问题。测试时如果出现这样的异常现象“已明确代码没问题，但是 VSCode 并没有提供错误提示”，可以通过重启 VSCode 来尝试解决。

## 📝 DOC - Configuration File

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

## 🤖 AI - eslint 的命名只有下面这些吗？

- eslint.config.js
- eslint.config.mjs
- eslint.config.cjs
- eslint.config.ts (requires additional setup)
- eslint.config.mts (requires additional setup)
- eslint.config.cts (requires additional setup)

---

ESLint 的配置文件可以有多种命名方式，而不仅仅是你列出的那些。实际上，ESLint 支持多种配置文件格式和命名约定。以下是 ESLint 官方支持的配置文件名称：

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

### 使用哪个配置文件

- 如果你的项目已经使用了 `.eslintrc.js` 或其他传统命名，你可以继续使用它。
- 如果你在创建新项目或希望采用最新标准，可以考虑使用 `eslint.config.js` 或相应的其他扩展名。

### 注意事项

- 如果在同一目录下存在多个配置文件，ESLint 会根据上面列出的顺序选择第一个找到的配置文件。
- 对于 TypeScript 配置文件（如 `eslint.config.ts`），你需要确保安装了 `@typescript-eslint/parser` 和相关的插件，并且在你的项目中正确配置了 TypeScript。

总之，虽然你提到的那些是官方推荐的新命名方式，但 ESLint 仍然支持传统的 `.eslintrc.*` 命名方式。你可以根据项目的需求和个人偏好来选择合适的配置文件名称。

## 🤖 AI - eslint 的配置文件都有哪些格式？

ESLint 支持多种配置文件格式，每种格式都有其特点和适用场景。以下是 ESLint 支持的主要配置文件格式：

1. **`.eslintrc.js` (JavaScript)**
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

2. **`.eslintrc.json` (JSON)**
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

3. **`.eslintrc.yaml` 或 `.eslintrc.yml` (YAML)**
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

4. **`.eslintrc.cjs` (CommonJS)**
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

5. **包管理器配置文件（如 `package.json`）**
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

6. **忽略文件 `.eslintignore`**
   - 虽然这不是一个配置文件，但 `.eslintignore` 文件用于指定哪些文件或目录应该被 ESLint 忽略。
   - 示例：
     ```
     node_modules/
     dist/
     build/
     ```

选择哪种格式主要取决于你的个人偏好以及项目的具体需求。通常情况下，如果不需要复杂的逻辑，推荐使用 `.eslintrc.json` 或者 `.eslintrc.yaml`，因为它们清晰且易于维护。如果你需要动态生成配置，则可以选择 `.eslintrc.js` 或 `.eslintrc.cjs`。