
##### 1. /etc/nginx/nginx.conf 

```sql

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

```

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
            
            location /profile {
               return 200 "profile page";
            }

         }

      }
      

##### 3. /etc/nginx/nginx.conf

      events {}

      http {

         server {

            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;

            if ( $arg_apikey != 12345 ){
               return 401 "Incorrect API KEY";
            }

            location /greeting {
               return 200 "$host $uri $date_gmt";
            }
            
            location /profile {
               return 200 "profile page";
            }

         }

      }

##### 4. /etc/nginx/nginx.conf

      events {}
      
      http {

         server {

            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;

            if ( $arg_apikey != 12345 ){
               return 401 "Incorrect API KEY";
            }

            location /greeting {
               return 200 "$host $uri $date_gmt";
            }

            location /profile {
               if ( $arg_profile_id != "tirmizee" ) {
                  return 410 "Incorrect profile";
               }
               return 200 "profile page";
            }

           }

      }


##### 5. /etc/nginx/nginx.conf

      events {}

      http {

         server {

            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;

            location /data.json {
               root /var/www/html/static;
               index data.json;
            }

         }

      }

##### 6. /etc/nginx/nginx.conf

      events {}

      http {

         server {

            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;

            location /readme.txt {
               index readme.txt;
            }

            location /data.json {
               root /var/www/html/static;
               index data.json;
            }

         }

      }

##### 7. /etc/nginx/nginx.conf

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
