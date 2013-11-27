---
layout: post
title: "Java Thread Dump"
description: ""
category: "java"
tags: [java, thread dump]
---
{% include JB/setup %}


[jstack](#jstack)

[Thread Dump信息](#thread-dump-info)

[Thread Run States](#thread-run-states)



<span id="jstack"></span>

## jstack

Usage:

	jstack [-l] <pid>
	    (to connect to running process)
	jstack -F [-m] [-l] <pid>
	    (to connect to a hung process)
	jstack [-m] [-l] <executable> <core>
	    (to connect to a core file)
	jstack [-m] [-l] [server_id@]<remote server IP or hostname>
	    (to connect to a remote debug server)

Options:

	-F  to force a thread dump. Use when jstack <pid> does not respond (process is hung)
	-m  to print both java and native frames (mixed mode)
	-l  long listing. Prints additional information about locks
	-h or -help to print this help message



<span id="thread-dump-info"></span>

3.1 首先介绍一下Thread Dump信息的各个部分

## Thread Dump信息

头部信息：

	时间，jvm信息
	2011-11-02 19:05:06  
	Full thread dump Java HotSpot(TM) Server VM (16.3-b01 mixed mode):  
 
线程info信息块：

	1. "Timer-0" daemon prio=10tid=0xac190c00 nid=0xaef in Object.wait() [0xae77d000]
	2.  java.lang.Thread.State: TIMED_WAITING (on object monitor)
	3.  atjava.lang.Object.wait(Native Method)
	4.  -waiting on <0xb3885f60> (a java.util.TaskQueue)     ###继续wait 
	5.  atjava.util.TimerThread.mainLoop(Timer.java:509)
	6.  -locked <0xb3885f60> (a java.util.TaskQueue)         ###已经locked
	7.  atjava.util.TimerThread.run(Timer.java:462)

	* 线程名称：Timer-0
	* 线程类型：daemon
	* 优先级: 10，默认是5
	* jvm线程id：tid=0xac190c00，jvm内部线程的唯一标识（通过java.lang.Thread.getId()获取，通常用自增方式实现。）
	* 对应系统线程id（NativeThread ID）：nid=0xaef，和top命令查看的线程pid对应，不过一个是10进制，一个是16进制。（通过命令：top -H -p pid，可以查看该进程的所有线程信息）
	* 线程状态：in Object.wait().
	* 起始栈地址：[0xae77d000]
	* Java thread statck trace：是上面2-7行的信息。到目前为止这是最重要的数据，Java stack trace提供了大部分信息来精确定位问题根源。

<span id="thread-run-states"></span>

## Thread Run States

**State**	**Description** 

**blocked**

	This thread tried to enter a synchronized block, but the lock was taken by another thread. This thread is blocked until the lock gets released. 

**blocked (on thin lock)**

	This is the same state as blocked, but the lock in question is a thin lock.

**waiting**

	This thread called Object.wait() on an object. The thread will remain there until some other thread sends a notification to that object. 

**sleeping** 
	
	This thread called java.lang.Thread.sleep(). 

**parked** 

	This thread called java.util.concurrent.locks.LockSupport.park().

**suspended** 

	The thread's execution was suspended by java.lang.Thread.suspend() or a JVMTI agent call. 




## 查找占用cpu最多的线程信息

	方案：
	java dump thread：
		jstack -l pid
	找到导致cpu高的线程:
		top -H -p pid，对应的线程id是十进制的
	十进制转十六进制，对应dump中nid(NativeThread ID)
	从dump中找到对应的线程


## 参考资料

[Using Thread Dumps(oracle doc)](http://docs.oracle.com/cd/E15289_01/doc.40/e15061/using_threaddumps.htm)

[性能分析之-- JAVA Thread Dump 分析综述](http://blog.csdn.net/rachel_luo/article/details/8920596)

[thread dump分析](http://blog.csdn.net/wanyanxgf/article/details/6944987)


