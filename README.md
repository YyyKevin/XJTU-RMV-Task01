# Task01

1. 按照给定教程安装好ubuntu22.04如下，期间未出现任何问题。![](/picture/pic.png)
2. 而后发现系统无法联网，系统右上角、设置中均找不到关于WI-FI的设置。查阅资料得知应该是ubuntu内核较旧，未对较新电脑配置相应的网卡驱动。![](/picture/p1.png)![](/picture/p2.png)在终端输入``uname -r``得知原内核版本为5.15.0。
3. 在[Ubuntu - Kernel Team Server](https://kernel.ubuntu.com/mainline/)中下载v5.19.17 Mainline Test 的四个文件，复制到ubuntu系统中，在四个文件所在的单独文件夹中启动终端，输入命令``sudo dpkg -i *.deb``解压文件将内核升级至5.19.17，后``reboot``重启。再次输入``uname -r``发现内核版本已更新至5.19.17。但依然无法连接WI-FI。
4. 切回windows查阅网卡型号如下：![](/picture/p3.png)
5. 在浏览器中搜索关于此网卡的相关驱动，发现[https://www.bilibili.com/video/BV11X4y1h7qN?p=2](https://www.bilibili.com/video/BV11X4y1h7qN?p=2)中有关于AX211型号网卡的教程，利用该up提供的文drivers-linux-firmware_20220818-1_all.deb解压安装重启后发现WI-FI即可正常连接。
6. 后测试暂未发现任何问题。![](/picture/p4.png)