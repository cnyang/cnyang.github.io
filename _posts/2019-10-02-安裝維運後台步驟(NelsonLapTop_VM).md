---
layout: post
title: "install step"
categories:
  - Install
tags:
---

# 安裝維運後台步驟(NelsonLapTop VM)

## install nginx + laravel
https://websiteforstudents.com/setup-laravel-php-framework-on-ubuntu-16-04-17-10-18-04-with-nginx-and-php-7-2-support/

    sudo apt-get install php-pgsql
    sudo apt-get install php-curl
     cnyang@ubuntuserver:/etc/nginx/sites-enabled$ sudo rm default

----------

install postgres

https://websiteforstudents.com/installing-postgresql-10-on-ubuntu-16-04-17-10-18-04/

    sudo -i -u postgres
    creasteuser slife -P
    su -l cnyang
    cp dumpfile to /var/lib/postgresql
    sudo chown postgres:postgres dump-smartlife-201909031805.backup
    createdb smartlife
    psql -f dump-smartlife-201909031805.backup smartlife postgres
----------
## 修改 .env

Laravel .env環境設定檔內db是指向slifeoss-pg
在本地環境要指向127.0.0.1

    cd /var/www/html/slifeoss-web
    sudo mv .env .env.IOT
    sudo cp .env.dev .env
    sudo systemctl stop nginx.service
    sudo systemctl start nginx.service
    sudo usermod -a -G www-data cnyang
    sudo chmod -R 775 slifeoss-web/








