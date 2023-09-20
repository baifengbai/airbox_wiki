## 串口连接

串口连接是一种用于在计算机和外部设备之间进行数据传输的通信接口。不同与网络连接，串口不需要复杂的配置即可完成通信，因此在故障调试等方面是一种重要的连接方式。AirBox的串口位于机身的Type-C接口。下面介绍Mac平台使用minicom进行串口通信。

* minicom安装。使用` brew install minicom `即可安装minicom。
* 通过线缆将AirBox的Type-C接口和计算机连接。在计算机终端中执行`ls /dev/tty.*`命令查看串口名，一般含有usb的属于与AirBox相连的串口名。![Alt text](<./imgs/截屏2023-09-19 14.58.39.png>)</br>
如上图中的/dev/tty.usbserial-0001即为所需串口名。
* `minicom -s`进入设置菜单，选择Serial port setup进入串口设置。![Alt text](<./imgs/截屏2023-09-19 14.54.48.png>)
* 按回车返回到菜单页，然后选择Exit即可进入串口通信页面。

## 网络连接
AirBox拥有一个LAN口和一个WAN口。因此我们可以使用WAN口直接与我们的计算机相连；或者我们还可以通过LAN口接入路由器或连接共享网络的计算机；下面分别演示这两种连接方式。

#### WAN口连接
![Alt text](<./imgs/截屏2023-09-19 15.10.29.png>)将AirBox与计算机相连，然后设置计算机端的IP地址。如上图将IP获取方式设置为手动，IP地址设置为192.168.150.2，连接成功后，AirBox的IP即是192.168.150.1。
    
    注意这种方式连接AirBox并没有接入互联网。

#### LAN口连接

将AirBox的LAN口直接与路由器相连，AirBox将自动获取路由器分配的IP地址，IP地址通过路由器或者串口进入AirBox终端执行`ifconfig`查看。

由于WAN口的方式连接AirBox不能接入互联网，而使用路由器连接可能受限于设备，这种情况我们推荐一种仅通过计算机就可以LAN口连接的方式。以MacOS为例，这种方式的操作步骤如下。

![Alt text](<./imgs/截屏2023-09-19 15.54.38.png>)

- 打开系统设置-通用-共享，然后打开互联网共享的配置将网络共享到与AirBox相连的网络设备上。如上图USB 10/100/1000 LAN则是与AirBox相连的设备。点击完成，开始共享网络。

![Alt text](<./imgs/截屏2023-09-19 16.01.56.png>)

- 通过串口查看AirBox的IP地址，或者通过遍历PING的方法。如在计算机终端里执行`for i in {1..255}; do ping -c 1 -W 1 192.168.2.$i >/dev/null && echo "x.x.x.$i is online"; done`查询AirBox的IP地址。上图可知，192.168.2.4即为AirBox的IP地址。此时AirBox也接入了互联网。

