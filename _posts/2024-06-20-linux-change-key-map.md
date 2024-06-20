---
title: Linux change key map
date: 2024-06-20
category: notes
---

xmodmap 

[xmodmap](https://www.x.org/archive/X11R6.8.1/doc/xmodmap.1.html)是个非常强力的键位修改工具

因为HHKB在mac里经常把meta当作ctrl来用，我希望在debian里面左边meta键跟ctrl是一样的效果

具体命令如下

1. 查看现在键位map
```
xmodmap -pm
```
mod4 对应的是 
```
Super_R (0x86),  Hyper_L (0xcf),  Super_L (0x85),  Super_L (0xce)
```
其中Super L对应的是meta键


2. 把meta功能对应的mod4取消
```
xmodmap -e "remove mod4 = Super_L" 
```

3. 把meta键加入ctrl里面
```
xmodmap -e "add control = Super_L" 
```

4. 确认更改成功
```
xmodmap -pm
```