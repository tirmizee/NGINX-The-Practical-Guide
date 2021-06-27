##### 

    events {}

    http {

       server {

          include mime.types;

          listen 80;
          server_name www.example.com;
          root /var/www/html;
          index index.nginx-debian.html;

          # prefix match
          location /variable {
             return 200 " uri =  $uri\n connection = $connection\n content_type = $content_type\n date_local = $date_local\n date_gmt = $date_gmt\n document_root = $document_root\n host = $host\nhostname = $hostname\n remote_addr = $remote_addr\n remote_port = $remote_port\n request_method = $request_method\n server_addr = $server_addr\n server_name = $server_name";
          }

       }

    }
