
##### /etc/nginx/nginx.conf

      events {}

      http {
      
         server {
            listen 80;
            server_name www.example.com;
            root /var/www/html;
            index index.nginx-debian.html;
         }
         
         server {
            listen 81;
            server_name www.example.81com;
            root /var/www/html-81;
            index index.html;
         }
         
      }

##### /var/www/html/index.nginx-debian.html

      <!DOCTYPE html>
      <html>
      <head>
      <title>Welcome to nginx!</title>
      <style>
          body {
              width: 35em;
              margin: 0 auto;
              font-family: Tahoma, Verdana, Arial, sans-serif;
          }
      </style>
      </head>
      <body>
      <h1>Welcome to nginx! port 8080</h1>
      </body>
      </html>

##### /var/www/html-81/index.html

      <!DOCTYPE html>
      <html>
      <head>
      <title>Welcome to nginx!</title>
      <style>
          body {
              width: 35em;
              margin: 0 auto;
              font-family: Tahoma, Verdana, Arial, sans-serif;
          }
      </style>
      </head>
      <body>
      <h1>Welcome to nginx! port 8080</h1>
      </body>
      </html>
