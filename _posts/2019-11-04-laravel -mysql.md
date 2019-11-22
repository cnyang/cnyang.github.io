https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04

sudo apt-get install php-mysql
sudo vim /etc/php/7.2/fpm/php.ini
extension=mysql
sudo systemctl restart php7.2-fpm
php artisan migrate:install

