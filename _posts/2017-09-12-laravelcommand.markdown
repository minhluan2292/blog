---
layout: post
title: Some Laravel Command
date: 2020-07-08 08:51:00 +0700
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: software.jpg # Add image post (optional)
tags: [Laravel, PHP] # add tag
---
## Create Project Laravel
You can create Project Laravel by 2 ways:

<p style="color:#F62217">1: Create by Composer command</p>

>composer create-project --prefer-dist laravel/laravel projectName

If error, maybe you didn't install Composer, you can install Composer at: <a href="https://getcomposer.org/download/">Composer</a>

<p style="color:#F62217">2: Create by Laravel installer</p>

If you want to create project by Laravel installer you ought to install it by: 

>composer global require laravel/installer

You can create project Laravel with:

>laravel new projectName

## Run Project

>php artisan serve

If you want run on different port

>php artisan serve  - -port=999

## Some command useful if error

>npm install

>composer install

>composer update

Remember you did cd to path of your project


