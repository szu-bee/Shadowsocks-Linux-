关于电脑上配置shadowsocks的说明网上有很多参考，部分不再另写说明。[Shadowsocks 使用说明](https://github.com/shadowsocks/shadowsocks/wiki/Shadowsocks-%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E)

这里给出Linux下客户端配置的一些参考方案：
[qt5图形界面方案](https://github.com/shadowsocks/shadowsocks-qt5/wiki/Installation)

(推荐) *python方案* 
主要分两步：
(1) 配置Shadowsocks命令行程序
(2) 配置浏览器(Chrome或Firefox)

第一步：配置Shadowsocks命令行程序
```
打开终端，输入：
sudo apt update                              // 最好先更新一下
sudo apt install python-pip                  // 安装pip 
sudo apt install python-setuptools m2crypto  // 安装setuptools和M2Crypto
sudo pip install shadowsocks                     // 安装Shadowsocks
// 启动Shadowsocks
sslocal -s 服务器域名或IP -p 服务器端口号 -k “密码” -l 1080 -t 600 -m rc4-md5 
// 例如，我的配置是：
sslocal -s proxy.xxx.com -p 23339 -k "********" -l 1080 -t 600 -m aes-256-cfb
/* 根据情况修改 */
```
第二步：配置浏览器
【此操作前需翻墙，可以用免费翻墙软件lantern临时用，获取lantern也需要翻墙，没有翻墙经验的可以找我拿】

我这里以Chrome的SwitchyOmega插件为例
先在chrome web store上搜到Proxy SwitchyOmega，点击安装
![](http://upload-images.jianshu.io/upload_images/2255197-d4db42fc69d4771d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
然后按下图所示设置即可
![](http://upload-images.jianshu.io/upload_images/2255197-5dc4da7e1ed921d5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
配置完成后，在插件设置那里切换成代理模式，就可以使用ss了！

如果不希望ss全局代理，参考以下说明：
从这里[复制最新版的txt文件链接](https://github.com/gfwlist/gfwlist)如下：![](http://upload-images.jianshu.io/upload_images/2255197-236bab8417effc9a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
粘贴到Rule List URL，再点击Download Profile Now即可下载
![](http://upload-images.jianshu.io/upload_images/2255197-a9ee8f15f353cba8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
使用时，点击绿色插件按钮，即可设置特定网址使用哪种模式，切换ss与direct两种模式
