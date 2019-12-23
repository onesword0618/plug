
# プロダクト作成  

## npm パッケージの作成  
```
 npm init -y  
```
> [npm-init](https://docs.npmjs.com/cli/init.html#description)  

## 内部ディレクトリ作成  
```bash
  mkdir -pv src/test && mkdir -v src/main
  mkdir -pv doc/assets/logo && mkdir -v doc/project
```
> [mkdir](https://www.gnu.org/software/coreutils/manual/html_node/mkdir-invocation.html#mkdir-invocation)  

## 開発時に利用するフレームワーク、ツール  
### テストフレームワーク  
```
  npm i -D jest
```
> [npm-install](https://docs.npmjs.com/cli/install#description)
> [npm-package-jest](https://www.npmjs.com/package/jest)
> [about-jest](https://jestjs.io/)
> [jest-Getting-started](https://jestjs.io/docs/en/getting-started.html)

```
$ npx jest --init

The following questions will help Jest to create a suitable configuration for your project

✔ Would you like to use Jest when running "test" script in "package.json"? … yes
✔ Choose the test environment that will be used for testing › node
✔ Do you want Jest to add coverage reports? … yes
✔ Automatically clear mock calls and instances between every test? … yes

✏️  Modified $HOME/src/plug/package.json

📝  Configuration file created at $HOME/src/plug/jest.config.js

```

*`$HOME` instead of your environment.* 

`jest.config.js` が生成される。

> [npm-package-npx](https://www.npmjs.com/package/npx)
> [about-npx](https://github.com/zkat/npx#readme)
> [jest-configuration](https://jestjs.io/docs/en/configuration.html)

### フォーマッター  
```
npm i -D -E prettier 
```
> [npm-package-prettier](https://www.npmjs.com/package/prettier)
> [about-prettier](https://prettier.io/)
> [prettier-Getting-started](https://prettier.io/docs/en/install.html)
> [prettier-option](https://prettier.io/docs/en/options.html)

* `-E`が付与されているのは[prettier-Getting-started](https://prettier.io/docs/en/install.html)で推奨されていたので。

## リントツール  
```
npm i -D prettier-eslint prettier-eslint-cli eslint-config-google
```

> [npm-package-prettier-eslint](https://www.npmjs.com/package/prettier-eslint)
> [about-eslint](https://eslint.org/)
> [npm-package-eslint](https://www.npmjs.com/package/eslint)
> [eslint-Getting-started](https://eslint.org/docs/user-guide/getting-started)
> [prettier-eslint](https://github.com/prettier/prettier-eslint#readme)
> [npm-package-prettier-eslint-cli](https://www.npmjs.com/package/prettier-eslint-cli)
> [prettier-eslint-cli](https://github.com/prettier/prettier-eslint-cli#readme)
> [npm-package-eslint-config-google](https://www.npmjs.com/package/eslint-config-google)
> [eslint-config-google](https://github.com/google/eslint-config-google#readme)
> [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html#formatting-braces)

`acorn-globals`,`espree`の依存関係で```npm i -D  acorn@^6.0.0```が必要
> [acorn](https://www.npmjs.com/package/acorn/v/6.0.0)
> [about-acorn](https://github.com/acornjs/acorn)

### リントツールの設定ファイル作成  
```bash
touch .eslintrc.json  
```
> [Configuring ESLint](https://eslint.org/docs/user-guide/configuring)

#### 下記の内容を記載する  
```json
{
  "extends": ["google"],
  "parserOptions": {
    "ecmaVersion": 11
  }
}
```
[eslint-extends](https://eslint.org/docs/user-guide/configuring#using-the-configuration-from-a-plugin)
[eslint-parserOptions/ecmaVersion](https://eslint.org/docs/user-guide/configuring#specifying-parser-options)
[JavaScript language resources](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Language_Resources)

TODO 開発中や、調査過程で必要だと思うパッケージが出てきたら採用する。