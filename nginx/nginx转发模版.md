```shell
worker_processes  2;

events {
    worker_connections  1024;
}


http {
    include       mime.types;
    default_type  application/octet-stream;

    client_max_body_size 80m;
    sendfile        on;

    keepalive_timeout  65;

    proxy_read_timeout 300;
    proxy_send_timeout 300;

    gzip  on;

    upstream lg-web {
        ip_hash;
        server 127.0.0.1:8087;
    }

    upstream lg-app {
        ip_hash;
        server 127.0.0.1:8085;
    }

    upstream lg-app-cms {
       ip_hash;
       server 127.0.0.1:8086;
    }

    upstream lg-platform {
        ip_hash;
        server 127.0.0.1:8088;
    }
    upstream lg-cms {
		ip_hash;
		server 127.0.0.1:8089; 
    }
   upstream lg-tts {
	ip_hash;
	server 127.0.0.1:8091;			
   }	

    server {
        listen       80;
		server_name www.shlgservice.com shlgservice.com;

        location / {
            root   html;
            index  index.html index.htm;
			proxy_pass http://lg-web;
        }

		location /lg/ {
			alias D:/app/data/lgqfj/lg/;
        }

       location /lg_mb/ {
            alias D:/app/data/lgqfj/lg_mb/;
        }
		location /downloadApp/ {
            alias D:/app/data/lgqfj/excel/;
        }

	location /static/ {
	    alias D:/app/lg-web-8087/webapps/ROOT/static/;
	}

       location /lg-app/ {
            proxy_pass http://lg-app;
       }
        location /lg-app-cms/ {
            proxy_pass http://lg-app-cms;
        }
        location /lg-platform/ {
            	proxy_pass http://lg-platform;
   		
        }
	location /cms/ {
	    proxy_pass http://lg-cms;
	}
	location /lg-tts/ {
	    proxy_pass http://lg-tts;
	}

  }

}



```