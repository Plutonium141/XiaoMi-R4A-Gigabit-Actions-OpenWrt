[Actions-OpenWrt 说明文档](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

# 适用于小米路由器4A千兆版的Actions-OpenWrt

这是一个基于[P3TERX的Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)的自动编译项目，做了一些小修改，默认用[lean的源码](https://github.com/coolsnowwolf/lede)编译，导入了[kenzok8的常用软件库](https://github.com/kenzok8/openwrt-packages.git)，由于lean源码直接编译的R4A固件经过breed控制台刷入会无限重启，需要修改`mt7621_xiaomi_mi-router-4a-3g-v2.dtsi`和`mt7621.mk`的分区信息才能正常刷入，所以对Actions-OpenWrt做出一些修改，使其可以在Github Actions上完成对文件的修改(其实是把已经修改好的文件进行替换)然后再进行编译。

- 原理基于恩山pidge的
[[恩山]分享小米R4A千兆版编译OPENWRT(Breed直刷版)](https://www.right.com.cn/forum/forum.php?mod=viewthread&tid=4052254)

- 如果实在不想编译固件可以用恩山cool_rose的
[[恩山] [R4A] lean源码openwrt固件小米4A千兆版 文件管理+清新主题+ipv6+广告屏蔽](https://www.right.com.cn/forum/thread-4083541-1-1.html)

- 已有小米R4A千兆版但是不知道怎么刷?可以去恩山看kan1111的
[[恩山] [R4A] 【2020.04.23】win10 “傻瓜版”小米4A千兆版 NO拆机 刷Padavan](https://www.right.com.cn/forum/thread-4007071-1-1.html)

## 如何使用?

- 0 先Fork这个项目
- 1 进入到自己的项目里
- 2 点击`Actions`
- 3 点击`Workflows`下的`Build OpenWrt`
- 4 找到右侧的白色下拉栏"Run workflow"并点击
- 5 点击绿色的"Run workflow"按钮即可开始编译

## 提示

- 把`.config`文件上传到本项目里即可根据你的`.config`文件编译(上传前记得把原来的`.config`删除,也可以直接修改)
- 导入的插件库是在`diy-part1.sh`配置的
- [在第4步](https://github.com/Plutonium141/XiaoMi4AG-Actions-OpenWrt#%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8)的白色下拉栏"Run workflow"会发现有一个`SSH connection to Actions`并且它的值是`false`如果改为`true`就可以用ssh进入actions了(!!!听说使用ssh连接进actions有可能导致封号!!!)
- `.github/workflows/build-openwrt.yml`里的23行为默认源码仓库,如果你想换一个源码编译可以改这一行(lean源码以外的openwrt可能会编译失败)
- `.github/workflows/build-openwrt.yml`第24行为所选源码的分支
- 具体使用方法请查看[Actions-OpenWrt作者的在线说明文档](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

## 关于本项目

- [Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)
- [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)
- [kenzok8的常用软件库](https://github.com/kenzok8/openwrt-packages.git)
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub Actions](https://github.com/features/actions)
- [OpenWrt](https://github.com/openwrt/openwrt)
