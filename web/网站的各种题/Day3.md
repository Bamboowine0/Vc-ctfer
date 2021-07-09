web7_版本部署
====
题目描述
------
![image](https://user-images.githubusercontent.com/71497784/124852069-54955400-dfd6-11eb-82b4-faef0acfc05b.png)

解题与收获
----
1.开始没啥思路，看了Hint，发现url/.git/index.php
2.按上述操作直接拿flag

收获：主要就是了解下[git](https://blog.csdn.net/weixin_45158297/article/details/103133336?utm_medium=distribute.pc_relevant.none-task-blog-baidujs_title-1&spm=1001.2101.3001.42424)
,然后查了查[index.php](https://docs.joomla.org/What_is_the_purpose_of_the_index.php_file%3F)

web_8版本部署
======
题目描述
------
同上

收获
----
1.了解到了.svn文件
2.and总的来讲，版本部署这种题中，主要是由于网站制作者在布置网站的过程中，不小心把一些关键文件夹放在了根目录外，导致了代码的泄露，找到这些文件就是解体的关键。

web_9VIM
-----
题目描述
------
![image](https://user-images.githubusercontent.com/71497784/125041050-e54d5c00-e0ca-11eb-9f80-caba7578580f.png)
解题（看了hint）
------
1.其实题目描述的就是编辑文本时意外退出的情况，在这种情况下，会产生缓存文件

2.[缓存文件叫啥](https://blog.csdn.net/a597934448/article/details/105431367)

收获
----
1.vim的缓存文件


web_10cookies
------
简述
----
没啥，本来也会，就是有个url加密，上一回没写出来也是这个原因。

（url编码）[https://baike.baidu.com/item/URL%E7%BC%96%E7%A0%81/3703727?fr=aladdin]
