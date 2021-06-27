##### 1. 

    events {}

    http {

       server {

          include mime.types;

          listen 80;
          server_name www.example.com;
          root /var/www/html;
          index index.nginx-debian.html;

          location / {
             try_files $uri $uri/ =404;
          }

       }

    }
