---
title: sed & awk命令
tags:
---

# [shell脚本读取文本][1]
写法一
``` sh 
#!/bin/bash
while read line
do
      echo $line     #这里可根据实际用途变化
done < filename      #filename 为需要读取的文件名
```
写法二：
``` sh
#!/bin/bash 

cat filename| while read line   #filename 为需要读取的文件名,也可以放在命令行参数里。
do
    echo $line
done
```
# 任务二——[sed替换分隔符][2]

替换字符串

```sh
 sed 's/source string/destination string/' example.log
```

替换这一行当中所有的字符

```sh {r, engine='bash', count_lines}
 sed 's/source string/destination string/g' example.log
```

完成目标任务的脚本
```sh {r, engine='bash', count_lines}
 #! /bin/bash
 
 while read line
 do
     echo $line
     sed -n "/^$line/p" "data/1_BlogContent.txt" >>2.txt
 
 done < "task1_head.txt"

```



[1]:https://fukun.org/archives/01282174.html
[2]:http://blog.csdn.net/menlinshuangxi/article/details/7979504