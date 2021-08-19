其实[这篇文章](https://xz.aliyun.com/t/7405#toc-4)讲的真的很全面了，基本上一些绕过姿势都讲到了，这里补充些细节和理解

1.针对CTFhub上的URIbypass来讲，其实就是http：//要求的网址@目标网址（就是内网）/目标文件（即flag.php)

2.对于ban了127和“.”的题目，可以用localhost或者127.0.0.1的十进制数2130706433来代替（实际上ip是二进制数进行点分十进之后的产物）

8和16进制不知道为啥好像非得点，用不了，and貌似0也可以代替127.0.0.1

3.302跳转，应该一般只使用在只允许http请求的场景下，利用302跳转完成对http请求的验证，再访问目标网址

ctfhub的题目前看到的解是利用xip.ip的点（访问xip.ip的子域名相当于访问不带xip.ip的域名）来达成302跳转

4.[DNS这块](https://zhuanlan.zhihu.com/p/89426041)，其实已经将明白了，但是关于[绑域名的网站](https://lock.cmpxchg8b.com/rebinder.html?tdsourcetag=s_pctim_aiomsg)还得仔细讲讲

![image](https://user-images.githubusercontent.com/71497784/130032786-15fc9233-183d-4edf-9703-68093d9ac1a1.png)

随后多次访问127.0.0.1，总有一次访问的域名对应127.0.0.1，即可完成访问
