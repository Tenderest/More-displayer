# Linux上多显示器的使用和一些命令操作
## 硬件
    首先检查设备的接线
## 软件
* 使用`xrandr`来管理显示器
    * 操作命令
    ```
    xrandr // 用来查看当前显示器的信息，查看是否连接成功
    xrandr --output xxx1 --auto --primary
    // 设置xxx1为主显示器
    xrandr --output xxx2 --left-of xxx1 --auto
    // 设置xxx2在xxx1显示器的左边，自动模式
    xrandr --output xxx2 --right-of xxx1 --auto
    // 设置xxx2在xxx1显示器的右边，自动模式
    // 如果左边不行就右边
    ```
    * 这时可能会出现花屏的问题，需要在`/etc/X11/xorg.conf`写入配置
    ```
    sudo vim /etc/X11/xorg.conf
    // 配置文件另外上传
    ```
* 也可以使用`xrandr`的图形化界面软件`arandr`来管理
    * 根据提示点，然后应用就行
---
Todo list:
 - [x] 花屏  
 - [ ] 自动回收工作区

_工作区的新建是根据鼠标聚焦的位置_  
_如果鼠标聚焦在主显示器则在主显示器上新建一个_  
_如果鼠标聚焦在外接显示器则在外接显示器上新建一个_  
_如果切换工作区鼠标则会自动切换过去工作区在的显示器_  
_如果在使用外接显示器的时候拔出接口，工作区不会自动回收相当于系统还认为有两个显示器此时再接上插口又能恢复之前的状态_  
