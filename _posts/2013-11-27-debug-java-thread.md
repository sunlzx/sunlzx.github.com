---
layout: post
title: "debug java thread"
description: ""
category: "debug"
tags: [debug, thread]
---
{% include JB/setup %}

### 查看进程的线程CPU占用情况

	top -H -p 30225

### 跟Java threead dump的线程对应起来

top -H pid 转为16进制，就是java thread dump 里的nid

<!-- 
!["thread native id"](/images/2013/11/debug-java-thread/thread-nid.png)
-->

<img src="/images/2013/11/debug-java-thread/thread-nid.png" alt="thread native id" title="thread native id" width="800" />

### strace attach 正在运行的进程或线程

	strace -p pid/tid

### stracd gdb

	strace用法
	gdb用法


