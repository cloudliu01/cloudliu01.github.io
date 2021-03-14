---
title: LicenseMonitorWhitepaper
top: false
cover: false
toc: true
mathjax: true
date: 2021-01-30 22:25:23
password:
summary:
img:
tags: License Monitor Whitepaper
categories: Whitepapers
---

# License Monitor 白皮书 #

## 项目背景 ##
在专业的设计领域，比如建筑，芯片，医学，都在上世纪末本世纪初经历了一个盗版横行的年代。一部分的原因是正版软件高昂的授权费用，另一部分原因是国内相关企业处于原始积累阶段，没有足够利润去支撑正版授权。随着时代的进步，国内相关行业的崛起，盗版高昂的试错成本，以及政府的支持，越来越多的公司开始选用正版软件。

## 商业软件授权方式 ##
{% asset_img 1.png License Types %}
现在商业软件的正版授权有多种类型
* Local
  * 每个用户有单独的license file 或 key，在安装时输入。一般key会和用户名或者硬件网卡地址绑定。
  * 另一个许可证模型是每个加密狗(Dongle)的许可，它允许加密狗的所有者在任何计算机上使用该程序。 不同于单独key，加密狗可以用在任何机器上，所以硬件升级后也可以使用。
* Centralized
所欧license都是在网络服务器上统一管理，用户可以根据需要checkout不同feature和数量的license。因为网络上用户同时需要某些license的机会很少，所以需要购买的license总数是可以适当少于总的用户数量的。另外，根据每种feature的使用率不同，也可以制定不同的购买比率，提高license使用率减少购买成本。
  * Node Locked: 虽然license是centralized管理，但只能特定范围的用户使用。
  * Concurrent / FLoating: 也称为Concurrent License或Network License，是一种在大量用户之间共享有限数量的软件应用程序license的一种方法。License Server可以通过局域网，Intranet，虚拟专用网络或Internet管理License。 当授权用户希望运行该应用程序时，他们会向中央license服务器请求许可证。 如果license可用，则license服务器将允许该应用程序运行。 当他们完成使用该应用程序时，或者当允许的许可期限到期时，许可服务器将收回该license并将其提供给其他授权用户。 这样的运作模式保证多名用户可以分时段使用同样的license提高利用率。 Foating License通常用于公司环境中的高价值应用程序； 例如电子设计自动化或工程工具。 同时，它的用途正在整个软件行业中广泛扩展。同时这也是最灵活的一种方式，也是我们这个白皮书主要讨论的一种方式。

除了以上的分类方式外，您可以在永久（Perpetual）许可证和年度许可证之间进行选择。 对于永久许可，通常需要一年的维护，续订折扣不大；对于年度许可证则没有任何续期，过期后必须购买新许可证，但新许可证一般会给很大折扣。对于需要持续更新和支持的软件，建议选用后一种方式。

## FlexLM ##
    FLEXlm软件是一种在专业软件（如 EDA）行业的license管理解决方案，可让软件供应商对客户可用的软件数量加以限制。 FLEXlm支持不同的许可策略，例如Floating和N-locked许可。 这种软件系统也称为DRM（数字版权管理）解决方案。 FLEXlm最初是1988年由GLOBEtrotter软件和Highland Software共同开发的。后来，Globetrotter在2000年被Macrovision收购，并将其更名为FlexNet。 在2008年，该公司被出售给Acresso Software，并更名为Flexera。 该产品名为Flexera FlexNet Publisher，但仍被广泛称为FlexLM。 2011年，加拿大教师私人资本基金收购了Flexera。 [2]

## 商业现状 ##
Floating license被广泛应用于公司环境中的高价值应用程序，例如半导体工业的电子设计自动化工具的标准license管理模式。在这些使用环境中，每个license * feature * count 的价格少则上千，多则上万。对一个有上百人的设计公司，所要购买的license的价值常常是以百万美金计。因此，如何提高license的使用效率，避免浪费成为一个必须要考虑的问题。
因为国内正版市场还不成熟，提高license的效率更是一个很少人考虑的问题；同时，市面上能监控和管理这种floating license的工具又非常少，因此在是一个相对有前景的商业机会。

## 项目价值 ##
本软件可以帮助使用FlexLM centralized方式来管理license的公司客户监控license的使用情况，从而合理地采购和分配license提高使用效率，最终达到有效管理并降低运营成本的目的

## 项目结构 ##
* lmstat parser - 执行lmstat命令从服务器得到当前license使用的情况。
* log parser - 读入并分析license log文件。
* test database & case generator - 产生测试用的lmstat和log文件用于开发调试。
* database - 后台数据库，用于保存lmstat和log parsers的输出数据便于viewer查询使用
* viewer - 用户界面，用于和后台数据库交互，显示用户所需信息

## 项目开发规划 ##
## 团队人员 ##
## 相关链接 ##

1. Scholten, Thomas. "Software Licensing". Retrieved 21 May 2012.
2, https://en.wikipedia.org/wiki/FlexNet_Publisher
3, https://en.wikipedia.org/wiki/Floating_licensing
