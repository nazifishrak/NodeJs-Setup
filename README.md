<img src="https://www.otricks.com/wp-content/uploads/2020/03/nodejs-typescript-otricks.com_.png"><h2>NodeJs and VS Code Configs</h2></img>

# Update Node
## Windows

1. ### Update npm
    ```
    npm install npm@latest -g
    ```
2. ### Clear npm cache
    ```
    npm cache clean -f
    ```
3. ### Install n (node version manager)
    ```
    npm install -g n
    ```
4. ### Update node to latest version
    ```
    n latest
    ```
## Mac
1. ### With Homebrew
    ```
   brew update
    brew upgrade node
    ```
    <br>
# Install and Update yarn
## On Windows

1. ### Install yarn
    ```
    npm install -g yarn
    ```
2. ### update yarn
    ```
    yarn set version latest
    ```
    ## On Mac

1. ### Install yarn
    ```
    brew install yarn
    ```
2. ### update yarn
    ```
    brew update
    brew upgrade yarn
    ```

# VS Code editor setup
## Configurations for eslint and prettier
### Go to your VS Code `settings.json` file and add the settings :
``` javascript
// config related to code formatting
"editor.defaultFormatter": "esbenp.prettier-vscode",
"editor.formatOnSave": true,
"[javascript]": {
  "editor.formatOnSave": false,
  "editor.defaultFormatter": null
},
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true,
  "source.organizeImports": true
},
"eslint.alwaysShowStatus": true
```
---
# Lint Setup
## Install Development Dependencies(Local to the working project)

```
yarn add -D eslint prettier
npx install-peerdeps --dev eslint-config-airbnb-base
yarn add -D eslint-config-prettier eslint-plugin-prettier
```
# Setup Linting Configuration file
## Create a `.eslintrc.json` file in the root folder and enter the contents below:
``` javascript
{
  "extends": ["prettier", "airbnb-base"],
  "parserOptions": {
    "ecmaVersion": 12
  },
  "env": {
    "commonjs": true,
    "node": true
  },
  "rules": {
    "no-console": 0,
    "indent": 0,
    "linebreak-style": 0,
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 4,
        "semi": true
      }
    ]
  },
  "plugins": ["prettier"]
}
```