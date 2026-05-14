---
title: maven教程
published: 2025-01-01
description: 有点东西
image: https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAP5agXACj1Hfpdyu5GkgDOxGSjyjoAAAsUhaxsAAX4oVJT1-EGUNwSqAQADAgADdwADOwQ.png
tags: [工具, 开发]
category: 工具
draft: false
---

maven是由阿帕奇软件基金会开源的一个 **自动化构建项目**,

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOLafqvV1XeNkXRjzTiL8mW37HmcfoAAuEQaxu8VdBXr1fAib68lH0BAAMCAAN4AAM7BA.png" style="zoom:50%;" />

主要是为了解决java项目中最常见的两个问题，
**依赖管理**和**项目构建**。

在java项目中
我们经常需要引入很多**第三方的库文件**，也就是jar包，

比如spring 、mybatis或者其他的一些工具库等等，
这些库文件可能还会依赖很多其他的库文件

如果我们 *手动去下载这些依赖的话，不但非常的麻烦，而且不同的依赖版本之间可能还会有冲突*，
这个时候就可以使用maven，来帮助我们管理这些依赖。

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOMafqwZ4eyTMlSHS3bRFfxVEFuwNgAAucQaxu8VdBXHMP54_SlK0gBAAMCAAN5AAM7BA.png" style="zoom:50%;" />





我们需要做的就是在一个叫做pom的XML文件中告诉我maven我们需要哪些依赖，

然后maven就可以自动的将这个jar包 以及它所依赖的所有其他的jar包，全部都下载并导入到项目中。
这就是maven在**依赖管理**方面的作用。





maven解决的另一个问题是 **构建管理**。

在java项目中，我们需要把java的源文件编译成字节码文件，然后再**把字节码文件打包成一个可执行的jar包或者WAR包**，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOQafrbEkw2iyn5g0IHulBsKx-k6skAAhIRaxu8VdBXb01HeCNm6BMBAAMCAAN5AAM7BA.png" style="zoom:50%;" />

如果没有自动化构建工具的话，这个过程就会非常的繁琐，而且容易出现各种问题，



maven提供了一个标准的项目结构和构建流程，
只需要按照这个标准来组织项目就可以非常轻松方便地执行、构建、打包和部署等工作，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAORafrcXznvOS80hmkCiuTvZZXrLLIAAhMRaxu8VdBXNQivP0AclZcBAAMCAAN4AAM7BA.png" style="zoom:40%;" />

这就是maven在构建管理方面的作用。



### pom

maven的核心概念是**项目对象模型**(Project Object Model)，
也就是pom，

它是一个XML文件，也是maven项目的核心文件
定义了项目的配置，依赖插件以及构建的过程。

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOSafrc4n1-o1XdlLqEAYTxrmPdjXQAAhQRaxu8VdBXovL6wJrPyaEBAAMCAAN5AAM7BA.png" style="zoom:33%;" />

maven和pom.XML文件之间的关系
有点类似于上节课我们讲过的make和make file，
或者前端node js项目中的NPM和package.JASON文件之间的关系，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOTafrecx4jYFjIvpwmXPFfjpCryEYAAhURaxu8VdBXEQgZoCZJdkwBAAMCAAN5AAM7BA.png" style="zoom:40%;" />

maven读取pom.XML文件之后，会根据这个文件中定义的规则去下载依赖包，
然后编译工程中的源代码，最后将工程打包成一个可执行的jar包或者war包

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOUafrhphixt9IF7Gg6KmVqjr8QEWYAAhYRaxu8VdBX5GZtQMRiYcEBAAMCAAN5AAM7BA.png" style="zoom:33%;" />

这个过程中，会**有很多的插件来帮助我们完成这些工作**。

比如编译插件，打包插件，测试插件等等
这些插件都是maven提供的，我们只需要在pom.XML文件中配置一下就可以了。

maven会自动的去执行这些插件，完成整个构建的过程。

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOVafriIdKoGRk23rtvNOD4u0Bwz6YAAhcRaxu8VdBXaPDaL7xKaQ8BAAMCAAN3AAM7BA.png" style="zoom:33%;" />



### maven仓库

