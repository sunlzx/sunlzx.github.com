---
layout: post
title: "bash shell"
description: ""
category: "shell"
tags: [shell]
---
{% include JB/setup %}

## for loop syntax

	for VARIABLE in 1 2 3 4 5 .. N
	do
		command1
		command2
		commandN
	done

OR

	for VARIABLE in file1 file2 file3
	do
		command1 on $VARIABLE
		command2
		commandN
	done

OR

	for OUTPUT in $(Linux-Or-Unix-Command-Here)
	do
		command1 on $OUTPUT
		command2 on $OUTPUT
		commandN
	done


## 相关资料

[Bash For Loop Examples](http://www.cyberciti.biz/faq/bash-for-loop/)