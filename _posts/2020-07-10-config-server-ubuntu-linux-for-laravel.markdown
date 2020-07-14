---
layout: post
title: Config Server Ubuntu 20.04 (Linux) for Laravel
date: 2020-07-10 00:00:00 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: how-to-start.jpg # Add image post (optional)
tags: [Server, Ubuntu, Linux, Laravel] # add tag
---
Cài đặt Apache
Sau khi có VPS chúng cần cài đặt môi trường Apache(các bạn cũng có thể dùng Nginx).

Update: 
> apt-get update

Cài đặt Apache: apt-get install apache2

Sau khi cài đặt bạn có thể start và enable Apache bằng cách:

>systemctl start apache2

If you don't have admin role, you use <strong>sudo</strong> before command, example:
>sudo systemctl start apache2

>systemctl enable apache2
 
>Cài đặt PHP

Thêm PHP vào khi PPA:

>add-apt-repository ppa:ondrej/php

Update:

>apt-get update

Chạy lệnh sau để cài PHP 7.2 và các extension cần thiết:

>apt install php7.2 php7.2-xml php7.2-mbstring php7.2-mysql php7.2-json php7.2-curl php7.2-cli php7.2-common php7.1-mcrypt php7.2-gd libapache2-mod-php7.2 php7.2-zip

Cài đặt Composer và install Laravel
Composer

>curl -sS https://getcomposer.org/installer | php

>mv composer.phar /usr/bin/composer

Install Laravel

Các bạn dùng composer để cài hoặc có thể dùng Git để clone source code vào đường dẫn: /var/www/html

composer create-project laravel/laravel /var/www/html/laravel

Cài đặt DocumentRoot
Mở file config của Apache:

nano /etc/apache2/sites-available/000-default.conf

Tìm dòng sau:

DocumentRoot /var/www/html

Thay thế bằng:

DocumentRoot /var/www/html/laravel/public

![Example]({{site.baseurl}}/assets/img/ubuntu_laravel_1.jpg)

Sau đó lưu lại rồi restart lại Apache nhé:

>systemctl restart apache2

Chỉnh Permission cho project:

>chown -R www-data:www-data /var/www/html/laravel

>chmod -R 755 /var/www/html/laravel/storage

Cài MySQL

Chạy lệnh sau:

>apt-get install mysql-server

Sau đó nhập password:



Đăng nhập MySQL với password ở trên:

mysql -u root -p


Thêm database bằng query sau:

CREATE DATABASE laravel_test;


Cấu hình .env cho project để connect MySQL:
Sửa file bằng cách:

nano /var/www/html/laravel/.env

Sau đó cấu hình giống như dưới local:



Tận hưởng:
Truy cập và tận hưởng bằng cách truy cập vào: IP của VPS

Kết thúc
Trên đây là toàn bộ các bước để deploy project Laravel lên VPS dùng hệ điều hành Ubuntu. Bài viết có gì sai sót mong mọi người bỏ quá cho