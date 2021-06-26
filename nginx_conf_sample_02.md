
##### /etc/nginx/nginx.conf

      events {}

      http {
         server {
            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;
         }
      }
