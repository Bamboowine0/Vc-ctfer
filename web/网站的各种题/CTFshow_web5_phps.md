web5_phps
=====

题目描述
-----
“源代码泄露有时能帮助破解”

解题
-----
1.搜着搜着发现php的源代码存在index.phps文件里

2.搜搜咋获得该文件

3.好家伙还是url后面加东西

4.操作后直接下下来文件

5.发现flag在另一个文件里

6.打开另一个文件，获得flag

收获
-----
[index.phps](https://blog.csdn.net/loseheart157/article/details/108140659):phps文件就是php的源代码文件，通常用于提供给用户（访问者）查看php代码，因为用户无法直接通过Web浏览器看到php文件的内容，所以需要用phps文件代替。其实，只要不用php等已经在服务器中注册过的MIME类型为文件即可，但为了国际通用，所以才用了phps文件类型。
