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
    > Dracula
    > Material icon Theme
    > Jira Code Font

const path = require('path')
path.resolve(__dirname, 'src', 'index.js')
use o path ao inves de ./src/index.js devivo as diferenças entre SOs

## Criar projeto NodeJs com TypeScript

```
$ mkdir pasta-projeto
$ cd pasta-projeto
$ yarn init -y
$ yarn add express
$ yarn add @types/express -D
$ yarn add typescript -D
$ yarn add ts-node-dev -D
$ yarn tsc --init 

Configurar tsconfig.json
    "outDir": "./dist",
    "rootDir": "./src",

Configurar script no package.json
    "scripts": {
        "build": "tsc",
        "dev:server":"ts-node-dev --transpileOnly --ignore-watch node-modules src/server.ts"
    },

```

## Padronizar editor de projetos

* Instalar plugin "EditorConfig for VS Code"
* Botão direito na pasta do projeto e escolher "Generate .editorconfig"
