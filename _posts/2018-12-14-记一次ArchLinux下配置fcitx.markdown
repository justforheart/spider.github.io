---
layout: post
title:  "记一次ArchLinux下配置fcitx"
date:   2018-12-14 19:00:49 +0800
tags:
  - Arch
  - Linux
  - fcitx
  - 配置
categories:
  - Arch
  - Linux
  - fcitx
---

之前一直都有在用debian系，后面也用过一段时间的manjaro，自我感觉输入法配置并不是一件费劲的事。最近迷上了洗发水（ArchLinux），真实的一匹。跟着官方wiki一步步走还是掉坑里了。 
   因此，在此告诫世人，千万要仔细看wiki，一定要有耐心。 
   好吧，讲一下我的痛苦经历吧。正题：  
   首先，下载安装软件---：sudo pacman -S fcitx fcitx-im fcitx-sogoupinyin 
   当然，你得是AUR源，接着就是一路默认下去。 
   那么，问题来了，当我启动fcitx后，本以为可以美滋滋的玩耍了，但是，死活切不出那只傻狗。  
   你知道我有多绝望吗？  
   看了一下wiki还有度娘，老子改了n多次的/etc/environment和~/.bash_profile,当然~/.bashrc我也没放过  
   期间ArchLinux论坛和Ubuntu中文论坛找了一番（怪当时蠢，其实前人已经给了答案了）  
   记得当时我看到了不止一篇里提到修改~/.xprofile文件  
   但是 当时蠢啊！  
   我在这个目录里ls -al n久之后，心想要么我撸多了眼花看不到，要么就是Arch定制性太高了，网上大神的配置环境跟我的不一样。  
   而且我还坚定地认为是第二种情况  
   结果是，下班时间断断续续倒腾了4、5个小时～  
   最后才发现，他喵的，默认是没有这个文件的，但是又确实是通过这个文件配置的。  
   当我Ctrl+space出现了那个傻狗之后，我竟然会流下眼泪  
   伤心事说完了  
   其实正确配置很简单：  
   mkdir ~/.xprofile  
   nano ~/.xprofile
   把下面几行东东贴上去就行了。  
   export XMODIFIERS="@im=fcitx"  
   export GTK_IM_MODULE=fcitx  
   export QT_IM_MODULE=fcitx  
   重新启动fcitx，或者干脆注销再进来就OK了。  
   听完我的伤心故事是不是瞬间快乐了呢？  
   老子真是++了。  

