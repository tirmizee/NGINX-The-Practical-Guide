
##### 1. simple

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

##### 2. multiple location

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
      


##### . match case

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

##### if condition 01

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

##### if condition 02

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


##### root 01

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

##### root 02

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


##### . root 03

      events {}

      http {

         server {

            include mime.types;

            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;

            # prefix match
            location ~ \.(gif|jpg|png)$ {
               root /var/www/data;
            }

            # prefix match
            location /images/ {
               root /var/www/data;
            }

         }

      }

##### . try_files

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
