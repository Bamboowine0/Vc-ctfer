题目描述
====
![image](https://user-images.githubusercontent.com/71497784/129441062-4897944e-1495-4893-9c12-54eba6ab5887.png)

知识
===
1.题目中利用的是curl，了解到curl一系列的功能是和不同的服务器通信，在url中输入的数据回到PHP脚本中的curl函数中去被请求

2.curl函数又支持gopher协议，所以可以利用该协议发送post请求，了解了gopher这个“万能协议”，[详细看这](https://zhuanlan.zhihu.com/p/112055947)

3.当然题目还利用了之前学到的file为协议用于读取源码并分析

4.http的post请求格式长时间不看忘记了，这次也算是回忆了一下，and几个常见请求头的含义也得复习下

Host 设置服务器域名和TCP端口号，如果使用的是服务请求标准端口号，端口号可以省略  
Content-Length 设置**请求体**的字节长度  

解题
===
（说实话为了学习稍微高效率一点，看了WP）  
1.第一步说实话有点看经验，访问flag.php文件，发现好像有东西，用file为协议读取源码，看看咋拿flag

代码如下：
```php
<?php

error_reporting(0);

if($_SERVER["REMOTE_ADDR"] != "127.0.0.1"){
    echo "Just View From 127.0.0.1";
    return;
}

$flag=getenv("CTFHUB");
$key = md5($flag);

if(isset($_POST["key"]) && $_POST["key"] == $key){
    echo $flag;
    exit;
}
?>

<form action="/flag.php" method="post">
<input type="text" name="key">
<!-- Debug: key=<?php echo $key;?>-->
</form>
```

发现需要用post请求发个key过去（html知识需要）

2.再次访问flag.php，查看页面源代码，可以看到html中的key数值，记下备用

3.那么怎么利用url这个参数发包呢？这里就要用gopher协议了

4.在完成协议之前，先得，把post请求包写好，具体内容如下：

>POST /flag.php HTTP/1.1  (表示访问flag.php文件）
>Host: 127.0.0.1:80  （源代码中可以看出要求从本地访问，那么这里其实就是本地访问自己，所以还是127.0.0.1）
>Content-Type:application/x-www-form-urlencoded  
>Content-Length: 36  （指下面报文的长度）
>
>key=862aa48e8623f6cca4c61a2eeeccc4d8  （报文）

5.由于在整个过程中，我们先发送了一次http请求，curl又发送了一次请求，所以post请求包中的数据要经过二次url编码，其中换行符还得改为%0D%0A（具体原因待查）

6.塞到gopher协议中

>gopher://127.0.0.2:80/_(postpacket)  **注意要加_否则会少读一个字母**

7.塞到url参数上，发送看response包即可

