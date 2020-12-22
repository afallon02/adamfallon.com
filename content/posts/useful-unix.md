---
title: "Useful Unix"
date: 2020-12-22T12:27:52Z
draft: false
---


# Table of Contents

1.  [How to show top 20 largest files from the command line](#orgc18fed5)
2.  [Show all ports open on a machine](#orga322f9c)
3.  [Find your internal ip address](#org21edf24)



<a id="orgc18fed5"></a>

# How to show top 20 largest files from the command line

    sudo du -a / | sort -n -r | head -n 20


<a id="orga322f9c"></a>

# Show all ports open on a machine

    nmap -sn <INTERNAL IP ADDRESS>


<a id="org21edf24"></a>

# Find your internal ip address

    ip addr

