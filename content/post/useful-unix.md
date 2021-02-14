---
title: "Useful Unix"
date: 2020-12-22T12:27:52Z
draft: false
image: https://www.poftut.com/wp-content/uploads/2016/12/img_584a2378c01cd.png
---

# Table of Contents

1.  [How to show top 20 largest files from the command line](#orga1e7b06)
2.  [Show all ports open on a machine](#org8db6d37)
3.  [Find your internal ip address](#org2d6e8ff)
4.  [Find your external ip address](#org6c2d27d)
5.  [Create a user and add it to a group](#org5ca7631)
6.  [Create a full system backup with rsync](#orgeafebdb)



<a id="orga1e7b06"></a>

# How to show top 20 largest files from the command line

    sudo du -a / | sort -n -r | head -n 20


<a id="org8db6d37"></a>

# Show all ports open on a machine

    nmap -sn <INTERNAL IP ADDRESS>


<a id="org2d6e8ff"></a>

# Find your internal ip address

    ip addr


<a id="org6c2d27d"></a>

# Find your external ip address

    curl ifconfig.co


<a id="org5ca7631"></a>

# Create a user and add it to a group

    # Create the new group
    sudo groupadd GROUPNAME
    # Add user to new group (requires you to logout after)
    sudo usermod -aG GROUPNAME $USER
    # See which groups you are a part off
    groups


<a id="orgeafebdb"></a>

# Create a full system backup with rsync

    set -euxo pipefail;
    
    current_date=`date -I`;
	backup_dir=`/tmp/backups` # Set this to somewhere approriate
    
    mkdir -p $backup_dir/$current_date;
    
    rsync --delete -aAXv / --exclude={"/dev/*","/proc/*","/sys/*","/tmp/*","/run/*","/mnt/*","/media/*","/lost+found","/swapfile"} $backup_dir/$current_date;

