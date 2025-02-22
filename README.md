<p align="center">
  <a href="https://cnliubx.github.io/EatGua/"><img src="https://github.com/CNLiubx/EatGua/tree/main/static/image/ClickBefore.png?raw=true" width="250" height="250" alt="EatGua"></a>
</p>
<div align="center">

# EatGua

_🍉 网页小游戏 🍉_

</div>


## 简介

小游戏：吃掉瓜瓜
改编自游戏[吃掉小鹿乃](https://xingye.me/game/eatkano/)

[English](README_EN.md)
|
[鹿乃b站](https://space.bilibili.com/316381099)
|
[二创作者B站](https://space.bilibili.com/1400417714)
|
[Github Pages](https://cnliubx.github.io/EatGua/)

## 可选功能

简易排行榜(日/周/月)已删除
详细请看原版GitHub

## 版本需求
+ MySQL 5+
+ PHP 5+

## 使用方法

注: 如果你想玩的话直接去玩就可以, 这里是如何制造你的改版

### Github Pages

点 [这里](https://www.bilibili.com/video/BV1r94y1d765) 看视频步骤

如果你不需要排行榜, 那么部署到Github Pages即可.

按照如下方法更改你想要显示的文字

1. **Fork本项目,不要在现在这个页面直接改,然后发现改不了.**

2. **打开你Fork的项目**, 找到`static/i18n/zh.json`, 找到下面这几项配置

   ```json
   {
     "game-title": "瓜瓜音游",
     "game-intro1": "从最底下瓜瓜的开始",
     "game-intro2": "看你能吃掉多少瓜瓜",
     "text-level-2": "TZL",
     "text-level-3": "TQL",
     "text-level-4": "您",
     "text-level-5": "人?"
   }
   ```

   你可以随意更改右侧文字, 就可以显示你想要的内容 **不要删掉双引号**

3. 找到`static/image`文件夹, 点击前显示的图片是`ClickBefore.png`, 点击后的图片是`ClickAfter.png`, 把他们改成你想要的即可.

    **注意文件格式, 需要是png**

4. 找到`static/music`文件夹, 点击时的音效是`tap.mp3`, 正常结束的音效是`end.mp3`, 点击错误的音效是`err.mp3`, 把他们改成你想要的即可.

   **注意文件格式, 需要是mp3**

5. 更改完毕后前往项目的`Settings` -> `Pages` -> `Source`, 选择`main` 分支然后点击`Save`.

### 部署到服务器

按照这些步骤来在你的服务器上配置排行榜的数据库

1. 创建数据库并且执行提供的脚本(这里用`gua`作为数据库名)
   ```sql
   CREATE DATABASE gua DEFAULT CHARSET=utf8;
   USE gua;
   SOURCE gua.sql;
   ```

2. 更改有数据库信息的`conn.php`为你的数据库配置

   ```php
   <?php
   // 把这里改为你的配置
   $link = new mysqli('localhost','NAME','PASSWORD','gua');
   mysqli_set_charset($link, 'utf8');
   if ($link->connect_error) {
       die("Failed to connect: " . $conn->connect_error);
   }
   $ranking = "kano_rank";
   ```


## 其它事项

点下star吧~ 欢迎pr代码
支持原作者!

