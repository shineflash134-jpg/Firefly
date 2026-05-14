---
title: nodejs
published: 2025-01-01
description: 这是文章的简短描述
image: ./cover.jpg
tags: [前端, 开发]
category: 前端开发
draft: false
---
### Nodejs安装



<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPIagKLXtw3HAz_HqfvYhDFWrW5sxEAAnUUaxulthBUxurL_SjT6HYBAAMCAAN5AAM7BA.png" style="zoom:60%;" />



安装好nodejs后，在cmd中 分别输入

```
node -v
npm -v
```



环境的配置，

找到nodejs在电脑中的安装地址，在这个安装路径下新创建两个文件夹分别是 **node_global**，**node_cache**。

<img src="./nodejs.assets/image-20260426100727191.png" alt="image-20260426100727191" style="zoom:45%;" />

**我的安装地址**

<img src="./nodejs.assets/image-20260429150851918.png" alt="image-20260429150851918" style="zoom:50%;" />

 



```
例子：
npm config set prefix "C:\Program Files\nodejs\node_global"
npm config set cache "C:\Program Files\nodejs\node_cache"

将上面的地址改为我们自己的地址，我的是
npm config set prefix "D:\develop\node\node_global"
npm config set cache "D:\develop\node\node_cache"
```



命令检验一下 是否配置正确

```
npm config get prefix
mpm config get cache
```



#### 配置环境变量

<img src="./nodejs.assets/image-20260429154132827.png" alt="image-20260429154132827" style="zoom:50%;" />



在global这个文件夹下增加一个 node_module 文件夹，

```
D:\develop\node\node_global\node_modules
```

<img src="./nodejs.assets/image-20260429154340105.png" alt="image-20260429154340105" style="zoom:50%;" />



**用户变量** （用户变量是单个用户的环境）的PATH，

将之前的 C:\Users\j\AppData\Roaming\npm ，以npm 结尾的这个地址修改为

```
D:\develop\node\node_global
```

<img src="./nodejs.assets/image-20260429154956752.png" alt="image-20260429154956752" style="zoom:50%;" />



**系统变量** （系统变量是全局的）的 path  里新建，

```
%NODE_PATH%
```

<img src="./nodejs.assets/image-20260429155125559.png" alt="image-20260429155125559" style="zoom:50%;" />



最后输入命令 进行检查

```
npm install express -g
```



##### 配置的作用

这样就可以让我们输入命令下载的程序安装在

```
D:\develop\node\node_global\node_modules
```

这个文件夹中了，

下图是下载好的opencode

<img src="./nodejs.assets/image-20260429161036335.png" alt="image-20260429161036335" style="zoom:50%;" />

















Node.js、nvm、npm和npx这四个概念到底是什么?





### Node.js

**Node.js：让JavaScript在浏览器外运行的环境**

简单来说，Node.js本质上是一个JavaScript的运行环境，它能编译并执行我们写的JavaScript代码，

<img src="./nodejs.assets/image-20260426093624142.png" alt="image-20260426093624142" style="zoom:50%;" />

在Node.js出现之前，JavaScript主要是 被浏览器解释执行的，

也就是说我们写的JS代码必须在浏览器中才能运行，而Nodejs的出现彻底改变了这一切，它把JavaScript从浏览器
的"牢笼"中解放出来，**让JavaScript可以在任何安装了Node.js的环境中执行**。



这个革命性的变化意味着什么呢?
它让我们可以用 JavaScript来开发 服务器端应用程序**，**构建后端服务，甚至开发桌面应用！



### nvm

说完Node.js，我们来看看nvm。

**nvm：解决多版本Node.js共存的问题**



nvm全称是**Node Version Management**，即**Node版本管理工具**。你可能会问：我们开发软件时通常只在一个环境里做开发，为什么需要版本管理工具呢?

主要原因是前端生态这些年发展太快了，Nodejs的更新频率非常高，版本也非常多

<img src="./nodejs.assets/image-20260426094057291.png" alt="image-20260426094057291" style="zoom:50%;" />

