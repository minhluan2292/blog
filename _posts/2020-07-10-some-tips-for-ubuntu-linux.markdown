---
layout: post
title: Some Tips For Ubuntu (Linux)
date: 2017-09-12 08:54:00 +0700
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: workflow.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Ubuntu, Server, Linux] # add tag
---
## Use command with user 
Change to account admin (if your account have permission admin)
>sudo su

## Change password root
>sudo passwd root

Install nano edit
>yum install nano zip unzip -y

Enable root login over SSH:
>nano /etc/ssh/sshd_config
Add a line in the Authentication section of the file that says PermitRootLogin yes and delete #

Restart the SSH server
>service sshd restart

## Change Timezone in Ubuntu

1. See time        
    >date
2. See timezone
    >ls /usr/share/zoneinfo/
3. See timezone Asia
    >ls /usr/share/zoneinfo/Asia
4. When you see timezone you want to change, you can change by command: 
    >cp /usr/share/zoneinfo/Asia/Ho_Chi_Minh  /etc/localtime
5. Check again by command #date
6. Sync time with internet by <strong>btpdate</strong>
 - Install ntp:
    >yum install -y ntp
 - Sync time by:
    >ntpdate vn.pool.ntp.org   
    >service ntpd start 
