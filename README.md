<h1 align="center">Welcome to cli-kit 👋</h1>
<p>
  <a href="https://www.npmjs.com/package/cli-kit" target="_blank">
    <img alt="Version" src="https://img.shields.io/npm/v/cli-kit.svg">
  </a>
  <img src="https://img.shields.io/badge/node-%3E%3D8.10.0-blue.svg" />
  <a href="#" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" />
  </a>
</p>

> The scaffold demo

原理：<https://github.com/jsany/cli-theory>

![demo](./snapshots/demo.gif)

## Features

- [x] typescript
- [x] eslint、prettier、commitlint
- [x] local template
- [x] remote template
- [x] first use config

## Prerequisites

- node >=6

## Config

when `npm install` in lifecyle of `postinstall` will copy `.clikitrc.json` to `$HOME/.clikitrc.json`, then use it first, you can edit this json file what you wanna

### Field

- githubToken: String - personal github token, default is `''`
- localTemplates: Object - local template
  - name: String - it must `root/templates` first level subdirectory name
  - message: String - about this template description, it will appear in prompt
- remoteTemplates: Object - remote template
  - name: String - it must repository([go detail](https://www.npmjs.com/package/download-git-repo#repository))
  - message: String - about this template description, it will appear in prompt
  - bootstrap: Object - it will assign top default bootstrap
- bootstrap: Object - it will run after project generate
  - npm: Array - npm cmd, like `npm i`
  - git: Array - git cmd, like `git init`
  - open: Array - open cmd(ide), like `code .`

`.clikitrc.json` default is:

```json
{
  "githubToken": "",
  "localTemplates": [
    {
      "name": "template-a",
      "message": "项目A(template-a)"
    },
    {
      "name": "template-b",
      "message": "项目B(template-b)"
    }
  ],
  "remoteTemplates": [
    {
      "name": "github:jsany/template-main",
      "message": "主工程(template-main)"
    },
    {
      "name": "github:jsany/template-secondary",
      "message": "子工程(template-secondary)"
    },
    {
      "name": "github:jsany/template-lerna",
      "message": "多包工程(template-lerna)",
      "bootstrap": {
        "npm": ["yarn"]
      }
    }
  ],
  "bootstrap": {
    "npm": ["npm install"],
    "git": ["git init"],
    "open": ["code ."]
  }
}

```

## Install

```sh
yarn install
```

## Build

```sh
yarn build
```

## Link

```sh
yarn link
```

## Usage

```sh
cli-kit init
```

```sh
cli-kit info
```

```sh
cli-kit config
```

## Show your support

Give a ⭐️ if this project helped you!

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
