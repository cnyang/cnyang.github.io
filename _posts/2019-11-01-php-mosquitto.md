---
layout: post
title: "php mosquitto"
categories:
  - Install
tags: 
  - ubuntu
  - php
  - mosquitto
---

###install

https://mosquitto.org/download/
https://mosquitto-php.readthedocs.io/en/latest/index.html

sudo apt-add-repository ppa:mosquitto-dev/mosquitto-ppa
sudo apt update
sudo apt install libmosquitto-dev
sudo pecl install Mosquitto-alpha
cd /etc/php/7.2/fpm
sudo vim php.ini
sudo systemctl restart nginx
sudo systemctl restart php7.2-fpm.service

https://www.cyberciti.biz/faq/how-to-reload-restart-php7-0-fpm-service-linux-unix/
replace php7.0 to php7.2

check phpinfo for  mosquitto

```php
<?php
try {
    $c = new Mosquitto\Client;
    $c->onConnect(function() use ($c) {
        $c->publish('cnyang/test', 'Hello', 1);
        $c->disconnect();
    });

    $c->connect('test.mosquitto.org');

    // Loop around to permit the library to do its work
    // This function will call the callback defined in `onConnect()`
    // and disconnect cleanly when the message has been sent
    $c->loopForever();

    echo "Finished\n";
} catch (Mosquitto\Exception $ex) {
    var_dump($ex);
}
?>
```
