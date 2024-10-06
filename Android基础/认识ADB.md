# 认识adb

## 什么是adb

adb是一种命令行工具，用于和Android设备进行通信。全名叫做`Android Debug Bridge`，根据英文名字就可以知道，ADB主要还是用来进行Android设备调试的工具。`adb` 提供对 Unix shell（可用来在设备上运行各种命令）的访问权限。



## adb的作用

adb的作用主要有以下几点：

设备控制、应用安装与调试、文件传输、shell命令执行、查看系统状态、控制网络、按键模拟、屏幕录制、备份与恢复、访问数据库、获取root权限等。



## adb的构成

adb的构成如下：

- client端（客户端），在电脑上发送adb调试命令
- daemon守护进程adbd（守护进程），负责接受和执行adb命令
- server端（服务端），负责管理客户端和守护进程之间的通信

原理图如下：

![adb工作原理.drawio](./%E8%AE%A4%E8%AF%86ADB.assets/adb%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86.drawio-1728216660047-2.png)



# 配置adb

## 配置环境变量

我们需要在电脑上安装adb，下载地址为：https://developer.android.google.cn/tools/releases/platform-tools?hl=zh-cn；如果你是Windows的操作系统，请下载第一个：

![image-20241006201751142](./%E8%AE%A4%E8%AF%86ADB.assets/image-20241006201751142.png)

### Windows手动安装

下载好之后如下：

![image-20241006202758374](./%E8%AE%A4%E8%AF%86ADB.assets/image-20241006202758374.png)

解压到你创建好的目录中，例如我这里在C盘创建了一个ADB的目录，并且将其解压到了该目录下

![image-20241006203537511](./%E8%AE%A4%E8%AF%86ADB.assets/image-20241006203537511.png)

#### 创建环境变量

在系统设置中，找到高级系统设置，然后点击环境变量：

![image-20241006203639582](./%E8%AE%A4%E8%AF%86ADB.assets/image-20241006203639582.png)

修改用户变量和系统变量：

![image-20241006203748526](./%E8%AE%A4%E8%AF%86ADB.assets/image-20241006203748526.png)

点击新建，把adb的路径输入，然后保存退出：

![image-20241006203844839](./%E8%AE%A4%E8%AF%86ADB.assets/image-20241006203844839.png)

进入操作系统的终端，输入以下命令查看是否能使用adb命令：

![image-20241006204008464](./%E8%AE%A4%E8%AF%86ADB.assets/image-20241006204008464.png)



### Linux手动安装

下载适用于Linux的`platform-tools-latest-linux.zip`。

解压下载的文件到某个目录下。

将解压后的目录添加到你的`PATH`环境变量中。例如，如果你解压到了`/home/rk3588s/adb`，则可以在你的`~/.bashrc`或`~/.zshrc`文件中添加以下行：

```
export PATH=$PATH:/home/rk3588s/adb
```

保存文件后，运行以下命令使变量生效：

```
source ~/.bashrc
```

或者如果你使用的是zsh：

```
source ~/.zshrc
```

运行`adb version`来验证ADB是否已正确安装。

![image-20241006204050640](./%E8%AE%A4%E8%AF%86ADB.assets/image-20241006204050640.png)



### Linux命令安装

如果你是Linux操作系统，那么可以直接使用shell命令安装更方便快捷，无需手动配置环境。如下：

基于Debian的系统：

```shell
sudo apt install -y adb
```

基于RPM的系统：

```shell
sudo yum install -y android-tools
sudo dnf install -y android-tools
```

基于Arch的系统：

```shell
sudo pacman -S android-tools
```

使用命令安装好之后不在需要进行任何配置











