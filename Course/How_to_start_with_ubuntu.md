# Ubuntu不算折腾的记录
> 大多数小伙伴入门Linux可能都是从Ubuntu入手的，而且Ubuntu的用户量众多，相关教程也十分的充足，而不太熟练的同学，比如我，每次装个啥软件都要来回搜索，所以记录一下，日后一次到位。

## 换源
这个问题最简单，但是很多小伙伴都是栽在这上面。

![打开软件更新器](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6e5df23cdd044b7290462de779002f66~tplv-k3u1fbpfcp-zoom-1.image)

![点击设置](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1cba38ff38c14f1e8d8dc1cc3b3bb409~tplv-k3u1fbpfcp-zoom-1.image)

![选择其他站点](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b5a2fffa957a48749abd86bd4013ce47~tplv-k3u1fbpfcp-zoom-1.image)

![选择阿里云服务器](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/cd181f33e7074df8832605ae6af3e5e9~tplv-k3u1fbpfcp-zoom-1.image)

![点击关闭并重新载入](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8b5fa0c25b334e0c924e76f117d05721~tplv-k3u1fbpfcp-zoom-1.image)

这就完事了，国内下载一些东西速度会快很多

---

## 安装软件
### 安装xdman
xdman是一个下载软件，类似于Windows下的idm，先装下载器，剩下的软件下载起来也就快了嘛～
#### 下载
官网：`https://sourceforge.net/projects/xdman/files/`

