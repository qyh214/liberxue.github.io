---
layout: post
title:  "Mac开启任何来源"
date:   2017-03-22
ascription: study
excerpt: "mac 10.12之后开启任何来源"
tag:
- Mac
- Capitan
- 任何来源
comments: true
---
>Mac升级了mac10.12最新版本的系统,也相信在升级了macOS Sierra (10.12)版本后,在"安全性与隐私"中找不到"任何来源"选项

{% highlight css %}
sudo spctl --master-disable
{% endhighlight %}