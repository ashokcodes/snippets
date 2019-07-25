## Install
```
sudo apt update
sudo apt install nginx
```

## Firewall
```
sudo ufw allow http
sudo ufw allow https
sudo ufw allow ssh
sudo ufw enable
```


## Status Check
```
systemctl status nginx
```


## Start/Stop/Restart
```
sudo systemctl stop nginx
sudo systemctl start nginx
sudo systemctl restart nginx
sudo systemctl reload nginx
sudo systemctl disable nginx
sudo systemctl enable nginx
```

## MySql Installation
```
sudo apt-get update
sudo apt-get install mysql-server
sudo mysql_secure_installation
```
### In MySql CLI
```
use mysql;

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';


flush privileges;

quit

```

## Node Installation
```
cd ~
curl -sL https://deb.nodesource.com/setup_11.x -o nodesource_setup.sh
sudo bash nodesource_setup.sh
sudo apt-get install nodejs
sudo apt-get install build-essential
```

## PM2 Install
```
sudo npm install -g pm2
```

## Set Up Nginx as a Reverse Proxy Server
```
sudo vim /etc/nginx/sites-available/default
```
```
location / {
    proxy_pass http://localhost:8080;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_cache_bypass $http_upgrade;
}
```
```
sudo nginx -t
```
```
sudo systemctl restart nginx
```