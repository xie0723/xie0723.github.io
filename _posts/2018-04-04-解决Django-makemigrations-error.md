---
layout:     post
title:      2018-04-04-解决Django-makemigrations-error
subtitle:
date:       2018-04-04
author:     xwm
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - Python
    - Django
---


## 问题

使用Django，创建迁移文件的时候，提示如下报错↓：

> python manage.py makemigrations

> You are trying to add a non-nullable field 'phone' to student without a default; we can't do that (the database needs something to populate existing rows).
Please select a fix:
 1) Provide a one-off default now (will be set on all existing rows with a null value for this column)
 2) Quit, and let me add a default in models.py




### 解决：

-  方法一


    phone = models.CharField(max_length=128, verbose_name='电话',null=True,blank=True)




- 方法二

    phone = models.CharField(max_length=128, verbose_name='电话',default='blank')



### 区别：

设置default='blank' 时，会在前端phone 一栏，表中默认填充 blank （如下图↓）.

![](.2018-04-04-解决Django-makemigrations-error_images\default_blank.png)