github：`https://github.com/subhra74/xdm`
![https://sourceforge.net/projects/xdman/files/](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/37c5c61ea5c14c2eb154e656a6a50306~tplv-k3u1fbpfcp-zoom-1.image)

#### 安装
由于`deb`包经常会有问题，建议下载`tar.gz`、`tar.xz`之类格式的文件。
deb包的话直接双击安装即可。
tar之类的话，解压以后运行`install.sh`
```
创建安装位置
sudo mkdir /opt/xdman/
解压tar.gz压缩包
sudo tar -zxvf xxxxxx.tar.gz -C /opt/xdman/		 
或者xz格式
sudo tar -xvf xxxxxx.tar.xz -C /opt/xdman/
开始安装
sudo ./opt/xdman/install/sh
```
另外，在浏览器上安装扩展更好用噢

![点击install addon安装对应浏览器扩展](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e7624a2ed94a4903a5114c18926a1778~tplv-k3u1fbpfcp-zoom-1.image)

#### 使用
![使用xdm下载xdm](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/873f7fca688b400580a0c2166e744e5a~tplv-k3u1fbpfcp-zoom-1.image)

---
### 安装QQ
参考网址：`https://www.lulinux.com/archives/1319`
#### 下载
下载`deepin-wine` : `https://github.com/wszqkzqk/deepin-wine-ubuntu`

下载`QQ容器`：`http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin.com.qq.im/`
#### 安装
```
创建安装位置
sudo mkdir /opt/deepin-wine/
解压deepin-wine
sudo unzip xxxxxx.zip -d /opt/deepin-wine/

安装deepin-wine
sudo ./opt/deepin-wine/install.sh

安装下载好的QQ容器
deb包，双击安装即可
```
#### 部分截图

![sudo ./opt/deepin-wine/install.sh](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bd0176324f97479ca175ed5420c62413~tplv-k3u1fbpfcp-zoom-1.image)

![双击安装QQ](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ecb69833d3074e54947c539fd9d85010~tplv-k3u1fbpfcp-zoom-1.image)

![运行QQ](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ae641e027b3b487e94ee62fe406145bc~tplv-k3u1fbpfcp-zoom-1.image)

---
### 安装微信
参考：`https://zouyu4524.github.io/blog/install-wechat-on-linux-via-wine/`
#### 下载
下载`deepin-wine` : `https://github.com/wszqkzqk/deepin-wine-ubuntu`同上QQ
下载微信：`https://pc.weixin.qq.com/?t=win_weixin&platform=wx&lang=zh_CN`
#### 安装
```
安装deepin-wine——略

使用wine安装微信
WINEPREFIX=~/.deepin-wine/Wechat deepin-wine ~/Downloads/Wechat_C1018.exe   #最后的部分是刚刚下载的微信路径
```

![使用wine安装微信](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2017fb2f184e40939788406628eb4095~tplv-k3u1fbpfcp-zoom-1.image)
PS：这里如果wine依赖安装不完整，或者wine的版本过低可能会造成微信闪退，这里自行选择wine即可。
#### 使用
如果没有快捷方式的话,自己查一下wine使用吧，上面有参考链接

---
### 安装搜狗输入法
#### 下载
下载搜狗输入法`Linux`版: `https://pinyin.sogou.com/linux/`
#### 安装
```
安装依赖fcitx
sudo apt-get install fcitx-bin
sudo apt-get install fcitx-table
```
这时还要配置一下输入法

- 搜索`language`并进行设置
![按一下徽标键搜索language即可](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a33fb1c58bd14b039fc9b31ea4c9b260~tplv-k3u1fbpfcp-zoom-1.image)

![键盘输入法系统选择fcitx](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/aa23f9fd92eb468faf47301269c72769~tplv-k3u1fbpfcp-zoom-1.image)
- 最后安装搜狗拼音，双击下载好的搜狗输入法`deb`文件即可
#### 使用
选择fcitx配置，确保
![在导航中找到fcitx配置](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e30f42c9a5ef4c4fa61ccd1f07614517~tplv-k3u1fbpfcp-zoom-1.image)

![确保配置中有搜狗拼音就可以使用了](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1cd7d9f63bc040cd96f0186080b3c464~tplv-k3u1fbpfcp-zoom-1.image)
> PS:如果该有的设置没有显示出来，就等一等。

---

### 安装网易云音乐
#### 下载
下载网易云客户端:`https://music.163.com/#/download`

![网易云官网截图](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d6b6cfad5ca149ceb2a56e4b91c2bf44~tplv-k3u1fbpfcp-zoom-1.image)

#### 安装
![安装网易云音乐](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/af3ee033c6a842a288faed10152b7812~tplv-k3u1fbpfcp-zoom-1.image)

#### 使用

![使用时截图](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/58ab40069c9844a780003c8ee6d1c342~tplv-k3u1fbpfcp-zoom-1.image)

---
### 安装百度网盘
#### 下载
官网：`https://pan.baidu.com/download`

![选择deb格式](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6716cb80e7d645af8dc12b37d7e3ab2f~tplv-k3u1fbpfcp-zoom-1.image)
#### 安装
双击安装即可
![安装时截图](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b783d34308cd41cbab67a64ffe73dd16~tplv-k3u1fbpfcp-zoom-1.image)

---
### 安装python
好神奇，我以为只有`python2`竟然也自带`python3`

![Ubuntu19.10自带python](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ae94277d88e64751a5fd29c300c47263~tplv-k3u1fbpfcp-zoom-1.image)

---

### 安装jdk
#### 下载
下载jdk安装包，`tar.gz`更稳妥一点，这里以`jdk-11.0.5.tar.gz`为例
#### 安装
```
解压jdk-11.0.5.tar.gz
sudo tar -zxvf jdk-11.0.5.tar.gz -C /usr/lib/jvm/
```
解压完，配置环境就行了，其中环境变量具体看一下解压到的文件路径`/usr/lib/jvm/jdk-11.0.5/`文件夹下有没有`jre`文件夹
如果没有的话 ，就：
```
echo "export JAVA_HOME=/usr/lib/jvm/jdk-11.0.5/" >> ~/.bashrc
echo "export PATH=$PATH:$JAVA_HOME/bin" >> ~/.bashrc

如果有jre文件夹的话还要加上下面这句
echo "export CLASSPATH =.: ${JAVA_HOME}/lib" >> ~/.bashrc
```
> PS:里面的标点可别错了
#### 使用
![终端查看Java版本](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f5376b3be7534f5abb53b9311078f4cc~tplv-k3u1fbpfcp-zoom-1.image)

---
### 安装pycharm
#### 下载
官网：`https://www.jetbrains.com/pycharm/download/#section=linux`
![pycharm下载界面](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1d5c7a1fe67742bc95827662f731497d~tplv-k3u1fbpfcp-zoom-1.image)
#### 安装
软件一般会默认安装到`/opt`文件夹下，所以：
```
解压安装包
sudo tar -zxvf pycharm全名.tar.gz -C /opt/
开始安装
sudo ./opt/pycharm刚才那个文件夹/pycharm.sh
```
部分截图如下：
![不导入设置](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2c7862c4c3cb49a7b111eddf1d759588~tplv-k3u1fbpfcp-zoom-1.image)

![不发送](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ebca6b6aa09e47e38667b01233557bcb~tplv-k3u1fbpfcp-zoom-1.image)
默认安装就行
然后点击**试用**进软件

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/db3d761929644c8bb3b9da00184ea782~tplv-k3u1fbpfcp-zoom-1.image)

