# 一. Gradle介绍

## 1.概述

> Gradle是一款Google推出的 **基于JVM**、 通用灵活的 项目构建工具， 支持[Maven](https://so.csdn.net/so/search?q=Maven&spm=1001.2101.3001.7020)，JCenter多种第三方仓库;支持传递性依赖管理、废弃了繁杂的xml文件，转而使用 **简洁的 、 支持多种语言** (例如：java、[groovy](https://so.csdn.net/so/search?q=groovy&spm=1001.2101.3001.7020)等)的 build脚本文件 。
>
> [官网地址:https://gradle.org/](https://gradle.org/)



## 2.常见的项目构建工具

> Ant: 2000 年Apache推出的纯Java编写构建工具，通过xml[build.xml]文件管理
> 项目优点 ：使用灵活，速度快(快于gradle和maven)，
> 缺点：Ant没有强加任何编码约定的项目目录结构,开发人员需编写繁杂XML文件构建指令,对开发人员是一个挑战。
>
> Maven: (^2004) 年Apache组织推出的再次使用xml文件[pom.xml]管理项目的构建工具。
> 优点:遵循一套约定大于配置的项目目录结构，使用统一的GAV坐标进行依赖管理, 侧重于包管理 。
> 缺点：项目构建过程僵化,配置文件编写不够灵活、不方便自定义组件,构建速度慢于gradle。
>
> Gradle: 2012 年Google推出的基于Groovy语言的全新项目构建工具，集合了Ant和Maven各自的优势。
> 优点：集Ant脚本的灵活性+Maven约定大于配置的项目目录优势,支持多种远程仓库和插件 ,侧重于大项目构建 。
> 缺点：学习成本高、资料少、脚本灵活、版本兼容性差等。
> ![img](Gradle.assets/b683bb710d0d4663bab9f551cc33ed10.png)



## 3. Gradle优势

> **依赖管理**:即将你项目中的jar包管理起来，你可以使用Maven或者Ivy的远程仓库、或者本地文件系统等
>
>  **编译打包**:可以通过脚本实现花样打包，包括修改文件、添加抑或排除某些类或资源、采用指定JDK版本构建、打包后自动上传等等等等
>
>  **多项目支持**: Gradle对多项目有着良好的支持，比如一个很具有代表性的实践就是spring framework
>
>  **多语言支持**：无论是java、groovy、scala、c++都有良好的支持
>
>  **跨平台支持**：gradle是基于jvm的，只要有jvm你就可以让gradle运行
>
>  **灵活的的脚本**：你可以使用groovy灵活的编写任务完成你想要做的任何事情



## 4. Gradle安装

### 4.1安装说明

> SpringBoot官方文档明确指出,目前SpringBoot的Gradle插件需要gradle 6. 8 版本及以上，所以我们这里选择 7 .x版本。
>
> 其中SpringBoot与Gradle存在版本兼容问题，Gradle与Idea也存在兼容问题，所以考虑到java程序员会使SpringBoot，所以要选择 6. 8 版本及高于 6. 8 版本的Gradle,那么相应的idea版本也要升级,不能太老哦。
>
> 查看本地idea 对应版本；尽量保持统一；现在推荐6.8以上；

### 4.2官网下载

> [Gradle | Releases](https://gradle.org/releases/)



### 4.3配置环境变量

1.  创建 `GRADLE_HOME` 系统变量

2.  把 `%GRADLE_HOME%\bin` 加入Path

3.  查看是否配置成功

    >  ```bash
    >  gradle -v # 查看gradle版本
    >  ```

4.  这里我们接着再配置一个 **`GRALE_USER_HOME`** 环境变量

> ![image-20221121202552250](Gradle.assets/image-20221121202552250.png)
>
> **`GRALE_USER_HOME`** 相当于配置 **Gradle 本地仓库位置**和 **Gradle Wrapper 缓存目录**





## 5. Gradle项目结构

> Gradle项目 默认目录结构和Maven项目的目录结构一致 ,都是基于 约定大于配置【ConventionOverConfiguration】。其完整项目目录结构如下所示：(**`重点在build.gradle和settings.gradle`**)
>
> ![image-20221121202925300](Gradle.assets/image-20221121202925300.png)





## 6. 创建Gradle项目

### 6.1使用在线SpringInitializr

> 网址：https://start.spring.io/
>
> ![image-20221121171140899](Gradle.assets/image-20221121171140899.png)



### 6.2 idea创建

> ![image-20221121171302744](Gradle.assets/image-20221121171302744.png)



### 6.3 命令创建

> ![image-20221121171924320](Gradle.assets/image-20221121171924320.png)
>
> ![image-20221121172105246](Gradle.assets/image-20221121172105246.png)
>
> ![在这里插入图片描述](Gradle.assets/9c8350ef024647f9ab8197e54dac27f6.png)



# 二. Gradle使用

## 1. Gradle常用指令

> | 常用命令             | 作用                       |
> | -------------------- | -------------------------- |
> | gradle clean         | 清空build目录              |
> | gradle classes       | 编译业务代码和配置文件     |
> | gradle test          | 编译测试代码，生成测试报告 |
> | gradle build         | 构建项目                   |
> | gradle build -x text | 跳过测试构建项目           |
>
> 这些命令，要在具有build.gradle的目录执行

## 2. 修改maven下载源

> 我们可以在gradle的init.d目录下创建以.gradle结尾的文件，.gradle文件可以实现在build开始之前执行，所以你可以在这个文件配置一些你想预先加载的操作。
>
> ![image-20221121173517451](Gradle.assets/image-20221121173517451.png)

> ```
> allprojects {
>     repositories {
>         mavenLocal()
>         maven { name "Alibaba" ; url "https://maven.aliyun.com/repository/public" } 
>         maven { name "Bstek" ; url "https://nexus.bsdn.org/content/groups/public/" } 
>         mavenCentral()
>     }
>     
>     buildscript {
>         repositories {
>             maven { name "Alibaba" ; url 'https://maven.aliyun.com/repository/public' } 
>             maven { name "Bstek" ; url 'https://nexus.bsdn.org/content/groups/public/' } 
>             maven { name "M2" ; url 'https://plugins.gradle.org/m2/' }
>         }
>     }
> }
> ```



## 3.启用我们写的gradle配置文件

1. 在命令行指定文件,例如：**`gradle --init-script yourdir/init.gradle -q taskName`**。你可以多次输入此命令来指定多个init文件
2. 把init.gradle文件放USER_HOME/.gradle/ 目录下
3. 把以.gradle结尾的文件放到 USER_HOME/.gradle/init.d/ 目录下
4. 把以.gradle结尾的文件放到 GRADLE_HOME/init.d/ 目录下

*  注意

   >  如果存在上面的4种方式的2种以上，gradle会按上面的1-4序号依次执行这些文件，如果给定目录下存在多个init脚本，会按拼音a-z顺序执行这些脚本，每个init脚本都存在一个对应的gradle实例,你在这个文件中调用的所有方法和属性，都会委托给这个gradle实例，每个init脚本都实现了Script接口。



## 4. 仓库地址说明

### 4.1 mavenLocal()

>  指定使用本地maven仓库，通常本地maven仓库都会通过settings.xml指定，所以gradle查找jar包的顺序如下：
>
>  `USER_HOME/.m2/settings.xml` 指定的本地仓库  -》 `M2_HOME/conf/settings.xml`指定的maven仓库  -》 `USER_HOME/.m2/repository`。

### 4.2 maven{ url }

>  指定使用maven仓库，一般用于私有仓库或其他第三方库（如阿里镜像仓库地址）

### 4.3 mavenCentral()

>  指定使用中央仓库

### 4.4 注意

>   gradle可以通过指定仓库地址为本地maven仓库地址和远程仓库地址相结合的方式，避免每次都会去远程仓库下载依赖库。这种方式也有一定的问题，如果本地maven仓库有这个依赖，就会从直接加载本地依赖，如果本地仓库没有该依赖，那么还是会从远程下载。但是**下载的jar不是存储在本地maven仓库**中，而是**放在自己的缓存目录**中，默认在 **`USER_HOME/.gradle/caches`** 目录,当然如果我们配置过 **`GRADLE_USER_HOME`** 环境变量，则会放在 **`GRADLE_USER_HOME/caches`** 目录，且**不可以将gradle caches指向maven repository**。因为caches下载文件不是按照maven仓库中存放的方式。



## 5. Gradle Wrapper

### 5.1 什么是Gradle Wrapper

>  Gradle Wrapper 实际上就是对 Gradle 的一层包装，用于解决实际开发中可能会遇到的不同的项目需要不同版本的 Gradle 问题。例如：把自己的代码共享给其他人使用，可能出现如下情况:
>
>  1.  对方电脑没有安装 gradle 
>
>  2.  对方电脑安装过 gradle，但是版本太旧了
>
>  这时候，我们就可以考虑使用 Gradle Wrapper 了。这也是官方建议使用 Gradle Wrapper 的原因。**<u>实际上有了 Gradle Wrapper 之后，我们本地是可以不配置 Gradle 的</u>**,下载 Gradle 项目后，使用 gradle 项目自带的 wrapper 操作也是可以的。



### 5.2 如何使用 Gradle Wrapper

>  项目中的 `gradlew`（用于linux）、`gradlew.bat`（用于windows） 脚本用的就是wrapper中规定的gradle版本。
>
>  ![image-20221121210145249](Gradle.assets/image-20221121210145249.png)
>
>  
>
>  而我们上面提到的 `gradle` 指令用的是本地 `gradle`，所以 `gradle` 指令和 `gradlew` 指令所使用的gradle版本有可能是不一样的。gradlew、gradlew.cmd的使用方式与gradle使用方式完全一致，只不过把gradle指令换成了gradlew指令



### 5.3 gradlew指令常用参数

>  当然,我们也可在终端执行 gradlew 指令时，指定指定一些参数,来控制 Wrapper 的生成，比如依赖的版本等
>
>  ```bash
>  gradle wrapper --gradle-version=4.4 
>  # 升级wrapper版本号,只是修改gradle.properties中wrapper版本，未实际下载
>  
>  gradle wrapper --gradle-version 5.2.1 --distribution-type all
>  # 关联源码用
>  ```



### 5.4 Gradle Wrapper的执行流程

1.  当我们第一次执行 ./gradlew build 命令的时候，gradlew 会读取 gradle-wrapper.properties 文件的配置信息

2.  准确的将指定版本的 gradle 下载并解压到指定的位置(`GRADLE_USER_HOME`目录下的`wrapper/dists`目录中) 

3.  构建本地缓存(`GRADLE_USER_HOME`目录下的`caches`目录中),下载再使用相同版本的gradle就不用下载了

4.  之后执行的 ./gradlew 所有命令都是使用指定的 gradle 版本。



### 5.5 gradle-wrapper.properties文件

>  ![image-20221121211620140](Gradle.assets/image-20221121211620140.png)

>  | 字段名           | 作用                                               |
>  | ---------------- | -------------------------------------------------- |
>  | distributionBase | 下载的Gradle压缩包解压后存储的主目录               |
>  | distributionPath | 相对于distributionBase的解压后的Gradle压缩包的路径 |
>  | distributionUrl  | Gradle发行版压缩包的下载地址                       |
>  | zipStoreBase     | 下载的Gradle压缩包存放位置                         |
>  | zipStorePath     | 相对于zipStoreBase的Gradle压缩包的路径             |

>  **注意**：前面提到的 **`GRALE_USER_HOME`** 环境变量用于 `Gradle Wrapper` 下载的特定版本的 gradle 存储目录。如果我们没有配置过 **`GRALE_USER_HOME`** 环境变量，**默认在当前用户家目录下的.gradle 文件夹**中。



# 三. Gradle与Idea

## 1. Groovy简介

>  在某种程度上，Groovy 可以被视为 Java 的一种脚本化改良版，Groovy 也是运行在 JVM 上，它可以很好地与 Java 代码及其相关库进行交互操作。它是一种成熟的面向对象编程语言，既可以面向对象编程，又可以用作纯粹的脚本语言。大多数有效的 Java 代码也可以转换为有效的 Groovy 代码，Groovy 和 Java 语言的主要区别是：完成同样的任务所需的Groovy 代码比 Java 代码更少。

*  **特点**

   >  1.  提供了动态类型转换、闭包、元编程等
   >  2.  支持函数式编程，不需要main函数
   >  3.  默认导入常用的包
   >  4.  类不支持default作用域，且默认作用域为public
   >  5.  Groovy中基本类型也是对象，可以直接调用对象的方法
   >  6.  支持 DSL（Domain Specific Languages 领域特定语言）和其它简洁的语法，让代码变得易于阅读和维护
   >  7.  Groovy 是基于 Java 语言的，所以完全兼容 Java 语法,所以对于 java 程序员学习成本较低

*  官网

   >  http://www.groovy-lang.org/documentation.html



## 2. Groovy安装

>  下载地址：https://groovy.apache.org/download.html

*  **解压并配置环境变量**

   >  ![image-20221121213918303](Gradle.assets/image-20221121213918303.png)



## 3.创建Groovy项目



## 4. Groovy基本语法



## 5. Idea创建Gradle管理的项目

### 5.1第一步：创建由 Gradle 管理的项目

>  ![image-20221121214716238](Gradle.assets/image-20221121214716238.png)



### 5.2第二步：修改当前项目使用本地安装的 gradle

>  可以加快下载项目依赖 jar 包的速度【配置了私服地址】
>
>  ![image-20221121214821318](Gradle.assets/image-20221121214821318.png)



### 5.3注意

1.  在 Terminal 中执行以 gradlew 开头命令和操作图形化的 IDEA 使用 Gradle 版本不一定是同一个版本。

    *  Terminal中以 gradlew 开头指令用的是 Wrapper 规定的 gradle 版本，wrapper 中规定版本默认和idea插件中规定的版本一致。

    *  IDEA使用Gradle是本地安装的

2.  目前只能是在创建项目时重新设置本地 gradle，创建新项目时需要重新去改

3.  当我们在 gradle.build 文件添加依赖之后 ，  这些依赖会在下载到 `GRADLE_USER_HOME/caches/modules-2/files-2.1`目录下面,所以这里的 `GRADLE_USER_HOME` 相当于 Gradle 的本地仓库，当然也可以如下方式找到 jar 包位置。

    >  ![image-20221121215639198](Gradle.assets/image-20221121215639198.png)



## 6.项目部署























