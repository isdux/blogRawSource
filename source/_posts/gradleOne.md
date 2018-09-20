---
title: 〆 Gradle One
date: 2018-01-19 16:08:31
categories: "Book Notes"
tags:
  - Technology
  - Gradle
    Java
---

**<font color="#5A5AAD">⚠  Gradle   </font>**

## how to install gradle

**gradle runs on all major operating system and requires only a java jdk or jre version 7 or higher to be installed.**

<!--more-->

### install manually

* download the lastest gradle distribution
* unpack the distribution

    $ mkdir /opt/gradle
    $ unzip -d /opt/gradle gradle-4.4.1-bin.zip
    $ ls /opt/gradle/gradle-4.4.1
    LICENSE  NOTICE  bin  getting-started.html  init.d  lib  media

* configure system environment

    $ export PATH=$PATH:/opt/gradle/gradle-4.4.1/bin

### extend: upgrade with the gradle wrapper

If your existing Gradle-based build uses the Gradle Wrapper, you can easily upgrade by running the wrapper task, specifying the desired Gradle version:

$ ./gradlew wrapper --gradle-version=4.4.1 --distribution-type=bin
Note that it is not necessary for Gradle to be installed to use the Gradle wrapper. The next invocation of gradlew or gradlew.bat will download and cache the specified version of Gradle.

$ ./gradlew tasks
Downloading https://services.gradle.org/distributions/gradle-4.4.1-bin.zip
...

## get start

### creating build Scans

gradle build --scan

Create different kinds of build scans by locally modifying this quickstart project. Here are some ideas:

Edit src/main/java/example/Example.java to introduce compile errors
Edit src/test/java/example/ExampleTest.java to introduce test failures
Add more dependencies, more plugins, and more projects
Alternatively, enable one of your own builds to produce build scans by following the step-by-step instructions

### creating new gradle builds

$ mkdir basic-demo
$ cd basic-demo
$ touch build.gradle

$ gradle tasks

**Details about the wrapper task can be seen through the help task.**

$ gradle help --task wrapper

.
├── build.gradle
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradlew    **1**
└── gradlew.bat    **2**

**1** Wrapper script for Unix-based systems
**2** Wrapper script for Windows

// 查看gradle编译属性
$ ./gradlew properties

// 分别对应属性里的描述，版本信息
description = 'A trivial Gradle build'
version = '1.0'

// 查看所有gradle原生和自定义任务
$ ./gradlew tasks --all

如: build.gradle 增加 task(功能为复制src文件的内容到文件dest--dest文件夹可以不存在<自动生成>)
task copy(type: Copy) {
    from 'src'
    into 'dest'
}

// 执行gradle 任务
$ ./gradlew copy

### 创建不同的项目，不同的task可能需要不同的plugin和dependence

for exam: 压缩文件 zip 任务, 需要gradle 的 base plugin

plugins {
    id 'base'
}

task zip(type: Zip) {
    from 'src'
}

切记： plugins {} 必须在build.gradle 的最前面，top！ windows里 ./gradlew 可以用 gradle 替换

## building java applications

[More init plugin](https://docs.gradle.org/current/userguide/build_init_plugin.html?_ga=2.176129574.526839806.1516845457-121663520.1516845457)

#### $ gradle init --type <name>

    If a --type parameter is not supplied, Gradle will attempt to infer the type from the environment. For example, it will infer a type value of “pom” if it finds a pom.xml to convert to a Gradle build.

    If the type could not be inferred, the type “basic” will be used.

type 属性的 name 常见的有以下几种：

* java-application
* java-library
* scala-library
* groovy-library
* basic

执行：
$ gradle init --type java-application

├── build.gradle
├── gradle    **1**
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradlew
├── gradlew.bat
├── settings.gradle
└── src
    ├── main      **2**
    │   └── java
    │       └── App.java
    └── test      **3**
        └── java
            └── AppTest.java

**1** Generated folder for wrapper files
**2** Default Java source folder
**3** Default Java test folder

其中 build.gradle 文件如下:

apply plugin: 'java'
apply plugin: 'application'

repositories {
    jcenter()  **1**
}

dependencies {
    compile 'com.google.guava:guava:21.0'  **2**
    testCompile 'junit:junit:4.12'         **3**
}

mainClassName = 'App'  **4**

**1** public Bintray Artifactory repository
**2** Google Guava library
**3** JUnit testing library
**4** Class with "main" method (used by Application plugin)


> $ ./gradlew tasks
> >> use the tasks task to see what task has been added by the plugin.
> $ ./gradlew run
> >> The run task tells Gradle to execute the main method in the class assigned to the mainClassName property.

### 编译创建javaweb项目

#### 创建如下的格式
webdemo/
    src/
        main/
            java/
            webapp/
        test
            java/

#### 创建build.gradle文件，内容如下

plugins {
    id 'java'
    id 'war'
}

repositories {
    jcenter()
}

dependencies {
    providedCompile 'javax.servlet:javax.servlet-api:3.1.0'
    testCompile 'junit:junit:4.12'
}

#### $ gradle wrapper --gradle-version=4.5
指定gradle版本进行编译

#### 增加 gretty plugin

plugins {
    id 'java'
    id 'war'
    id 'org.akhikhl.gretty' version '1.4.2'
}

执行指令

$ ./gradlew appRun