想象一下这种情况：一个应用是在最新版本的Node.js中开发的，但当你把它放在一个老版本的Node.js环境中运行时就可能会遇到各种兼容性问题，导致应用无法正常工作，这时nvm就派上用场了！

它是如何管理Node.js版本的呢?

nvm实际上是帮我们在同一台电脑上安装多个不同版本的Node.js，并且可以根据不同项目的需要轻松切换使用哪个版本。

比如，项目A需要Node.js 20，项目B需要Node.js 22，有了nvm，我们只需要一行命令就能完成切换非常方便!

<img src="./nodejs.assets/image-20260426094508207.png" alt="image-20260426094508207" style="zoom:50%;" />



#### nvm安装配置



home

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPMagKm9yNFyRtGXt_phmMFcwwsybsAArQUaxulthBUyXs18H3_NSsBAAMCAAN4AAM7BA.png" style="zoom:50%;" />

D:\develop\nvm\nvm



**系统链接**

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPNagKnFdDAsDHvbPZG18yBfFYp8fAAArUUaxulthBUgPSbAdakNAgBAAMCAAN4AAM7BA.png" style="zoom:50%;" />

D:\develop\nvm\nodejs



忽略

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPJagKkpTRcoMtL4GolmUN8uVkdRiAAAqcUaxulthBUfLtCnmagooUBAAMCAAN4AAM7BA.png" style="zoom:60%;" />



管理之前已下载好的node版本，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPLagKlfSLAnxToe8Pcm0mvRoZTzk0AAq4UaxulthBUOVBqontAFRQBAAMCAAN4AAM7BA.png" style="zoom:50%;" />



**检查**

```
# 查看 nvm 版本，version 可简写成 小v
nvm version
nvm v
# 显示 node 是运行在 32 位还是 64 位
nvm arch
```





#### 操作指令



##### 重点

```
# 显示已经安装的列表，list 可简化为 ls
nvm list
# 显示远程可安装的列表，list 也可简化为 ls
nvm list available
# 卸载指定版本 node
nvm uninstall [version]
# 使用指定版本 node
nvm use [version]

```



**演示**

先别敲命令，还没配置好。 

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPOagKnsXcpHrnOYBUhpJtScza_1LoAArcUaxulthBUO2yByCBe038BAAMCAAN5AAM7BA.png" style="zoom:67%;" />

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPPagKn1J0hxi1GD8hcn_-tgixPX2sAArgUaxulthBUiiqR3T17dxUBAAMCAAN5AAM7BA.png" style="zoom:57%;" />



**少用**

```
# 开启 node.js 版本管理
nvm on
# 关闭 node.js 版本管理
nvm off

```



#### 配置下载镜像

configure taobao mirror【配置下载镜像】

在 `nvm` 的安装路径下，找到 `settings.txt`，在后面加上这两行，设置国内淘宝镜像源：



```
node_mirror: https://npmmirror.com/mirrors/node/
npm_mirror: https://npmmirror.com/mirrors/npm/
```

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPQagK7Ch-UqVj-oNCeflpoo_6u7EoAAtEUaxulthBUm_FYRS7m_-YBAAMCAAN4AAM7BA.png" style="zoom:50%;" />



问题：为什么要配置镜像？

答：配置完国内的镜像后，npm install xxx 的下载速度会很快！





#### node安装



##### install node

```shell
nvm list available
nvm install 16
nvm list
nvm use 16
```

小提示：不要安装 node 的奇数版本！LTS 一般就是偶数版本。

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPRagK7eXQhSkLEA9rVtVBFIMm_d8sAAtIUaxulthBUs3SbO3m3QVQBAAMCAAN5AAM7BA.png" style="zoom:50%;" />



```
nvm use 18
```

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPSagK7uq60NiuBJNP5t45kRxV1V8AAAtMUaxulthBUbg5wKU-_zmMBAAMCAAN5AAM7BA.png" style="zoom:50%;" />



