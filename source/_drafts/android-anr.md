---
title: Android ANR分析办法
categories:
keywords: ANR,Android,分析,查找
tags:
---

adb bugreport > bugreport.txt

adb pull /data/anr/traces.txt
