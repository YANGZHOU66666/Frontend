# Web前端开发技术

## 1. web概述

+ 特点：易导航和图形化的界面、与平台无关性、分布式结构、动态性、交互性
+ 原理：浏览器地址栏输入统一资源定位符/超链接方式 访问指定IP地址的网页或网站

### web相关概念

+ URL 统一资源定位器

  协议类型：//服务器地址（端口号）/路径/文件名

+ web服务器

  计算机软件和硬件组成的有机整体

  第一个网页称主页

  需要为web服务器配置IP地址和域名，才能对外提供web服务

## 2. HTML

### 2.1 HTML文档结构

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Document</title>
</head>
<body>
	
</body>
</html>
```

两个<head>包裹的是头部

两个<body>包裹的是主体

### 2.2头部

+ 标题title标记

  ```html
  <title>标题显示在浏览器的标题栏上</title>
  ```

+ 元信息meta标记：描述一个HTML网页文档的属性，也称为“元信息”

  ```html
  <meta name="" content="">
  <meta http-equiv="" content="">
  ```

  meta属性分为两组：

  + name属性与content属性

    | 属性 | 值                                                       | 说明                                                         |
    | ---- | -------------------------------------------------------- | ------------------------------------------------------------ |
    | name | author<br>description<br>keywords<br>generator<br>robots | 定义网页作者<br>定义网页简短描述<br>定义网页关键词<br>定义编辑器<br>见说明表 |
  
    robots属性值及说明表：
  
    | 值                                                    | 说明                                                         |
    | ----------------------------------------------------- | ------------------------------------------------------------ |
    | all<br>none<br>index<br>noindex<br>follow<br>nofollow | 文件将被检索，且页面上的链接可以被查询<br>文件将不被检索，且页面上的链接不可被查询<br>文件将被检索<br>文件将不被检索，但页面上的链接可以被查询<br>页面上的链接可以被查询<br>文件将被检索，但页面上的链接不可以被查询 |
  
  + http-equiv属性与content属性
  
    | 属性       | 值                                               | 说明                                                         |
    | ---------- | ------------------------------------------------ | ------------------------------------------------------------ |
    | http-equiv | content-type<br>expires<br>refresh<br>set-cookie | 内容类型<br>网页缓存过期时间<br>刷新与跳转（重定向）页面<br>如果网页过期，那么存盘的cookie将被删除 |

### 2.3主体body

| 属性       | 值                                                        | 说明                                                         |
| ---------- | --------------------------------------------------------- | ------------------------------------------------------------ |
| text       | rgb(r,g,b)<br>rgb(r%,g%,b%)<br>#rrggbb或#rgb<br>colorname | rgb函数（整数），r、g、b的取值范围为0-255<br>rgb函数（百分比）r、g、b的取值范围为0-100<br>十六进制数据，期中#rgb可以转化为#rrggbb<br>颜色的英文名称，如red、green、blue等 |
| bgcolor    | 同上                                                      | 背景颜色，不建议用                                           |
| alink      | 同上                                                      | 活动链接颜色，不建议用                                       |
| link       | 同上                                                      | 未被访问链接的颜色，不建议用                                 |
| vlink      | 同上                                                      | 已被访问链接的颜色，不建议用                                 |
| background | URL                                                       | 规定背景图像，不建议用                                       |
| topmargin  | pixel                                                     | 上边距大小                                                   |
| leftmargin | pixel                                                     | 左边距大小                                                   |

### 2.4 HTML基本语法

#### 2.4.1 标记类型

+ 单（个）标记：

  + 基本语法：<标记名称>或<标记名称/>

    ```html
    例如：
    <br>表示换行
    <hr>表示水平分隔线
    <link>表示链接标记
    ```

+ 双（成对）标记

  + 基本语法：<标记名称>内容</标记名称>

    ```html
    例如：
    <strong>中间的内容会被加粗</strong>
    ```

#### 2.4.2 HTML属性

+ 基本语法：<标记名称 属性名1="属性值1" 属性名2="属性值2" …… 属性名3="属性值3">

#### 2.4.3 HTML基本语法清单

[见另一文件](D:\前端文件\基础语法整理)

### 2.5 注释

```html
<!-- 注释信息 -->
或
<comment>注释信息</comment>
```

### 2.6 HTML文档编写规范

略

### 2.7 HTML文档类型

#### 2.7.1 <!DOCTYPE>标记

