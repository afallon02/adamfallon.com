---
title: "Useful Unix"
date: 2020-12-22T12:27:52Z
draft: false
---

# Table of Contents

1.  [How to show top 20 largest files from the command line](#org28f7e84)
2.  [Show all ports open on a machine](#org41187ab)
3.  [Find your internal ip address](#org58b27bd)
4.  [Create a user and add it to a group](#orge72f29b)



<a id="org28f7e84"></a>

# How to show top 20 largest files from the command line

    sudo du -a / | sort -n -r | head -n 20


<a id="org41187ab"></a>

# Show all ports open on a machine

    nmap -sn <INTERNAL IP ADDRESS>


<a id="org58b27bd"></a>

# Find your internal ip address

    ip addr


<a id="orge72f29b"></a>

# Create a user and add it to a group

    # Create the new group
    sudo groupadd GROUPNAME
    # Add user to new group (requires you to logout after)
    sudo usermod -aG GROUPNAME $USER
    # See which groups you are a part off
    groups

# Mounting a drive

	# Show all mounted drives
	mount
	# Show only ext4 formatted drives
	mount -t ext4
	# Create a mountpoint
	sudo mkdir /media/<NAME>
	# Mount
	sudo mount /dev/<DRIVE> /media/<NAME>