在maven中有一个仓库的概念，仓库简单来说就是存放jar包的地方，
按照作用范围的不同
可以分为本地仓库，远程仓库和中央仓库，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOWafriiOdzHqTYqngPnjJ54Q0tNcIAAhgRaxu8VdBX4FfFmxnETisBAAMCAAN5AAM7BA.png" style="zoom:33%;" />



**本地仓库**就是我们自己电脑上的一个目录，
一般默认是在用户家目录下的点M2这个目录里面，这个位置可以在maven的配置文件中修改
修改的方法
后面我们会讲到这里

**远程仓库**也叫做私服仓库，一般是 ==一个公司或者组织内部搭建的一个仓库==，
用来给内部的项目提供统一的依赖管理，
这样就可以避免jar包的重复下载，
而且也可以**把一些公司内部发布的私有的jar包放到这个仓库里面供其他项目来使用**。



最常用的搭建私服仓库的工具是nexus，后面我们也会演示如何使用nexus 来搭建一个私服仓库，
远程私服仓库并不是必须的，如果没有配置的话
maven会直接去中央仓库下载依赖。



**中央仓库** 就是maven官方维护的一个仓库，
所有开源的jar包都可以在中央仓库里面找到，

maven在下载依赖的时候
会**首先去本地仓库中查找**，如果本地仓库没有的话，**再去远程仓库和中央仓库查找和下载**，
下载完成之后就会放到本地仓库里面，
下次再使用的时候，就可以直接从本地仓库中获取，而不需要再次去远程仓库或者中央仓库下载了，
这样就可以避免重复下载提高了构建的效率。





### maven安装



