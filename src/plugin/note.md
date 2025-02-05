# 插件说明

`KiviBot` 的插件分为以下两种：

- `npm 插件`
- `本地插件`

不管是 npm 插件还是本地插件，他们都应该是符合 `CommonJS` 规范的 node 模块。

> node 模块，即：模块目录下存在 `index.js` 入口文件。或者，存在 `package.json` 文件并且 `package.json` 中的 `main` 字段指定了模块的入口文件。

插件配置文件统一放在了 `框架目录/data/plugins/<name>` 对应目录下（一般是 `config.json` 文件），**没做特殊说明外，大部分官方插件的配置请在此处修改，直接修改源码会在更新时被覆盖导致配置无效。**

## npm 插件

所谓 npm 插件，就是可以使用 `/plugin add` 消息指令直接从 npm 下载安装的插件（也可通过 `npm` 或者 `kivi` 命令在终端进行安装）。通常这类插件的命名遵循 `kivibot-plugin-` 开头的约定。官方插件会采取这种形式发布到 npm 提高用户体验。npm 插件需要先安装才能使用，安装完成后，会被存放于框架目录下的 `node_modules` 目录下，你可以在里面找到插件的源代码。**在使用消息指令安装或者启用插件时，不需要带上 `kivibot-plugin-` 前缀。**

## 本地插件

顾名思义，本地插件是指没有被发布到 npm 的本地插件（如用户自行开发的插件，或者一些私人插件），不需要下载。存放在框架目录下的 `plugins` 目录下。和 npm 插件一样，每一个插件都应该是一个符合 `CommonJS` 规范的 node 模块。
