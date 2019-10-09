---
layout: post
title: "nginx https"
categories:
  - Install
tags:
---

# nginx https
https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-nginx-in-ubuntu-18-04



    server {
            listen 80;
            listen [::]:80;
                    server_name slifeoss-web.com www.slifeoss-web.com;
            return 301 https://$server_name$request_uri;
    }
    
    server {
            listen 443 ssl http2;
            listen [::]:443 ssl http2;
                    include snippets/self-signed.conf;
                    include snippets/ssl-params.conf;
                    root /var/www/html/slifeoss-web/public;
                    index index.php index.html index.htm index.nginx-debian.html;
                    server_name slifeoss.com www.slifeoss.com;
    
                    location / {
                    try_files $uri $uri/ /index.php?$query_string;
            }
    
                    location ~ \.php$ {
                            include snippets/fastcgi-php.conf;
                            fastcgi_pass             unix:/var/run/php/php7.2-fpm.sock;
                            fastcgi_param   SCRIPT_FILENAME $document_root$fastcgi_script_name;
                    }
                    
                    location ~ /\.ht {
                                                    deny all;
                                    }
                    location ~ /.well-known {
                                                    allow all;
                                    }
    }

