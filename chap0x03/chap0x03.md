# Systemd 入门教程

## 一.实验目的
* 参考Systemd入门教程进行操作，了解Systemd的主要命令

## 二.实验环境
* Ubuntu 20.04
  
## 三.实验操作录屏
### 入门篇
1. 3.2 systemd-analyze - 3.3 hostnamectl

[![3.2 systemd-analyze - 3.3 hostnamectl](https://asciinema.org/a/404088.svg)](https://asciinema.org/a/404088)

2. 3.4 localectl - 3.5 timedatectl

[![3.4 localectl - 3.5 timedatectl](https://asciinema.org/a/404095.svg)](https://asciinema.org/a/404095)

3. 3.6 loginctl

[![3.6 loginctl](https://asciinema.org/a/404102.svg)](https://asciinema.org/a/404102)

4. 4.1 systemctl list-units - 4.2 systemctl status

[![4.1-4.2](https://asciinema.org/a/404107.svg)](https://asciinema.org/a/404107)

5. 4.3 Unit管理 - 4.4 依赖关系

[![4.3-4.4](https://asciinema.org/a/404121.svg)](https://asciinema.org/a/404121)

6. 5.1-5.4 Unit的配置文件

[![5.1-5.4](https://asciinema.org/a/404134.svg)](https://asciinema.org/a/404134)

7. 6.Target

[![6.Target](https://asciinema.org/a/404317.svg)](https://asciinema.org/a/404317)

8. 7.日志管理

[![7.日志管理](https://asciinema.org/a/404324.svg)](https://asciinema.org/a/404324)

### 实战篇

[![8.实战篇](https://asciinema.org/a/404331.svg)](https://asciinema.org/a/404331)


## 四.自查清单
1. 如何添加一个用户并使其具备sudo执行程序的权限？
* 添加用户:```useradd username```
* 提升权限:```usermod -a -G adm username```

2. 如何将一个用户添加到一个用户组？
   ```usermod -a -G groupname username```

3. 如何查看当前系统的分区表和文件系统详细信息?
* 查看分区表:```sudo fdisk -l```
* 查看文件系统详细信息:```df -h```

4. 如何实现开机自动挂载Virtualbox的共享目录分区？
* 创建共享文件的挂载目录:```mkdir /mnt/share```
* 实现挂载:```mount-t vboxsf share_file_name /mnt/share ```
* 进入/etc/fstab进行编辑:```share_file_name /mnt/share vboxsf default 0 0```

5. 基于LVM（逻辑分卷管理）的分区如何实现动态扩容和缩减容量？
* 创建分区并修改为LVM模式:``` fdisk 分区名```
* 动态扩容: ```lvextend -L {{size}}```
* 缩减容量: ```lvreduce -L {{size}}```
  
6. 如何通过systemd设置实现在网络连通时运行一个指定脚本，在网络断开时运行另一个脚本？
* 修改systemd-networkd中的Service
* ExecStartPost=网络联通时运行的指定脚本
* ExecStopPost=网络断开时运行的另一个脚本

7. 如何通过systemd设置实现一个脚本在任何情况下被杀死之后会立即重新启动？实现杀不死？
* ```sudo systemctl vi scriptname```
* ```Restart = always```
* ```sudo systemctl daemon-reload```
  
## 五.参考文献
[Systemd入门教程:命令篇](http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-commands.html)<br/>
[Systemd入门教程:实战篇](http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-part-two.html)<br/>
[centos7修改服务器时间报错--Failed to set time: Automatic time synchronization is enabled](https://blog.csdn.net/xzm5708796/article/details/103733211)<br/>
[在Virtualbox下为Ubuntu20.04开机自动挂载共享目录的方法](https://blog.csdn.net/jiangdan_lili/article/details/110003759)<br/>
[LVM逻辑卷管理--在线扩容、逻辑卷与卷组容量缩减、逻辑卷快照](https://blog.51cto.com/13691477/2299707)
   
 
   
   

      
