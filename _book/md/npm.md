# npm

[TOC]

## npm是什么

**Nodejs下的包管理器。**

它是世界上最大的软件注册表，每星期大约有 30 亿次的下载量，包含超过 600000 个 *包（package）* （即，代码模块）。来自各大洲的开源软件开发者使用 npm 互相分享和借鉴。包的结构使您能够轻松跟踪依赖项和版本。

npm 由三个独立的部分组成：

| 名词               | 解释                                                         |
| ------------------ | ------------------------------------------------------------ |
| 网站               | [*网站*](https://npmjs.com/) 是开发者查找包（package）、设置参数以及管理 npm 使用体验的主要途径。 |
| 注册表（registry） | *注册表* 是一个巨大的数据库，保存了每个包（package）的信息。 |
| 命令行工具 (CLI)   | [*CLI*](https://docs.npmjs.com/cli/npm) 通过命令行或终端运行。开发者通过 CLI 与 npm 打交道。 |

## [npm的下载安装](https://www.cnblogs.com/quwaner/p/11541445.html)

| 步骤                                                         | 说明                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| 下载Node.js                                                  |                                                              |
| 打开**cmd**,输入[**echo %PATH%**]                            | 查看变量环境,查看node.js是否安装                             |
| node -v                                                      | 查看node版本号                                               |
| npm -v                                                       | 查看npm版本号                                                |
| 运行下面两条<br>[**npm config set prefix "D:\nodejs\node_global"**]<br />[**npm config set cache "D:\nodejs\node_cache"**] |                                                              |
| npm list -global                                             | 查看本地global位置                                           |
| npm config list                                              | 显示所有配置信息<br />我们关注一个配置文件C:\Users\Administrator\.npmrc<br />![img](https://images2017.cnblogs.com/blog/1287619/201712/1287619-20171212145956347-1443850138.png) |
| 查看镜像网站<br />npm config set registry                    | 镜像网站赋值<br />npm config set registry=http://registry.npm.taobao.org |
| npm info vue                                                 | 看看能否获得vue的信息                                        |
| npm install npm -g                                           | 更新npm                                                      |
| npm -v                                                       | 查看npm版本号                                                |
| npm list -global                                             | 看看全局是否为空                                             |
| 增加环境变量NODE_PATH 内容是：D:\nodejs\node_global\node_modules | 默认的模块D:\nodejs\node_modules 目录,这个是不对的           |



## npm的语法

| 语法                    | 说明           | 示例                                                         |
| ----------------------- | -------------- | ------------------------------------------------------------ |
| npm install 包 -g       | 下载包         |                                                              |
| npm update -g 包        | 更新包         |                                                              |
| npm uninstall -g 包     | 卸载包         |                                                              |
| npm info 包             | 获得包的信息   | npm info vue                                                 |
| 包 -v                   | 查看版本号     | npm -v                                                       |
| 包 -Version             | 包详细版本说明 | npm -Version                                                 |
| npm view 包 versions    | 查看全部版本   | npm view jquery  versions                                    |
| npm view 包 versions    | 查看最新版本   | npm view jquery  version                                     |
| npm config list         | 所有配置信息   |                                                              |
| npm list -global        | 本地global位置 |                                                              |
| npm config set registry | 查看镜像站     | 镜像网站赋值<br />npm config set registry=http://registry.npm.taobao.org |
|                         |                |                                                              |



## npm的常用包

#### [nrm(npm的镜像源管理工具)](https://www.jianshu.com/p/94d084ce6834)

有时候国外资源太慢，使用这个就可以快速地在 npm 源间切换

##### 安装nrm

npm install -g nrm，全局安装nrm

##### 使用nrm

执行命令nrm ls查看可选的源

其中，带*的是当前使用的源，上面的输出表明当前源是官方源。

> nrm ls
> *npm ---- https://registry.npmjs.org/
> cnpm --- http://r.cnpmjs.org/
> taobao - http://registry.npm.taobao.org/
> eu ----- http://registry.npmjs.eu/
> au ----- http://registry.npmjs.org.au/
> sl ----- http://npm.strongloop.com/
> nj ----- https://registry.nodejitsu.com/

##### 切换源

执行命令nrm use taobao

##### 增加源

执行命令 nrm add <registry> <url>，其中reigstry为源名，url为源的路径。

##### 删除源

执行命令nrm del <registry>删除对应的源。

##### 测试速度

 nrm test 测试相应源的响应时间。

nrm test npm  



## GitBook

npm install -g gitbook@3.0.0

-f

Run "npm uninstall -g gitbook" then "npm install -g gitbook-cli"

C:\Users\19168\AppData\Local\Temp\tmp-17168RvTcyHJ32hIm\node_modules\gitbook



### SUMMARY.md

决定 GitBook 的章节目录

每次修改目录需要在对应文件下初始化

gitbook init

gitbook serve

然后访问

http://localhost:4000

我们通过使用 `标题` 或者 `水平分割线` 将 GitBook 分为几个不同的部分，如下所示

```markdown
# Summary

### Part I

* [Introduction](README.md)
* [Writing is nice](part1/writing.md)
* [GitBook is nice](part1/gitbook.md)

### Part II

* [We love feedback](part2/feedback_please.md)
* [Better tools for authors](part2/better_tools.md)

---

* [Last part without title](part3/title.md)
```



### book.json

该文件主要用来存放配置信息，我先放出我的配置文件。

#### 插件

GitBook 有 [插件官网](https://links.jianshu.com/go?to=https%3A%2F%2Fplugins.gitbook.com%2F)，默认带有 5 个插件，highlight、search、sharing、font-settings、livereload，如果要去除自带的插件， 可以在插件名称前面加 `-`，比如：

```json
{
    "title": "本书标题",//本书标题
    "author": "作者",//本书作者
    "description": "本书说明",//本书描述
    "language": "zh-hans",//本书语言，中文设置 "zh-hans" 即可
    "gitbook": "3.2.3",//指定使用的 GitBook 版本
    "styles": {
        "website": "./styles/website.css"//自定义页面样式
    },
    "structure": {
        "readme": "README.md"//指定 Readme、Summary、Glossary 和 Languages 对应的文件名
    },
    "links": {
        "sidebar": {
            "测试连接": "https://blankj.com"//在左侧导航栏添加链接信息
        }
    },
    "plugins": [//配置使用的插件
        "-sharing",
        "splitter",
        "expandable-chapters-small",
        "anchors",

        "github",
        "github-buttons",
        "donate",
        "sharing-plus",
        "anchor-navigation-ex",
        "favicon"
    ],
    "pluginsConfig": {//配置插件的属性
        "github": {
            "url": "https://github.com/Blankj"
        },
        "github-buttons": {
            "buttons": [{
                "user": "Blankj",
                "repo": "glory",
                "type": "star",
                "size": "small",
                "count": true
                }
            ]
        },
        "donate": {
            "alipay": "./source/images/donate.png",
            "title": "",
            "button": "赞赏",
            "alipayText": " "
        },
        "sharing": {
            "douban": false,
            "facebook": false,
            "google": false,
            "hatenaBookmark": false,
            "instapaper": false,
            "line": false,
            "linkedin": false,
            "messenger": false,
            "pocket": false,
            "qq": false,
            "qzone": false,
            "stumbleupon": false,
            "twitter": false,
            "viber": false,
            "vk": false,
            "weibo": false,
            "whatsapp": false,
            "all": [
                "google", "facebook", "weibo", "twitter",
                "qq", "qzone", "linkedin", "pocket"
            ]
        },
        "anchor-navigation-ex": {
            "showLevel": false
        },
        "favicon":{
            "shortcut": "./source/images/favicon.jpg",
            "bookmark": "./source/images/favicon.jpg",
            "appleTouch": "./source/images/apple-touch-icon.jpg",
            "appleTouchMore": {
                "120x120": "./source/images/apple-touch-icon.jpg",
                "180x180": "./source/images/apple-touch-icon.jpg"
            }
        }
    }
}
```

