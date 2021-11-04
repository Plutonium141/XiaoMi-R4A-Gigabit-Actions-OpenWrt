[Actions-OpenWrt 说明文档](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

# 适用于小米路由器4A千兆版/R3G v2的breed控制台的 Actions-OpenWrt

[![LICENSE](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square&label=LICENSE)](https://github.com/P3TERX/Actions-OpenWrt/blob/master/LICENSE)
![GitHub Stars](https://img.shields.io/github/stars/P3TERX/Actions-OpenWrt.svg?style=flat-square&label=Stars&logo=github)
![GitHub Forks](https://img.shields.io/github/forks/P3TERX/Actions-OpenWrt.svg?style=flat-square&label=Forks&logo=github)

这是一个基于Actions-OpenWrt的自动编译项目,做了一些小修改,可以编译出支持breed控制台刷入的Openwrt固件,默认用[lean的源码](https://github.com/coolsnowwolf/lede)编译,导入了[kenzok8的常用软件库](https://github.com/kenzok8/openwrt-packages.git)
lean源码直接编译的固件经过breed控制台刷入会无线重启

原理基于恩山pidge的
[[恩山]分享小米R4A千兆版编译OPENWRT(Breed直刷版)](https://www.right.com.cn/forum/forum.php?mod=viewthread&tid=4052254)

如果实在不想编译固件可以用恩山cool_rose的
[[恩山] [R4A] lean源码openwrt固件小米4A千兆版 文件管理+清新主题+ipv6+广告屏蔽](https://www.right.com.cn/forum/thread-4083541-1-1.html)

已有小米R4A但是不知道怎么刷?可以去恩山看kan1111的
[[恩山] [R4A] 【2020.04.23】win10 “傻瓜版”小米4A千兆版 NO拆机 刷Padavan](https://www.right.com.cn/forum/thread-4007071-1-1.html)

## 如何使用?

- 0 先Fork这个项目
- 1 进入到自己的项目里
- 2 点击"Actions"
- 3 点击"Workflows"下的"Build OpenWrt"
- 4 找到右侧的白色下拉栏"Run workflow"并点击
- 5 点击绿色的"Run workflow"按钮即可开始编译

## 提示

- 把.config文件上传到本项目里即可根据你的.config文件编译
- 原来的.config文件可删除,删除后将会根据源码默认配置编译
- 导入的插件库是在diy-part1.sh配置的
- 第4步的白色下拉栏"Run workflow"会发现有一个"SSH connection to Actions"并且它的值是
- .github/workflows/build-openwrt.yml里的23行为默认源码仓库,如果你想换一个源码编译可以改这一行(lean源码以外的openwrt可能会编译失败)
- 第24行为所选源码的分支
- 具体使用方法请查看[Actions-OpenWrt作者的在线说明文档](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

## 关于本项目

- [Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)
- [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)
- [kenzok8的常用软件库](https://github.com/kenzok8/openwrt-packages.git)
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub Actions](https://github.com/features/actions)
- [OpenWrt](https://github.com/openwrt/openwrt)
