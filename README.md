[Actions-OpenWrt 说明文档](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

# 适用于小米路由器4A千兆版的Actions-OpenWrt

这是一个基于[P3TERX的Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)的自动编译项目，做了一些小修改，默认用[lean's OpenWRT分支](https://github.com/coolsnowwolf/lede)编译，导入了[kenzok8的常用软件库](https://github.com/kenzok8/small-package)

- 原理基于恩山pidge的
[[恩山]分享小米R4A千兆版编译OPENWRT(Breed直刷版)](https://www.right.com.cn/forum/forum.php?mod=viewthread&tid=4052254)

- 如果实在不想编译固件可以用恩山cool_rose的固件
[[恩山] [R4A] lean源码openwrt固件小米4A千兆版 文件管理+清新主题+ipv6+广告屏蔽](https://www.right.com.cn/forum/thread-4083541-1-1.html)

- 已有小米R4A千兆版但是不知道怎么刷?可以去恩山看kan1111的
[[恩山] [R4A] 【2020.04.23】win10 “傻瓜版”小米4A千兆版 NO拆机 刷Padavan](https://www.right.com.cn/forum/thread-4007071-1-1.html)

## 如何使用?

- 0 先Fork这个项目
![截图0](https://user-images.githubusercontent.com/62324696/149093848-61c37f29-78ef-47e3-8d76-e110db0a353c.jpg)
---
- 1 进入到自己的项目里
---
- 2 点击`Actions`
![截图1](https://user-images.githubusercontent.com/62324696/149089269-af2e0149-c177-4a23-ac4d-ea962b3cf499.jpg)
---
- 3 点击`Build OpenWrt`下的`Run workflow`即可开始编译
![截图2](https://user-images.githubusercontent.com/62324696/149091183-c26f7a8a-8841-444d-ad77-0b5cc4b8795b.jpg)
---
- 4 等待编译完成后再次进入`Actions`点击刚刚完成的一次编译
![截图3](https://user-images.githubusercontent.com/62324696/149091977-5dc23449-d6d9-427e-ae50-bcd504abb544.jpg)
---
- 5 点击编译完成的固件即可下载
![截图4](https://user-images.githubusercontent.com/62324696/149092391-6645411b-ec2e-4074-ae32-d74c0d5ed32d.jpg)

## 提示

- 默认的登录ip是`192.168.1.1`密码是`password`
- 本仓库偶尔会更新记得检查一下
- 你可以直接到[Releases](https://github.com/Plutonium141/XiaoMi-R4A-Gigabit-Actions-OpenWrt/releases)里去下载最近编译好的固件
- 编译好的压缩包里多个文件`openwrt-ramips-mt7621-xiaomi_mi-router-4a-gigabit-squashfs-sysupgrade.bin`就是用来刷入的固件
- ![图片](https://user-images.githubusercontent.com/62324696/161236877-316fd2ad-3bb5-4fa0-9541-f2a24059a923.png)
- r4a千兆版只有16MB的闪存，插件不要选的太多，如果太多会导致无法输出-squashfs-sysupgrade后缀的固件，算是编译失败了，要重新再来
- 把`.config`文件上传到本项目里即可根据你的`.config`文件编译(上传前记得把原来的`.config`删除,也可以直接修改)
- 如果你想自己生成`.config`文件设备类型按照这样选就可以了
- ![图片](https://user-images.githubusercontent.com/62324696/161233565-65c2a229-7aff-4828-aa1a-ff44e421c0d1.png) 
- 在编译菜单的Extra package菜单下勾选ipv6helper固件即可支持ipv6
- ![图片](https://user-images.githubusercontent.com/62324696/161233982-f2d692d2-20d0-4e52-8363-6e27dc3e5aac.png)
- 额外的插件库是在`diy-part1.sh`配置的
![图片](https://user-images.githubusercontent.com/62324696/161236686-54172b1c-ff83-414a-9f43-771b8d480074.png)
- 具体使用方法请查看[Actions-OpenWrt作者的在线说明文档](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

## 关于本项目

- [Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)
- [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)
- [kenzok8的常用软件库](https://github.com/kenzok8/small-package)
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub Actions](https://github.com/features/actions)
- [OpenWrt](https://github.com/openwrt/openwrt)
