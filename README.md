# YankeeBBR
来自Loc大佬Yankee魔改的BBR的Debian一键安装包

## 安装命令
```bash
wget -N --no-check-certificate https://raw.githubusercontent.com/FunctionClub/YankeeBBR/master/bbr.sh && bash bbr.sh install
```

然后根据提示重启系统。

重启完成后，运行

```bash
bash bbr.sh start
```

启动魔改版BBR

## 查看魔改BBR状态
```bash
sysctl net.ipv4.tcp_available_congestion_control
```
如果看到有 **tsunami** 就表示开启成功！




## BIGDONGDONG 搭建谷歌SSR和BBR的方法：（参考）

谷歌VM实例系统里面 没有Debian8了

所以大家改用CentOS6 （就没蓝底那个窗口了）

也可以使用debian9(推荐）
使用debian9 可以只用从第5步开始（当然sudo -i 这一步还是要的）只需2步就可以搭建好。不用装BBR加速器 速度也非常的快 直接破百兆！

1：```bash sudo -i ```

(最前面显示root@xxxx)

2：wget -N --no-check-certificate https://raw.githubusercontent.com/FunctionClub/YankeeBBR/master/bbr.sh && bash bbr.sh install

蓝底窗口按TAB键选NO

选择重启 Y

这里会断开连接，大家可以关掉窗口再重新打开或几秒钟后在界面随便按几个字母 便会提示重新连接。

3：sudo -i

(最前面显示root@xxxx)

4：bash bbr.sh start

5：wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh && chmod +x shadowsocksR.sh

6：./shadowsocksR.sh

输入shadowsocks 密码

输入端口号

其他一路回车（也可自行选择混淆 协议）

在最后出现红底数据以后

谷歌云防火墙规则添加 （位置在谷歌云 VPC网络-防火墙）
点击添加新规则，然后按照一下这个设置好。这样 SSR 设置任何端口都可以使用。并且后续不需要再来防火墙规则做设置了。

![Deploy](https://user-images.githubusercontent.com/34980980/38017949-234a1e70-32a6-11e8-823f-9242466d87b7.png)


## BIGDONGDONGB ROOK 的搭建方法：（参考）

原创技术小哥的网站更多详细设置参见原贴：https://doub.io/brook-jc3/

此方式优点： 属于小众代理，被XX的概率较低，速度和SSR 不相伯仲

缺点：客户端配置不如SSR客户端丰富 比如规则之类的 设置相对麻烦或者要下对应客户端而且并不是全平台。还有就是更正一下视频里说的不支持路由器目前已知支持 软路由系统openwrt,但梅林貌似还没有。如果有我会在这里通知大家。

以下是以谷歌云为例子！！

## Part1首先搭建BBR加速

1：sudo -i

(最前面显示root@xxxx)

BBR加速 有两套代码，选其一

2（第一套）：wget -N --no-check-certificate https://raw.githubusercontent.com/FunctionClub/YankeeBBR/master/bbr.sh && bash bbr.sh install

蓝底窗口按TAB键选NO

选择重启 Y

这里会断开连接，大家可以关掉窗口再重新打开。

3：sudo -i

(最前面显示root@xxxx)

4：bash bbr.sh start

## Part2 搭建brook服务端

如果这一步之前有选Y重启的话 需要 先输入 sudo -i

5：wget -N --no-check-certificate https://softs.fun/Bash/brook.sh && chmod +x brook.sh && bash brook.sh

如果失效用这个

wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/brook.sh && chmod +x brook.sh && bash brook.sh

6：运行脚本后会出现脚本操作菜单，选择并输入 1 就会开始安装

7：输入端口 [1-65535]

(默认: 2333):

大家可以自行输入自己的端口（防火墙开通的）

8：请输入 Brook 密码

(默认: doub.io):

9：选择 Brook

Brook（新版协议，即 [servers]）

Brook Stream（旧版协议，即 [streamservers]，不推荐，除非使用新版协议速度慢）

(默认: 1. Brook（新版协议）):1
========================
协议 : servers
========================
[信息] Brook 停止成功 !

[信息] Brook 启动中...

[信息] Brook 启动成功 !

9： Brook 用户配置复制或截图
![Deploy](https://user-images.githubusercontent.com/34980980/38174986-2cc4056e-3608-11e8-9e58-f15839a9dc6d.jpg)


10：如何在手机、电脑（PC/MAC)上使用请参照视频


谷歌云防火墙规则 （说白了就是创建完实例以后需要再去防火墙那个地方打开相应的端口才可以使用实例）

谷歌云防火墙规则添加 （位置在谷歌云 VPC网络-防火墙）

点击添加新规则，然后按照一下这个设置好。这样 SSR 设置任何端口都可以使用。并且后续不需要再来防火墙规则做设置了。缺点是 所有端口开放。当然也会有一些危险。

![Deploy](https://user-images.githubusercontent.com/34980980/38160189-089475e2-34ec-11e8-81ae-96f6af6ee727.png)
