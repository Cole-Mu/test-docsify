# typora-vue-theme

[![HitCount](http://hits.dwyl.io/blinkfox/typora-vue-theme.svg)](http://hits.dwyl.io/blinkfox/typora-vue-theme) [![GitHub issues](https://img.shields.io/github/issues/blinkfox/typora-vue-theme.svg)](https://github.com/blinkfox/typora-vue-theme/issues) [![GitHub license](https://img.shields.io/github/license/blinkfox/typora-vue-theme.svg)](https://github.com/blinkfox/typora-vue-theme/blob/master/LICENSE) [![GitHub forks](https://img.shields.io/github/forks/blinkfox/typora-vue-theme.svg)](https://github.com/blinkfox/typora-vue-theme/network) [![GitHub stars](https://img.shields.io/github/stars/blinkfox/typora-vue-theme.svg)](https://github.com/blinkfox/typora-vue-theme/stargazers)

[English](README.md)

> 这是 Typora Markdown 编辑器的类似 Vue 文档风格的自定义主题。

## 简介

[Typora](https://www.typora.io/)是一款支持实时预览的 Markdown 编辑器和阅读器，支持`Windows`、`macOS`、`Linux`三大平台。Typora 作为一款合格的 Markdown 编辑器，支持图片、列表、表格、代码、公式、目录等功能，同时这款软件还支持（一键）动态预览功能，让一切都变得如此干净、纯粹。并且有多种主题模板。**[typora-vue-theme](https://github.com/blinkfox/typora-vue-theme)就是参考了[Vue](https://vuejs.org/)文档风格而开发的一个 Typora 自定义主题**。

## 安装主题

1. 下载本主题中的`vue.css`、`vue-dark.css`文件和包含字体的`vue`文件夹；
2. 打开 Typora，点击“**偏好设置**” => “**打开主题文件夹**”按钮，将弹出 Typora 的主题文件夹；
3. 将下载好的`vue.css`和`vue-dark.css`文件和包含字体的`vue`文件夹放到 Typora 的主题文件夹中；
4. 关闭并重新打开 Typora，从菜单栏中选择 “**主题**” => “**Vue**” 或者 “**Vue Dark**” 即可。

## 效果图

![vue主题效果图1](http://static.blinkfox.com/typora_vue_theme_screen_01.png)

![vue主题效果图2](http://static.blinkfox.com/typora_vue_theme_screen_02.png)

![vue主题效果图3](http://static.blinkfox.com/typora_vue_theme_screen_03.png)

### Vue Dark

![Screenshot 4](https://github.com/MamoruDS/typora-vue-theme/raw/master/screenshots/screenshot_01.png)

![Screenshot 5](https://github.com/MamoruDS/typora-vue-theme/raw/master/screenshots/screenshot_02.png)

> **感谢**: 本主题中的`vue-dark.css`来自[typora-vue-dark-theme](https://github.com/MamoruDS/typora-vue-dark-theme).

cron表达式是用来配置spring定时任务执行时间的字符串，由5个空格分隔成的6个域构成，格式如下：

{秒}  {分}  {时}  {日}  {月}  {周} {年(非必须)}
|  域  |       范围       | 特殊字符        | 是否必需 | 示例                                                         |
| :--: | :--------------: | :-------------- | :------: | ------------------------------------------------------------ |
|  秒  |       0-59       | , - * /         |    Y     | * 表示任何秒都触发，"0,3,5"表示0秒、3秒、5秒触发。           |
|  分  |       0-59       | , - * /         |    Y     | "0-3"表示0分钟到3分钟每分钟都触发，"0/2"表示只有偶数分钟触发。 |
|  时  |       0-23       | , - * /         |    Y     | "3-15/2"表示上午3点到下午3点每隔2个小时触发。                |
|  日  |       1-31       | , - * ? / L W C |    Y     | "1"表示1号执行，"5,15"表示5号和15号执行。需要注意的是，日期可以写0，不会报错但也不会生效。 |
|  月  |  1-12或JAN-DEC   | , - * /         |    Y     | "1-4,12"表示1月到4月以及12月触发。                           |
|  周  |   0-7或SUN-SAT   | , - * ? / L C # |    Y     | "?"表示一周都触发，"6,7"表示周六日触发。                     |
|  年  | empty, 1970-2099 | , - * /         |    N     |                                                              |


| 特殊字符 | 含义                                                      |
| :------: | --------------------------------------------------------- |
|    ?     | 问号 表示不确定的值                                       |
|    ,     | 逗号 指定数个值                                           |
|    -     | 指定一个值的范围                                          |
|    /     | 指定一个值的增加幅度。n/m表示从n开始，每次增加m           |
|    L     | 用在日表示一个月中的最后一天，用在周表示该月最后一个星期X |
|    W     | 指定离给定日期最近的工作日(周一到周五)                    |
|    #     | 表示该月第几个周X。6#3表示该月第3个周五                   |

> 注意，1月到12月可以用对应的英文缩写JAN-DEC代替，周日到周六可以用对应的英文缩写SUN-SAT代替。但是，**周日的缩写SUN只会被替换为0**，因此在cron表达式的周域，我们可以写6-7，却不能写SAT-SUN。

常用cron表达式

| 表达式             | 含义                                                         |
| ------------------ | ------------------------------------------------------------ |
| 0 0/5 * * * ?      | 整分开始 每隔五分钟执行一次                                  |
| 0 15 10 * * ? *    | 每天10点15分触发                                             |
| 0 15 10 * * ? 2017 | 2017年每天10点15分触发                                       |
| 0 * 14 * * ?       | 每天下午的 2点到2点59分每分触发                              |
| 0 0/5 14 * * ?     | 每天下午的 2点到2点59分(整点开始，每隔5分触发)               |
| 0 0/5 14,18 * * ?  | 每天下午的 2点到2点59分、18点到18点59分(整点开始，每隔5分触发) |
| 0 0-5 14 * * ?     | 每天下午的 2点到2点05分每分触发                              |
| 0 15 10 ? * 6L     | 每月最后一周的星期五的10点15分触发                           |
| 0 15 10 ? * 6#3    | 每月的第三周的星期五开始触发                                 |

