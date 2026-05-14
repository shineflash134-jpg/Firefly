---
title: 我的第一篇文章
published: 2025-01-01
description: 这是文章的简短描述
image: ./cover.jpg
tags: [前端, 开发]
category: 前端开发
draft: false
---

## Java的JDK



### 下载

我们先 打开命令行后输入并执行命令

```
systeminfo
```

检查自己的系统类型 （计组内容），

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPqagQ4tmXsd4WUChq6GlUNryOmSdEAAnQQaxtThyFUUbdJgdZI3rsBAAMCAAN5AAM7BA.png" style="zoom:50%;" />

是x64，



来到 官网下载jdk，[Java Downloads | Oracle 中国](https://www.oracle.com/cn/java/technologies/downloads/#java21)

镜像：[Index of java-local/jdk/8u151-b12](https://repo.huaweicloud.com/java/jdk/8u151-b12/)

在 `jdk1.8.0_151` 这个版本号中，**151 代表的是 Java 8 的第 151 次更新补丁（Update 151）**。

![](https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPsagRP2ShYAAF1VVPJ8KQQ4GVNRm_-AAIrEWsbU4cpVOXNrc6Y9I8GAQADAgADeQADOwQ.png)







##### 真假jdk

安装的时候让你设置两次路径，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPuagRWTAABhQTdF-XK6qODEIePSQskAAI0EWsbU4cpVN0CMy3VEbmBAQADAgADdwADOwQ.png" style="zoom:67%;" />



**真正的 JDK 是 文件夹 (`D:\develop\java\jdk1.8`)**。

- **证据**：这个文件夹里有 `include`（存放 C 语言头文件）、`db`（内置数据库）以及最重要的 **`src.zip`**（Java 核心类库的源代码）。





**那个 JRE 是文件夹 (`D:\develop\java\jdk1.8.0_151`)**。

- **证据**：它只有 `bin` 和 `lib`，缺少了开发所需的头文件和源码包。



1. **设置 `JAVA_HOME`**：路径填写 `D:\develop\java\jdk1.8`。
2. **设置 Path**：添加 `%JAVA_HOME%\bin`。





检查Java版本

```
java -version
```













### 管理不同的jdk

设置 JAVA_HOME时，要如下

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPtagRRHIDS8gbfTd7wzPScJyaynNYAAi0RaxtThylUBefMgYq7xCwBAAMCAAN5AAM7BA.png" style="zoom:50%;" />





 **Windows 手动管理（经典方式）**

如果你不使用第三方工具，可以通过规范的目录管理和脚本实现。

1. **独立安装**：下载不同版本的 JDK（如 JDK 8, 17, 21），安装到**不同的目录**（例如 `C:\Java\jdk-8`, `C:\Java\jdk-17`），千万不要覆盖安装。

2. 切换脚本

	：编写简单的批处理文件（

	```
	.bat
	```

	）来快速切换环境变量。

	- 创建一个 

		```
		setjdk17.bat
		```

		，内容如下：

		batch

		

		```
		set JAVA_HOME=C:\Java\jdk-17
		set PATH=%JAVA_HOME%\bin;%PATH%
		echo Switched to JDK 17
		```

	- 每次打开命令行时，先运行这个脚本即可切换当前会话的环境。

3. **注意**：不要在 Windows 系统属性里写死 `JAVA_HOME`，否则 IDE 可能会读取错误。





## idea编译报错



setting中，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPvagRX4i-8HY2HgTEzDDrpfBW5BwwAAjURaxtThylUKt67kXpi9hEBAAMCAAN3AAM7BA.png" style="zoom:50%;" />

你告诉编译器“我要用 Java 8 的语法写代码”（源发行版 8），但同时可能又不小心把它配置成了“编译成老版本格式”（目标发行版 1.5 或其他），这两者冲突了。
Java 规定：**如果你选了 Java 8 的语法，生成的目标文件也必须是 1.8 格式。**



structure里，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPxagRmu15UWDeRXCSjVgn_FMWUpEwAAlYRaxtThylUOLwJYdUQHlYBAAMCAAN5AAM7BA.png" style="zoom:60%;" />



<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAPyagRm7y-dVD7xlsBRhqwHXT4OHAkAAlcRaxtThylUiKqGbVwwmPIBAAMCAAN5AAM7BA.png" style="zoom:50%;" />





