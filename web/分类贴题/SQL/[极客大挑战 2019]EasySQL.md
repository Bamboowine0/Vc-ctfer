自己做的时候挺离谱的，一直在试到底是什么类型的注入.....

题目
====

![image](https://user-images.githubusercontent.com/71497784/129673496-5df35247-e8cf-4662-9c63-a346a0831635.png)  
知识点
=====
1.这种题不像自己之前学的各种SQL的各种类型的注入题，主要思路就是成功登录

2.万能密码：在查询语句的基础上加上**or** 1=1 #因为or的特性，两个表达式有一个成立就返回true，所以整条语句返回true，即可登录成功

3.url中的”#“要用%23代替！！！！（大声）

思路
====
1.这种题首先就是冲着成功登录去

2.那么在这种思路下，首先的方向就不是进数据库中查询，而是想办法登陆成功

3.猜想网站应该是验证
>select username,password from xxxx where username='balab' and password='labalaba'
是否返回true来判断登录是否成功

4.先单引号验证闭合类型，再加注释符，成了

5.在username或者password后面加万能密码，成了。
