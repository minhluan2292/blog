---
layout: post
title: Cron Job (Task Scheduling) For Laravel Ubuntu
date: 2020-07-14 10:12:20 +0700
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. #### Add post description (optional)
img: github.svg #### Add image post (optional)
fig-caption: #### Add figcaption (optional)
tags: [CronJob, Laravel, Autotask, Autorun, Task Scheduling]
---

1. Create command
>php artisan make:command NameCommand

One command will create at <strong>app/Console/Commands</strong>
You can rename:

* <strong>protected $signature = 'command:name';</strong> example => <strong>protected $signature = 'hour:update';</strong>
* <strong>protected $description = ‘Command description’;</strong> example => <strong>protected $description = ‘Send an hourly email to all the users’;</strong>

You will change code in handle() function you want to execute

![Cronjob 1]({{site.baseurl}}/assets/img/cronjob1.jpg)

For registering the command, go to <strong>app/console/kernal.php</strong> and place the following code:

![Cronjob 2]({{site.baseurl}}/assets/img/cronjob2.jpg)

### fter that, If you want run Cron Job on Ubuntu (Linux), you will do:

1. CD to path of your laravel Project and run: 

![Cronjob 3]({{site.baseurl}}/assets/img/cronjob3.jpg)

After that, you will run command: 
>crontab -e
And you add as image:

![Cronjob 4]({{site.baseurl}}/assets/img/cronjob4.jpg)

OR:
>* * * * * cd /path-to-your-project && php artisan schedule:run >> /dev/null 2>&1

Finish :D