下载地址：[Download Apache Maven – Maven](https://maven.apache.org/download.cgi)

tar.gz文件





如果使用的是windows系统的话
步骤也是基本相同的，同样也是下载解压到本地之后，
找到系统的环境变量配置界面，
点击一下开始菜单之后
搜索环境变量
然后点击找到的这个编辑系统环境变量
在下面有一个环境变量按钮
打开之后就可以在这里添加环境变量了
先来添加一个 MAVEN_HOME的环境变量，
它的值就是maven解压之后的目录，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOXafrlQSDwdnWxj2cI47ntY9hL7x8AAh0Raxu8VdBXya6PHJhuqbgBAAMCAAN5AAM7BA.png" style="zoom:50%;" />

再把maven_home下面的bin目录
添加到path环境变量里面，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOYafrls3R1FM3_TcO1RK5KOY-tsfMAAh4Raxu8VdBXdEzjWioySdABAAMCAAN4AAM7BA.png" style="zoom:50%;" />

这样环境变量就生效了



打开一个命令提示符或者power shell
输入

```
mvn -v
```

如果能够看到maven的版本信息
那么就说明maven安装配置成功了。







### maven的配置



#### 本地仓库

安装完成之后，
还有几个需要配置的地方，
在maven的安装目录下面有一个CONFIG，目录里面有一个**settings.XML**文件，这个文件就是maven的配置文件。

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOZafrs1xwwG42MHkyTG_at0i4QLYkAAisRaxu8VdBXRC87FXi0Hc0BAAMCAAN5AAM7BA.png" style="zoom:43%;" />


我们来打开这个文件看一下
这个文件里面有很多的配置项，
先来找到 local repository， 也就是**本地仓库**这个标签，

这个标签就是用来配置本地仓库的位置的，本地仓库默认的位置是在用户家目录下的.m2这个目录里面，
直接把它改成自己想要的目录位置就可以了，

这里有个需要注意的地方，就是直接修改这里的路径是不会生效的，因为这里是被注释掉的
XML文件里面的注释和HTML是一样的。



如果想要修改的话，就需要把这一行复制到注释的外面，然后再来修改才会生效。

那我们就把这一行复制到下面，把里面的路径修改成自己家目录下的repo这个目录下，
这样就可以把本地仓库，修改成自己想要的位置了。

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOaafruYnH7U2bXJMOaJz7ythLJusYAAi0Raxu8VdBXLSmc60YI9ZgBAAMCAAN5AAM7BA.png" style="zoom:50%;" />



我的

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAObafrv1wxQ7aBi12fDi4HEmsTPv9sAAjARaxu8VdBX2J-qBv5zMx8BAAMCAAN5AAM7BA.png" style="zoom:53%;" />



#### 中央仓库

另外还有一个需要配置的地方，就是**镜像的配置**，
由于中央仓库是在国外的，有的时候国内的网络环境访问起来速度会比较慢，
这个时候就可以配置一个国内的镜像，来加速下载。

往下翻，找到MIRORS这个标签，
然后在里面添加一个镜像就可以了，每个镜像用一个mirror标签来表示。

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOcafrwdXH_jkyyBD2OaX8MCvSBA1wAAjERaxu8VdBX4DSWhfq7UPEBAAMCAAN5AAM7BA.png" style="zoom:43%;" />

比如我们要配置一个阿里云的镜像的话，
就可以在MIRORS标签里面的最后添加一个mirror镜像，

```
  <mirror>
    <id>aliyunmaven</id>
    <mirrorOf>*</mirrorOf>
    <name>阿里云公共仓库</name>
    <url>https://maven.aliyun.com/repository/public</url>
  </mirror>
```

id是aliyunmaven ，这个是镜像的唯一标识。
mirrorOf用来指定哪些仓库应该使用这个镜像，这里配置成* 就表示所有的仓库都使用这个镜像，
name表示这个镜像的名字，
URL是这个镜像的地址，也就是从哪里来下载依赖
这样就配置好了一个阿里云的镜像，

以后
maven在下载依赖的时候，就会优先从这个镜像中下载，速度会快一些。



#### 配置jdk(profiles)

最后还有个需要配置的地方 就是 **JDK的版本**，
maven默认使用的JDK版本是1.7，一般我们使用的JDK版本都是1.8以上的，

如果想要让maven默认使用我们安装的JDK版本的话，
就需要在**profiles**里面来配置一下。

我们往下翻  **找到profiles的这个标签**，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOdafryhxc78JZhL3XB6ya1Be68PTQAAjgRaxu8VdBXvPeF7XETK0gBAAMCAAN5AAM7BA.png" style="zoom:33%;" />

然后在里面添加一个profile，
把下面这段内容直接复制过来就可以了
这里使用的是JDK22版本，
如果想要使用其他的JDK版本的话，
只需要把这里的版本号改成你想要使用的版本就可以了，这样最基本的配置就完成了。

```
<profile>
        <id>jdk8</id>
        <properties>
            <maven.compiler.source>1.8</maven.compiler.source>
            <maven.compiler.target>1.8</maven.compiler.target>
        </properties>
    </profile>
    
    <profile>
        <id>jdk11</id>
        <properties>
            <maven.compiler.source>11</maven.compiler.source>
            <maven.compiler.target>11</maven.compiler.target>
        </properties>
    </profile>
    
```



**在命令行中激活指定的 profile：**

```
# 使用 JDK 8 的配置进行构建
mvn clean install -P jdk8

# 使用 JDK 11 的配置进行构建
mvn clean install -P jdk11
```







### mvn命令的使用

安装配置完成之后，
我们先来通过一个官网的简单示例，来快速了解一下如何使用，以便于对maven有一个整体的认识

我们先来打开maven的官网，
在左边导航菜单的用户中心（Use），这里找到一个快速开始指引（Getting Started Guide）,然后点击一下打开这个页面。

这个就是maven官网提供的一个快速开始的说明文档，

首先我们需要创建一个maven项目，
可以使用maven提供的一个快速开始模板来创建，
这个模板会自动生成一个标准的maven项目结构，
找到下面这一行命令，把它复制下来

```
mvn -B archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart-DarchetypeVersion=1.4
```



然后打开vs code，新建一个文档 ，把上面这行命令粘贴进去。

这里我们稍微来解释一下这个命令，
这里的group id就是 **项目的组织id**，一般是一个**公司或者组织的唯一标识**。
可以根据自己的实际情况来填写，

比较常用的方式是把域名反过来写
比如这里我们就可以把它修改成net.geekhour，

**DartifactId** 是项目的唯一标识，一般是项目工程的名字，
由于是一个maven的示例项目，所以我们把它改成maven sample

在后面是一个模板的id （DarchetypeArtifactId），
也就是maven为我们提供的各种不同类型的项目结构，这里我们直接保持默认就可以。

```
mvn -B archetype:generate -DgroupId=net.geekhour -DartifactId=maven-sample
-DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4
```



<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOeafr2IsqVkC3Spq6oDPTxrbls68IAAj4Raxu8VdBXgg8xqTPrAAH7AQADAgADdwADOwQ.png" style="zoom:50%;" />

然后我们打开一个命令行终端，把这一行命令复制下来
粘贴进去，然后回车执行一下，
这里如果是第一次执行的话会需要一点时间
因为会需要下载一些文件，我们稍微等一下
好的执行完成了
可以看到这里输出了一个**build success**，也就是构建成功的提示。



然后我们可以看到在当前目录下
就多了一个maven sample这个目录。

这个就是maven帮我们生成的一个项目，
来进入到这个目录下面，然后使用vs code单独来打开这个目录
这样左边的目录结构看起来更加清晰一些，
先来看一下这个项目的结构，
这就是一个标准的maven项目结构，
里面有一个SRC目录，
下面分别是用来 **存放项目源码的main目录** 和 **存放单元测试源码的test目录**，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOfafr2zs4mJCXjJ73Ky6YM5tW0kPMAAj8Raxu8VdBXMrUgtxMpi2IBAAMCAAN4AAM7BA.png" style="zoom:67%;" />

在他们里面也分别生成了两个源文件，

一个app.java文件，
内容非常简单，就是打印一行hello world。

还有一个用来执行单元测试的appTest.java文件里面也自动生成了一些简单的测试用例代码。



然后下面还有一个pom.XML文件，
这个文件就是maven工程的核心配置文件，

我们来看一下这个文件的内容，
最上面的是XML的声明和一个project的标签以及模型的版本，
这些内容基本上都是固定的不用太关注。

再往下是这个项目的一些基本信息，
可以看到这里就是根据我们刚刚输入的命令行里面的参数来生成的，
比如这里的group id，artifactid和version等等，

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOgafr3hWa99L9VU4BOoQjp5l-pAAFzAAJAEWsbvFXQV3w1WZa4OR79AQADAgADeQADOwQ.png" style="zoom:50%;" />

这就是maven项目的一个基本结构。





然后我们可以在终端 输入**maven compile**来编译项目，

```
maven compile
```

<img src="https://freeflowers134.ccwu.cc/file/AgACAgUAAyEGAATtG69eAAOhafr4aIgJcFMMJ5j7Xjd6RM8UPFQAAkMRaxu8VdBXOhiuFQ47qAcBAAMCAAN5AAM7BA.png" style="zoom:50%;" />

也需要一点时间，

编译完成了，
然后在vs code左边的目录树里面就可以看到多了一个 **target目录**，
*这个目录就是刚刚执行编译指令之后生成的*，
一般用来 **存放编译生成的字节码文件**，**以及打包后生成的jar包**



点开这个目录来看一下，
可以看到里面的一个classes目录，
再点进去就可以看到我们编译生成的app.class文件也就是app.java编译之后生成的字节码文件，



但是现在**还没有生成jar包**，
如果想要生成jar包的话，需要执行一个 ==打包的命令==，

方法就是在命令行终端再输入一个mvn package，

```
mvn package
```

就可以了

好的打包完成了，然后再来看一下target目录，
可以看到里面就多了一个maven sample的jar包，
这个就是刚刚打包生成的架包
也是这个项目 **最终的可执行文件**。

如果想要运行这个jar包的话,
可以在终端输入java杠CP
后面加上加班的位置和入口类的名称
回车之后可以看到控制台输出了hello world
就表示项目已经成功运行了
这样我们就使用命令行来完成了一个maven项目
从生成到编译再到打包和运行的整个构建过程







下面来看一下如何在idea中使用maven
idea是一个非常强大的java集成开发环境
它对于maven的支持也是非常友好的
还没有安装的同学
这里可以暂停去下载安装一下
打开idea之后
先来新建一个maven项目
项目名称
这里可以随便填一个
比如这里就叫做mon demo archetype
这里选择一个maven的模板
也就是maven帮我们定义好的
一些不同类型的项目结构
我们还是选择quick start
也就是快速开始的这个模板
然后往下拉一下
可以看到有一个高级设置的选项
点开这个选项之后
可以设置项目的group id
artifact id和版本号
其实这里和我们之前在命令行中
输入参数的方式是一样的
设置好之后
点击一下右下角的创建按钮
这样就创建好了一个maven项目
我们先来看一下这个项目的结构
可以看到和刚刚在命令行中创建的工程
是完全相同的
这里我们还需要再来修改一下idea的铭文配置
打开idea的设置界面
在左侧的菜单栏中找到构建执行部署这个选项
点开之后找到构建工具
再点开就可以看到maven了
这里就是idea的maven配置界面
我们需要设置一下maven的安装目录
找到下面的maven home pass这个选项
idea默认会自带一个maven
比如这里使用的就是自带的3.9.6
这个版本
一般我们都会把这里设置成
使用自己安装的maven
点击下拉列表右边的这个扩展按钮
然后选择maven的安装目录
点击确定就可以了
看到这里的版本号变成了3.9.8
就表示设置成功了
还有一个需要设置的地方
就是用户设置文件的位置
也就是下面这一行的user settings file
这里默认的话这里是置灰的
不可以直接修改
需要勾选一下右侧的override
也就是覆盖这个选项
这样左边的输入框就可以编辑了
点一下右边这个打开文件的按钮
然后选择之前安装好的maven的配置文件
也就是settings点XML这个文件
这里需要注意的是
下面这个本地仓库的路径
是直接从maven的配置文件中读取的
现在是在默认的点M2这个目录下
我们点击打开之后
就可以看到
这个本地仓库的位置也被自动的修改
成了之前在settings文件中设置的位置
当然这里也可以勾选右侧的覆盖栏手动修改
但是一般我们都直接从配置文件中读取
这样就设置好了idea的maven配置









回到项目中
可以看到idea右侧有一个maven的图标
点击一下就会打开maven的工具栏
最上面的一排是一些常用的功能按钮
包括重载所有项目
下载源码或者文档分析
项目依赖等等
然后下面是一个profiles的列表
这个其实就是我们在maven配置文件里面
配置的一些profile
可以在这里选择使用哪一个profile
因为现在我们只配置了一个profile
所以这里也只会显示一个
如果配置了多个的话
这里也都会显示出来
最下面就是main demo这个项目的一些信息了
点开之后可以看到里面有四个目录
分别是生命周期
插件依赖和仓库
这里的生命周期指的就是maven的构建生命周期
它定义了一系列的阶段
包括项目的清理编译测试
打包部署等等
几乎所有的构建过程
生命周期的概念是抽象的
实际上是由各种不同的插件来实现的
点开下面插件这个目录可以看到
里面列出了所有的插件
插件本质上就是一些java类
它们实现了maven的一些接口
然后在不同的生命周期阶段被妹妹调用
这些插件就是用来实现各种不同的生命周期的
可以看到
基本上和上面的生命周期是一一对应的
比如这里的clean插件
就是用来实现上面的clean生命周期的
上面的生命周期中的每一个阶段
也都是使用下面的一个或者多个插件来实现的
梅文提供了三种主要的生命周期
分别是clean default和set
clean是用来清理项目的
也就是把编译生成的字节码文件
和打包生成的架包都删除掉
这个和之前我们在命令行中执行过的maven
clean命令其实是完全相同的
在idea中可以通过双击来执行对应的生命周期
比如这里我们双击一下clean按钮
现在因为我们的项目还没有执行过编译和打包
所以这里还看不出效果
那我们先来编译一下
可以看到现在就生成了一个target目录
也就是我们编译生成的字节码文件
那现在再来双击一下clean按钮的话
就可以看到target目录被删除了
这就是clean生命周期的作用
除了clean之外
第二个最主要的生命周期就是default
也就是默认的生命周期
它包括了验证编译测试
打包检查
安装部署等等阶段
这也就是我们从头开始
构建一个项目的主要步骤
其实也就是这里除了clean和set之外的所有步骤
那我们就来逐个说明一下
首先是validate
它的作用是用来验证项目是否正确
并且所有必要的信息是可用的
我们先来执行一下
提示我们成功了
那我们稍微来修改一下pm点XML文件
把里面的group PID这一行注释掉
再来执行一下validate
可以看到这里就会提示我们缺少group id
因为group id是一个必须的配置项
如果没有配置的话
就会报错
validate的主要作用
也就是用来验证这些配置项是否正确
那我们把这个注释去掉
再来执行一下
可以看到这次就没有问题了
然后是compile
compile的作用是用来编译项目的源代码
也就是把java的源码文件编译成字节码文件
这个和我们之前在命令行中输入的maven
compile命令也是一样的
那我们来执行一下
可以看到执行之后也是生成了一个target目录
点开就可以看到里面生成的字节码文件
再往下是test
也就是单元测试
他会把项目中的单元测试用例都执行一遍
也就是我们工程中的test目录
下面的所有测试用例
我们来双击一下
测试前需要先执行编译
然后在下面执行了单元测试
结果是执行了一个测试用例
没有失败和错误
表示单元测试通过了
我们打开单元测试的原文件
找到最下面这个测试用例函数
然后把里面的断言改成false
再来执行一下测试
可以看到这次就会提示测试失败
这就是test的作用
然后再往下是package
package的作用是用来打包项目
也就是把编译生成的字节码文件
和其他的资源文件一起打包
生成一个架包或者外包
这个也是和我们在命令行中直接执行maven package
是一样的
来双击执行一下
这里有个需要注意的地方
就是执行package的时候
它不仅仅只是执行一个打包的动作
而是会先执行一下编译和测试
我们往上翻一下
可以看到在执行package之前
先执行了一下编译
然后又执行了一下测试
没有问题之后才会执行打包
这就是梅文生命周期的一个特点
它是有顺序的
每个阶段都是依赖于上一个阶段的
如果上一个阶段执行失败了
那么下一个阶段就不会再执行了
这样就可以保证整个构建过程的正确性
打包之后可以看到
在target目录下就生成了一个架包
这个价包的命名也是有规则的
前面是项目的artifact id
后面是项目的版本号
然后是verify
verify的作用是用来验证打包的结果
也就是检查打包生成的价包是否正确
是否符合质量标准以及各种规则
比如执行集成测试
验证代码质量等等
一般是在打包之后执行的
这个并不是很常用
大家了解一下就可以了
然后是install
也就是安装
install的作用
是把项目打包之后生成的架包或者外包
安装到本地仓库中
也就是把这个加包复制到我们在settings点R
XML文件中
配置的本地仓库所在的文件夹下来执行一下
可以看到执行完成之后
它提示我们已经将这个架包复制到了这个位置
那我们来复制一下这个路径
然后打开一个终端
来到这个目录下面
然后输入一个ls命令
可以看到里面就是我们刚刚打包生成的架包
那有的同学可能对于LINUX命令不太熟悉
那我们在访达里面再来打开看一下
那这里有个小技巧
就是在终端中输入一个open点号命令
就可以在访达中打开这个目录
然后把上面文件的显示方式改成芬兰的方式
这样看起来会清晰一些
可以看到最右边就是我们刚刚打包生成的架包
它在本地仓库里面的位置也是有规则的
上一级目录是版本号
再往上一级是artifact id
也就是我们项目的名称
然后再往上就是group id
group id会以点号分隔成多级目录
比如这里的net点GIO2就会被分隔成两级目录
然后再往上一级
就是我们配置的本地仓库的位置了
这样我们本地仓库里面就有了这个加包
其他模块就可以使用这个加包了
这就是install的作用
默认生命周期的最后一个阶段就是deploy
deploy的作用是把项目打包之后生成的加包
上传到远程仓库里面
一般是发布到公司内部的私服仓库
这里
由于我们还没有配置私服仓库
所以暂时先不给大家演示了
等到后面我们讲解私服仓库的时候
再来给大家演示如何配置和使用
以上就是default生命周期的所有阶段
之前我们说有三个主要的生命周期
除了clean和default之外
还有一个生命周期就是set
set是用来生成项目的站点文档的
也就是把项目的一些信息和文档
生成一个静态的网站
比如我们来执行一下
执行完成之后
可以看到target目录下面就多了一个set目录
这个就是maven为我们生成的站点文档
我们点开index点HTML
这个文件可以选择右上角的浏览器图标
这样就可以使用浏览器来查看这个站点了
这里可以查看到这个项目的一些基本信息
包括他使用了哪些依赖它的插件等等
最后还有一个需要提示的地方
就是MVN命令
后面可以跟上不同的生命周期阶段
比如m VN clean compile
就会按顺序执行clean和compile这两个阶段
那我们打开一个终端来执行一下
输入mv n clean compile之后回车
可以看到先执行了clean
然后后面紧接着又执行了compile
在实际项目中
比较常用的是mn clean package和mn clean install
也就是清理之后再执行打包或者安装
这样就可以一键完成整个构建的过程
在很多CCD的自动化构建脚本中
也经常会使用这样的方式