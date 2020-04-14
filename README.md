# GoStack BootCamp

**Treinamento imersivo** nas tecnologias mais modernas de desenvolvimento web e mobile.

## Anotações

```
* https://dribbble.com/
Dribbble is the leading destination to find & showcase creative work and home to the world's best design professionals.

* www.pinterest.ca
Discover recipes, home ideas, style inspiration and other ideas to try.
 
* www.figma.com
Build better products as a team. Design, prototype, and gather feedback all in one place with
 
* www.notion.so
A new tool that blends your everyday work apps into one. It's the all-in-one workspace for you and your team.
```

## Ambiente de desenvolvimento

* Node
* Yarn
* Visual Studio Code
    * Dracula
    * Material icon Theme
    * Jira Code Font

```
const path = require('path')
path.resolve(__dirname, 'src', 'index.js')
use o path ao inves de ./src/index.js devivo as diferenças entre SOs
```

## Criar projeto NodeJs com TypeScript

```
$ mkdir pasta-projeto
$ cd pasta-projeto
$ yarn init -y
$ yarn add express
$ yarn add -D @types/express typescript ts-node-dev eslint-import-resolver-typescript
$ yarn tsc --init 

Configurar tsconfig.json
    "outDir": "./dist",
    "rootDir": "./src",

Configurar script no package.json
    "scripts": {
        "build": "tsc",
        "dev:server":"ts-node-dev --transpileOnly --ignore-watch node-modules src/server.ts"
    },

Configurar .eslintrc.json
    "rules": {
        "import/extensions": [
        "error",
        "ignorePackages",
        {
            "ts": "never"
        }
        ]
    },
    "settings": {
        "import/resolver": {
        "typescript": {}
        }
    }

```

## Padronizar projeto

```
* Instalar plugin "EditorConfig for VS Code"
* Botão direito na pasta do projeto e escolher "Generate .editorconfig"

* Instalar plugin "ESLint"


$ yarn add eslint -D

$ yarn eslint --init
    ? How would you like to use ESLint? To check syntax, find problems, and enforce code style
    ? What type of modules does your project use? JavaScript modules (import/export)
    ? Which framework does your project use? None of these
    ? Does your project use TypeScript? Yes
    ? Where does your code run? Node
    ? How would you like to define a style for your project? Use a popular style guide
    ? Which style guide do you want to follow? Airbnb: https://github.com/airbnb/javascript
    ? What format do you want your config file to be in? JSON
    ? Would you like to install them now with npm? No

$ yarn add -D @typescript-eslint/eslint-plugin@latest eslint-config-airbnb-base@latest eslint-plugin-import@^2.20.1 @typescript-eslint/parser@latest

* atualizar settings.json
    "[javascript]": {
        "editor.codeActionsOnSave": {
            "source.fixAll.eslint": true,
        }
    },
    "[javascriptreact]": {
        "editor.codeActionsOnSave": {
            "source.fixAll.eslint": true,
        }
    },
    "[typescript]": {
        "editor.codeActionsOnSave": {
            "source.fixAll.eslint": true,
        }
    },
    "[typescriptreact]": {
        "editor.codeActionsOnSave": {
            "source.fixAll.eslint": true,
        }
    },
```

### Prettier

$ yarn add -D prettier eslint-config-prettier eslint-plugin-prettier

Configurar .eslintrc.json
    ...
    "extends": [
        "airbnb-base",
        "plugin:@typescript-eslint/recommended",
        "prettier/@typescript-eslint",
        "plugin:@prettier/recommended"
    ],
    ...
    "plugins": [
        "@typescript-eslint",
        "prettier"
    ],
    ...
    "rules": {
        "prettier/prettier": "error",
        "import/extensions": [
            "error",
            "ignorePackages",
            {
                "ts": "never"
            }
        ]
    },

Criar prettier.config.js
	module.exports = {
		singleQuote: true,
		trailingComma: "all",
		arrowParens: "avoid",
	};
	

### Debug

* Na guia lateral Run (bug) clicar em "create a launch.json file

```
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "attach",
      "protocol": "inspector",
      "restart": true,
      "name": "Debug",
      "skipFiles": [
        "<node_internals>/**"
      ],
      "outFiles": [
        "${workspaceFolder}/**/*.js"
      ]
    }
  ]
}
```

* Atualizar package.json

```
"dev:server": "ts-node-dev --inspect --transpileOnly --ignore-watch node-modules src/server.ts"
```
