题目
====
![image](https://user-images.githubusercontent.com/71497784/129538144-b3348dbe-afef-4c29-a11b-2328e6784912.png)

知识点
===
1.PHP中关联数组，主要是以name【key】=vale的方式出现，以‘key‘=>'value的方式赋值

2.复习in_array（target,str)函数，是检测前面的东西(target)在不在后面的字符串中

3.mb_strsub(str,start,end)用于剪切字符串，将str的start到end部分拿出（不包括end）

4.mb_strpos(str,target)用于检索target在str的位置

5.[目录穿越](https://blog.csdn.net/weixin_43726480/article/details/113185474?utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control)

题解回顾
===
1.进网页看源码发现提示source.php

2.查看source.php

3.有点懵，确实还是PHP不熟

4.看了半天也没明白结构，自己把代码拖到PHPstrom里手动输入file值尝试（不可取，需反思）

5.大致明白逻辑了又不懂函数，还是去查了看看（早该查的）

6.这才理解运行的原理，file参数进来后进checkfile函数判断，一共三层，第一层是判断file的内容在不在白名单中，第二层通过给file最后加个？并用mb_xxx两个函数提取file参数中在？之前的内容，第三层是先解码再判断

7.了解原理了就知道了要surcease。php后面加个？来阶段了

8.但是，问号后面该填什么又没了思路

9.无奈之下看wp，发现目录穿越，最终payload为：
**source.php?/../../../../../../ffffllllaaaagggg**

10.一开始还不太理解，查了后发现其实是将source.php当作一个文档，一个“../”就是往上一个目录，要是和source。php在同一个目录下就只用一个../就行，但是由于不知道在哪，所以就需要一个个加一个个试了
