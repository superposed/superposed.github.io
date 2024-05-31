---
title: 2024 SpiritGame writeup
date: 2024-05-30 20:24:56
tags:
- CTF
categories: 
- 网络安全
---
## **Misc:App1e_Tree's Big Duck**

最开始以为要百度识图，后面发现直接访问官网[https://jluctf.top/member]()点出题者LiBr的头像跳转到博客[https://nvme0n1p.dev/ ]()发现长城杯的这篇文章
![](1.jpg)
百度找到长城杯官网ccb.itsec.gov.cn按照题目格式即可拼接flag

## **Misc:****俄罗斯方块**

游戏题：超过3000分即可获得flag，多练习即可轻松获得flag（

## **Misc:sqlshark**

观察数据包即可发现是sqlmap头，可以筛一下HTTP
![图片](2.jpg)
直接从最后翻，这里只需要看返回的HTTP数据包，GET开头的可以不看，找到数据包发现Unicode编码，解码后
![图片](3.jpg)
`username:qvzbq[\"今天设计了一个数据库的系统来玩，打算用来试试永不过时的sqlmap~\\r\\n\\r\\n虽然但是sqlmap真好用啊，直接把我精心设计的服务器打爆了！\\r\\n\\r\\n还好我没有在服务器里藏flag（？我只是放了点其他的东西www\\r\\n\\r\\nhkwcyo4.24hkwcyo1hkwcyo4.22hkwcyo日寄4.24\"]qjqzq`

继续往下翻
![图片](4.jpg)
`username:qvzbq[\"1hkwcyo所以你放了什么东西？hkwcyo1\", \"2hkwcyo是https://gist.github.com/lbr77/891f6326b8a0b5e1b6a4369c55de1b3a啦~hkwcyo2\", \"3hkwcyo这个东西的密码会是什么？hkwcyo1\",
\"4hkwcyo记得我的群昵称吗？hkwcyo2\", \"5hkwcyo对了！苹果派！hkwcyo1\", \"6hkwcyo我去，孤独摇滚！难道flag是bochi the rock？hkwcyo2\",
\"7hkwcyo不对不对~和波奇没有关系！flag是SpiritGame{这个角色名字的英文，不带空格！}hkwcyo1\"]qjqzq`

找到正确flag提示，观察作者头像是miku 搜一下英文名Hatsune Miku去掉空格即可得到flag

## **Web:** **GomokuMaster**

游戏题直接在前端修改js代码

找到这个function
![图片](5.jpg)
把对面的回合改成自己的就可以顺利获得flag