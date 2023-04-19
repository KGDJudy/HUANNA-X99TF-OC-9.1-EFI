# HUANNA-X99TF-OC-9.1-EFI
配置：
#1.主板：华南X99TF
#2.独显：AMD 6800XT
#3.内存：DDR4 ECC 2400HZ  32G*2
#4.CPU：E5 2666 V3
#5.WIFI及蓝牙：BCM 94360Z4
#6.系统版本：Ventura 13.3.1 (22E261)



BIOS设置：
ACPI Settings>ACPI Sleep State=S3(开启S3睡眠支持，需要的童学可以开启）
CSM Configuration>CSM Support=Disabled(首先要把Boot Option Filter=UEFI Only，这里改完重启重新进BIOS才能改上一步）
NCT5532D Super I0 Configuration>Restone AC Power Loss=Powen On(这个是开启来电自启功能）

OC版本更新为9.1。机型有Mac Pro7,1，Mac Pro7,1的已自定义内存，能启用显示ECC，我是128G内存，内存比我大的（然后，比我小的可直接食用），可自行在Platformlnfo>Memory修改，Size（即容量）按你实际减少，总容量加起来为你实际的容量即可，Speed（即频率）按实际的填写，SeriaNumber、PartNumber、DeviceLocato这些可以随便填，也可以按你实际内存型号信息等填写，如是DDR4的，需将DataWidth改成64，Type改成26，非ECC内存的请把ErrorCorrection改成1或2（非ECC的建议改2）。我的自己修改一些装*参数，实际上没图的频率那么高，哈哈。

如不懂的怎么自定义的，请移至https://bbs.pcbeta.com/viewthread-1872987-5-1.html此大神教程。或是在Kernel里添加SystemProfilerMemoryFixup.kext。

这次WhateverGreen.kext仍是用1.5.7，不过这次的WEG版本是是LEE大神魔改的，更高的版本我就没去测试了，此EFI里有加了5000、6000系列独显的注释，同时也有单独针对6600或6600xt部分品牌卡出现显示输出口异常问题：如只有一个DP口有输出，或亮屏速度太慢等问题简单、半解决方法。

另外我仍继续用DSDT-HUANANZHI.aml来解决声卡驱动，没太多时间去折腾，反正也不用WIN，用WIN也是直接用PD，所以不存在双系统引导WIN时卡ACPI问题。有需的伙伴自取，哈哈。
