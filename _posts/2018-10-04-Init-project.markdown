---
layout: post
title:  "Заметки. Инициализация проекта"
date:   2018-10-04 22:10:00 +0000
comments: true
tags:
- git
- npm
- babel
category: blog
---

Для себя делаю заметки как инициализирвоать проект на `js`.
Итак:
# git

![just a picture](https://img4.goodfon.ru/original/1920x1080/2/21/github-git-octocat-programming-code-it-logo.jpg)

## настройка git
```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
$ git config --global core.editor emacs
$ git config --list
user.name=John Doe
user.email=johndoe@example.com
color.status=auto
...
```

## .gitignore
```
/node_modules/
dist
```

## удаленные репозитории
```
$ git clone https://github.com/schacon/ticgit

$ git remote set-url origin https://github.com/SergAlexAnd/hexlet_1

$ git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)

$ git remote add pb https://github.com/paulboone/ticgit
$ git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)
pb	https://github.com/paulboone/ticgit (fetch)
pb	https://github.com/paulboone/ticgit (push)
```

# npm
```
$ npm init
$ npm install -g nodejs-package
```

# babel
```
$ npm install --save-dev @babel/core @babel/cli @babel/node @babel/preset-env
$ npx babel src --out-dir dist
```
## .babelrc
```
{
  "presets": [
    ["@babel/env", {
      "targets": {
        "node": "current",
        "firefox": "60",
        "chrome": "67",
        "safari": "11.1"
      }
    }]
  ]
}
```
Для винды дополнительно надо установить [Cross-env](https://github.com/kentcdodds/cross-env){:target="_blank"}
```
$ npm install --save-dev cross-env
```
## package.json - scripts
```
"build": "cross-env NODE_ENV=production babel src --out-dir dist --source-maps inline",
"prepublishOnly": "npm run build"
```
Вроде пока всё, если что-то вспомню, допишу сюда.

