#### 激活
参考：`https://zhile.io/2018/08/25/jetbrains-license-server-crack.html`
采用补丁激活的方法

下载**补丁**：`https://www.lanzous.com/i914kba`
密码:后台回复“**访问密码**”获取

保存的`jetbrains-agent-offline.jar`，这里我放在安装目录的bin目录下了
![补丁位置](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b80457f0bb91486db3f33201c6c7d879~tplv-k3u1fbpfcp-zoom-1.image)

打开pycharm，找到`Configure `或` Help` ->`Edit Custom VM Options ...`在最后一行加上`-javaagent:/opt/pycharm-2019.2.5/bin/jetbrains-agent-offline.jar`其中路径自行修改
![修改文件](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3fc96b5ed622460bb1c8b9365da38d5d~tplv-k3u1fbpfcp-zoom-1.image)

**重启pycharm**，如果打不开，报错一群有关Java的信息，就删除家目录下隐藏的Pycharm文件，参考下图
![删除家目录下隐藏的Pycharm文件](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d275cf1c76824dc5ae8802dafdccbabf~tplv-k3u1fbpfcp-zoom-1.image)
然后找到`Help` -> `Register... `或 `Configure`-> `Manage License...`
选择License server方式,地址填入: http://jetbrains-license-server (应该会自
动填上)
或者点击按钮: `Discover Server`来自动填充地址。
![License server激活](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a2535282129e4fdd9770563cf7ba39af~tplv-k3u1fbpfcp-zoom-1.image)

然后打开` Help` ->`about`可以看到许可没有限制
![激活完成](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6c5ccca205854755baf45940473adf0a~tplv-k3u1fbpfcp-zoom-1.image)

#### 使用
```
首先在桌面上新建一个pycharm.desktop的文件并赋予755权限
sudo touch ~/Desktop/pycharm.desktop
sudo chmod 755 ~/Desktop/pycharm.desktop

然后在里面写入下面内容，其中Exec和Icon的路径自行修改
[Desktop Entry]
Type=Application
Name=Pycharm
GenericName=Pycharm
Comment=Pycharm
Exec=sh /opt/pycharm-2019.2.5/bin/pycharm.sh
Icon=/opt/pycharm-2019.2.5/bin/pycharm.png
Terminal=pycharm
Categories=Pycharm;
```
然后右键选择`allow lunching`
![使快捷方式生效](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f72153d0ad8b44d3a0dfebdf504101c4~tplv-k3u1fbpfcp-zoom-1.image)
![然后就有了一个pycharm的桌面图标](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/43fd04d445ec467d8bb7c95635683811~tplv-k3u1fbpfcp-zoom-1.image)
双击打开即可享用

> PS:`Jetbrains`家的其他软件也都可以，不再一一演示了。
---
### 安装electron-ssr
#### 下载
github下载：`https://github.com/qingshuisiyuan/electron-ssr-backup/releases`
从我这下载：`https://www.lanzous.com/i915lef`
密码:后台回复“**访问密码**”获取
#### 安装
双击安装即可

---

> 噗，我原来就这点需求啊，可以开始干活了……

<!--

## 最后，点个关注不迷路

> 公众号：[孟游先生的旅游笔记](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8a089ae12bfb4ca9a9e5d9ac82f58d43~tplv-k3u1fbpfcp-zoom-1.image)

-->
