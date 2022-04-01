[Actions-OpenWrt 说明文档](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

# 适用于小米路由器4A千兆版的Actions-OpenWrt

这是一个基于[P3TERX的Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)的自动编译项目，做了一些小修改，默认用[lean的源码](https://github.com/coolsnowwolf/lede)编译，导入了[kenzok8的常用软件库](https://github.com/kenzok8/small-package)，由于lean源码直接编译的R4A固件经过breed控制台刷入会无限重启，需要修改`mt7621_xiaomi_mi-router-4a-3g-v2.dtsi`和`mt7621.mk`的分区信息才能正常刷入，所以对Actions-OpenWrt做出一些修改，使其可以在Github Actions上完成对文件的修改(其实是把已经修改好的文件进行替换)然后再进行编译。

- 原理基于恩山pidge的
[[恩山]分享小米R4A千兆版编译OPENWRT(Breed直刷版)](https://www.right.com.cn/forum/forum.php?mod=viewthread&tid=4052254)

- 如果实在不想编译固件可以用恩山cool_rose的
[[恩山] [R4A] lean源码openwrt固件小米4A千兆版 文件管理+清新主题+ipv6+广告屏蔽](https://www.right.com.cn/forum/thread-4083541-1-1.html)

- 已有小米R4A千兆版但是不知道怎么刷?可以去恩山看kan1111的
[[恩山] [R4A] 【2020.04.23】win10 “傻瓜版”小米4A千兆版 NO拆机 刷Padavan](https://www.right.com.cn/forum/thread-4007071-1-1.html)

## 如何使用?

- 0 先Fork这个项目
![截图0](https://user-images.githubusercontent.com/62324696/149093848-61c37f29-78ef-47e3-8d76-e110db0a353c.jpg)
- 1 进入到自己的项目里
- 2 点击`Actions`
![截图1](https://user-images.githubusercontent.com/62324696/149089269-af2e0149-c177-4a23-ac4d-ea962b3cf499.jpg)
- 3 点击`Build OpenWrt`下的`Run workflow`即可开始编译
![截图2](https://user-images.githubusercontent.com/62324696/149091183-c26f7a8a-8841-444d-ad77-0b5cc4b8795b.jpg)
- 4 等待编译完成后再次进入`Actions`点击刚刚完成的一次编译
![截图3](https://user-images.githubusercontent.com/62324696/149091977-5dc23449-d6d9-427e-ae50-bcd504abb544.jpg)
- 5 点击编译完成的固件即可下载
![截图4](https://user-images.githubusercontent.com/62324696/149092391-6645411b-ec2e-4074-ae32-d74c0d5ed32d.jpg)

## 提示

- 把`.config`文件上传到本项目里即可根据你的`.config`文件编译(上传前记得把原来的`.config`删除,也可以直接修改)
- 自己本地生成`.config`文件的时候记得改源码里的`feeds.conf.default`文件 添加一行`src-git small8 https://github.com/kenzok8/small-package`
- 导入的插件库是在`diy-part1.sh`配置的
![截图5](https://user-images.githubusercontent.com/62324696/149093566-9a53ee64-a89f-40c5-bc6c-9986c6086e34.jpg)
- 在"Run workflow"下有一个`SSH connection to Actions`如果改为`true`就可以用ssh进入actions了![截图6](https://user-images.githubusercontent.com/62324696/149093304-a45bb61b-9bda-4365-b5c0-02354313704c.jpg)
<br>*不建议, 听说使用ssh连接进actions有可能导致封号!!!*
- 具体使用方法请查看[Actions-OpenWrt作者的在线说明文档](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

## 关于本项目

- [Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)
- [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)
- [kenzok8的常用软件库](https://github.com/kenzok8/small-package)
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub Actions](https://github.com/features/actions)
- [OpenWrt](https://github.com/openwrt/openwrt)
