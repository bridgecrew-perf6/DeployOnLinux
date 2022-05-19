
Nginx reverse proxy:
go to sudo nano /etc/nginx/sites-enabled/default.
edit:
location / {
                # First attempt to serve request as file, then
                # as directory, then fall back to displaying a 404.
                # try_files $uri $uri/ =404;
              proxy_pass http://localhost:3000;
              proxy_set_header X-Real-IP $remote_addr;
              proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
              proxy_set_header Host $http_host;
              proxy_set_header X-NginX-Proxy true;
              proxy_set_header Upgrade $http_upgrade;
              proxy_set_header Connection "upgrade";

        }

ufw 5000 port allow :
ufw allow 5000/tcp