每次使用 nvm 安装 node 都需要手动创建这两个文件夹吗？

答：并不是每次都需要自己手动创建，但是第一次推荐你手动创建，以后当你设置 prefix 和 cache 后，系统会自动创建。



##### 修改 npm 默认镜像源

1. 修改 `npm` 镜像源为淘宝镜像源

```sh
npm config set registry http://registry.npmmirror.com
```

1. 检查是否成功

```sh
npm config get registry
```



<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPTagK8vzIiXZ7jHXkwCaQT0ovnv7UAAtcUaxulthBUXZ-8-piTGJkBAAMCAAN5AAM7BA.png" style="zoom:50%;" />









#### 【关键】设置全局模板（prefix）和缓存文件（cache）的存放路径：

使用nvm后，使用前要输入

```
nvm use 版本
```

`node_global`：npm install 下载的全局插件

`node_cache`：node 的缓存

```shell
# npm config set cache "%NVM_SYMLINK%\node_cache"
npm config set cache "D:\develop\nvm\nodejs\node_cache"

# npm config set prefix "%NVM_SYMLINK%\node_global"
npm config set prefix "D:\develop\nvm\nodejs\node_global"
# 可编辑 .npmrc 配置文件
npm config edit
# 查看部分 .npmrc 配置信息
npm config ls
```



输入后 查看or编辑 配置文件，

```
npm config edit
```

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPUagLBuSz98cu5btC3x1TbAwiJGYoAAuEUaxulthBUUaSSs89uK7sBAAMCAAN5AAM7BA.png" style="zoom:50%;" />

> 注意：

1. 引号里面换自己的路径
2. 引号里面的路径是软链接（`nodejs`）的路径



每次使用 nvm 安装 node 都需要配置 prefix 和 cache 吗？

答：并不需要每次都设置。配置的 prefix 和 cache 的信息都在 `C:\Users\zhuang\.npmrc` 文件里





#### 配置全局变量



此时，在环境变量中

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPVagLDiTy3a7UuYvc7g252OpHL2BMAAucUaxulthBUkVULowSIz84BAAMCAAN4AAM7BA.png" style="zoom:50%;" />



现在 ，把右侧的三个 添加到Path中

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPWagLEU8P-BWpu8wF2Vm-XvMOZ1bUAAuoUaxulthBUzsst-AnLXb0BAAMCAAN5AAM7BA.png" style="zoom:50%;" />







主要是后期你安装些命令之后，系统就会要到这里边找，





### npm

接下来是npm，全称Node Package Manager ,它是Node.js生态系统中的包管理工具。



在没有npm之前如果我们想在项目中 **使用第三方库**，(比如实现Excel文件上传功能)，

需要手动下载这些库的代码，放在项目的lib文件夹中，然后在需要的地方通过script标签引入，如果项目变得复杂，依赖的第三方库增多，而且这些库之间还可能存在复杂的依赖关系，手动管理将变得极其困难。
npm就是为了解决这个问题而生的。

<img src="./nodejs.assets/image-20260426095158287.png" alt="image-20260426095158287" style="zoom:50%;" />



有了npm，我们只需要在命令行中输入简单的命令，告诉npm我们需要哪些第三方库，它就会自动为我们下载这些库及其所有依赖，并且管理它们之间的依赖关系，同样，当我们不再需要某个库时，也可以通过npm轻松删除。

<img src="./nodejs.assets/image-20260426095323178.png" alt="image-20260426095323178" style="zoom:60%;" />





#### pnpm

[ERROR] The configured global bin directory "C:\Users\j\AppData\Local\pnpm\bin" is not in PATH Run "pnpm setup" to update your shell configuration.

提示你 pnpm 的全局命令目录没有被添加到系统的 PATH 环境变量中，并且已经贴心地给出了解决方案！

你只需要按照提示，在终端里运行下面这条命令：

powershell



```
pnpm setup
```

运行完这条命令后，pnpm 会自动帮你把相关的路径配置到系统的环境变量里。