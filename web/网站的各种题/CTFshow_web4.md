web4-robots.txt
====

题目描述
----
“总有人把提示写在robots文件里提示大佬”

解题步骤
----
1.根据提示搜网站的robots

2.搜完发现robots是一种告诉爬虫那些能爬哪些不能爬的txt文件

3.搜索如何获得robots文件，发现直接
  url/robots.txt
 就可以获得robots文件
4.照找到的提示操作，得到flag

收获
------
[robots](https://baike.baidu.com/item/robots/5243374?fr=aladdin) :
当一个搜索蜘蛛访问一个站点时，它会首先检查该站点根目录下是否存在robots.txt
如果存在，搜索机器人就会按照该文件中的内容来确定访问的范围；如果该文件不存在，所有的搜索蜘蛛将能够访问网站上所有没有被口令保护的页面。
