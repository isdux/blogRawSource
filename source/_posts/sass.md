---
title: 〆 sass [manage your css]
date: 2018-09-17 11:31:55
categories: "css"
tags:
  - Technology
  - css
  - tutorial
---

**<font color="#5A5AAD"I never really noticed that I had to decide, to play someone's game or live my own life.</font>**

## <font color="#FF5151">manage your css by sass </font>使用SASS管理自己的css。
<font style="color: #394F6A; font-size: 20px; font-family: '微软雅黑'">[主要语言] sass</font>

<!--more-->

# install sass

## 命令行方式

**关于sass的使用，通常有图形化界面和命令行两种方式，作为一个有轻微技术情怀的少年，我选择使用命令行的方式**

### sass 安装

首先你需要安装node环境，至于安装方式这里不再赘述，我们的内容从nodejs安装完成后的sass安装开始:

> npm install -g sass     （anywhere）
> choco install sass     （windows）
> brew install sass/sass/sass     （mac）

### sass 关键字

#### 缩进控制层级关系

```
    nav {
      ul {
        margin: 0;
        padding: 0;
        list-style: none;
      }

      li { display: inline-block; }

      a {
        display: block;
        padding: 6px 12px;
        text-decoration: none;
      }
    }
```

#### $自定义变量

```
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```


#### @import 关键字 拆分css

> 优点：单个css更小，整体更便于层级管理和后期维护
> 缺点：每次import都需要一次request请求

```
// _reset.scss

html,
body,
ul,
ol {
  margin:  0;
  padding: 0;
}
```

```
// base.scss

@import 'reset';

body {
  font: 100% Helvetica, sans-serif;
  background-color: #efefef;
}
```

#### @mixin and @include
多用于批量前缀或者后缀等重复性工作的处理

```
@mixin transform($property) {
  -webkit-transform: $property;
      -ms-transform: $property;
          transform: $property;
}

.box { @include transform(rotate(30deg)); }
```

#### @extend 关键字

主要用于：单个选择器的样式批量添加

```
// This CSS won't print because %equal-heights is never extended.
%equal-heights {
  display: flex;
  flex-wrap: wrap;
}

// This CSS will print because %message-shared is extended.
%message-shared {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.message {
  @extend %message-shared;
}

.success {
  @extend %message-shared;
  border-color: green;
}

.error {
  @extend %message-shared;
  border-color: red;
}

.warning {
  @extend %message-shared;
  border-color: yellow;
}
```

#### 混合运算

在sass里，css可以进行数据相关混合运算

```
.container { width: 100%; }


article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}
```

