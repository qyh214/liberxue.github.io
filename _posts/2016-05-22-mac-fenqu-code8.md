---
layout: post
title: "MAC 中该磁盘不能被分区，因为文件系统验证失败错误代码8"
date:  2016-05-22
ascription: study
excerpt: "MAC 中该磁盘不能被分区，因为文件系统验证失败错误代码8 磁盘修复操作失败，因为文件系统验证失败错误代码8"
tag:
- MAC分区
- 错误代码8
- 文件系统验证失败
comments: true
feature: /upload-img/bj/018.jpg
---
手贱mac磁盘分区时间加密了磁盘跟主磁盘密码不一致

分区 修复 提示：MAC 中该磁盘不能被分区，因为文件系统验证失败错误代码8

解决方案： 一直按住Command+S键启动到单用户模式。10.12以上出现登陆，输入密码即可

系统自动进入 加载（出现root #）后，

输入小写的

{% highlight css %}
#container {
fsck -f 命令并按回车键Enter
}
{% endhighlight %}



耐心等待大概1分钟的Checking过后，

{% highlight css %}
#container {
提示The Volume Macintosh HD was repaired successfully（宗卷Macintosh HD修复成功），
}
{% endhighlight %}


再输入
{% highlight css %}
#container {
reboot //按Enter重启到苹果系统
}
{% endhighlight %}
，

第一次执行fsck -f后，没有修复成功，第二次，同样操作，执行/sbin/fsck -f终于显示修复成功。

在网上查了下问题原因：Boot Camp助理分区提示该磁盘不能被分区，因为不能移动某些文件，磁盘工具提示分区失败：未能修改分区图，因为文件系统验证失败，多出现在使用较久、存储文 件较多的旧版苹果系统里。苹果Mac OS X系统里的fsck -f命令，相当于Windows系统的chkdsk命令（全称为CheckDisk，磁盘检查），用于修复磁盘的逻辑错误。

