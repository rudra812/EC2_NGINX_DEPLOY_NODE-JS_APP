sudo apt update
sudo apt upgrade -y
sudo apt install git -y
sudo apt install nodejs -y
git clone ""
sudo apt install nginx
enable/start nginx -- > sudo systemctl enable nginx/ sudo systemctl start nginx
check nginx status --> sudo systemctl status nginx

in root folder type --> sudo nano /etc/nginx/sites-available/default

paste below info
--------------------

server {
    listen 80;
    server_name _;

    location /api/ {
        proxy_pass http://127.0.0.1:4500/;

        proxy_http_version 1.1;

        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
Nano Editor commands:
---------------------------
Writeout - CTRL + o
SAVE - ENTER
EXIT - CTRL + X

Test updated configuartion
----------------------------------
sudo nginx -t

reload updated nginx config:
-------------------------------------
sudo systemctl reload nginx

npm start


enable nginx
------------------------------------
sudo systemctl enable nginx


check nginx status
---------------------------------------
sudo systemctl status nginx

start nginx
------------------------
sudo systemctl start nginx

stop nginx
------------------------
sudo systemctl stop nginx

Test configuartion
------------------------
sudo nginx -t

