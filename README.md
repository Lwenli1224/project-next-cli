# project next cli

可能更通用的脚手架，基于 Github API v3 实现. 基于团队的 [chef-cli](https://github.com/2046/chef-cli) 增强。

## 背景和实现细节

- [搭建一个通用的脚手架](https://github.com/jiangtao/blog/issues/23)

## 下载

```bash
yarn globally add project-next-cli
npm i -g project-next-cli
```

## 支持

- 提供脚手架管理： 下载，初始化，版本选择等功能
- 基于所有的github项目组
- 增强：改变输入方式为选择，改进体验
- 增强：支持swig模板编译
- 提供interfaces接口，开发者可自定义生成的项目的选项，提供生成成功后的钩子，[点击查看实例](https://github.com/project-scaffold/cli)

## 关于interfaces

远程仓库增加interfaces接口目录，其中放置 ask.js， hook.js， 方便扩展，若没有则使用内置的ask

1. ask.js 

可以是数组， 可以是一个返回数组的方法；遵循 [Inquirer prompt参数](https://github.com/SBoudrias/Inquirer.js#prompt)

2. hook.js 

目前只提供生成成功后方法也就是after，提供给开发者作扩展用。after函数，可以是async function, 返回Promise实例的函数，普通函数。


## How to use

```bash
project install
project init
project update
project search
project uninstall <installed template>
project config set <k> <v>
project config remove <k>
project config get <k>
project config help
```

<img src="./project-next-cli.gif" />

## 文件说明

src目录下每个文件对应一个功能，project.js是入口文件，index.js是统一入口，其他*.js文件为对应的命令文件。
utils 为基础库目录， helper 为 模板引擎编译帮助文件目录

```bash
├── LICENSE
├── README.md
├── bin
│   └── project
├── package.json
├── project-next-cli.gif
├── src
│   ├── clear.js
│   ├── config.js
│   ├── helper
│   ├── index.js
│   ├── init.js
│   ├── install.js
│   ├── list.js
│   ├── project.js
│   ├── search.js
│   ├── uninstall.js
│   ├── update.js
│   └── utils
└── yarn.lock
```

## Thanks

- [download-git-repo](https://github.com/flipxfx/download-git-repo)
- [minimist](https://github.com/substack/minimist)
- [ora](https://github.com/sindresorhus/ora)
- [semver](https://github.com/npm/node-semver)
- [request](https://github.com/request/request)
- [rmfr](https://github.com/shinnn/rmfr)
- [metalsmith](https://github.com/segmentio/metalsmith)
- [eslint](https://github.com/eslint/eslint)

## TODO

- [x] 支持模板引擎
- [x] 支持外部interface，可以自定义问答输入，自定义完成后后续操作
- [ ] 测试用例

## LICENSE

MIT
