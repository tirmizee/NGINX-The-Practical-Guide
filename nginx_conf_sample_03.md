##### 1. /etc/nginx/nginx.conf 

      events {}

      http {

         server {

            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;

            location /greeting {
               return 200 "$host $uri $date_gmt";
            }

         }

      }

##### 2. /etc/nginx/nginx.conf

      events {}

      http {

         server {

            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;

            location /greeting {
               return 200 "$host $uri $date_gmt";
            }

         }

      }
