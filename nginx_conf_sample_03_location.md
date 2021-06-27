
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
      


##### . /etc/nginx/nginx.conf

- ##### uri = Prefix Match
- ##### = uri = Exact Match
- ##### ^~ uri = Preferential Prefix Match
- ##### ~ uri = Exact Match case sensitive
- ##### ~* uri = Exact Match case insensitive

      events {}

      http {

         server {

            include mime.types;

            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;

            # prefix match
            location /home {
               return 200 "prefix match $uri";
            }

            # exact match
            location = /main {
               return 200 "exact match $uri";
            }

            # regex match case sensitive
            location ~ /menu[0-9] {
               return 200 "regex match case sensitive";
            }

            # regex match case insensitive
            location ~* /abount {
               return 200 "regex match case insensitive";
            }

         }

      }

##### . /etc/nginx/nginx.conf

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

##### . /etc/nginx/nginx.conf

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


##### . /etc/nginx/nginx.conf

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

##### . /etc/nginx/nginx.conf

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

##### . /etc/nginx/nginx.conf

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
